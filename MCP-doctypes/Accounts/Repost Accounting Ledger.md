# Master Control Plan: `Repost Accounting Ledger`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_vpup` | None | Column Break | None |  |  |  | None | None |
| `delete_cancelled_entries` | Delete Cancelled Ledger Entries | Check | None |  |  |  | 0 | None |
| `section_break_metl` | None | Section Break | None |  |  |  | None | None |
| `vouchers` | Vouchers | Table | Repost Accounting Ledger Items |  |  |  | None | None |
| `amended_from` | Amended From | Link | Repost Accounting Ledger |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/repost_accounting_ledger/repost_accounting_ledger.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Repost Accounting Ledger", {
	setup: function (frm) {
		frm.fields_dict["vouchers"].grid.get_field("voucher_type").get_query = function (doc) {
			return {
				query: "erpnext.accounts.doctype.repost_accounting_ledger.repost_accounting_ledger.get_repost_allowed_types",
			};
		};

		frm.fields_dict["vouchers"].grid.get_field("voucher_no").get_query = function (doc) {
			if (doc.company) {
				return {
					filters: {
						company: doc.company,
						docstatus: 1,
					},
				};
			}
		};
	},

	refresh: function (frm) {
		frm.add_custom_button(__("Show Preview"), () => {
			frm.call({
				method: "generate_preview",
				doc: frm.doc,
				freeze: true,
				freeze_message: __("Generating Preview"),
				callback: function (r) {
					if (r && r.message) {
						let content = r.message;
						let opts = {
							title: "Preview",
							subtitle: "preview",
							content: content,
							print_settings: { orientation: "landscape" },
							columns: [],
							data: [],
						};
						frappe.render_grid(opts);
					}
				},
			});
		});
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
No dashboard charts found.


### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
