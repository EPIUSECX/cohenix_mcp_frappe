# Master Control Plan: `Repost Payment Ledger`

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
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `filters_section` | Filters | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  |  | None | None |
| `add_manually` | Add Manually | Check | None |  |  |  | 0 | Ignore Voucher Type filter and Select Vouchers Manually |
| `status_section` | Status | Section Break | None |  |  |  | None | None |
| `repost_status` | Repost Status | Select | 
Queued
Failed
Completed |  |  | ✅ | None | None |
| `repost_error_log` | Repost Error Log | Long Text | None |  |  |  | None | None |
| `selected_vouchers_section` | Vouchers | Section Break | None |  |  |  | None | None |
| `repost_vouchers` | Selected Vouchers | Table | Repost Payment Ledger Items |  |  |  | None | None |
| `amended_from` | Amended From | Link | Repost Payment Ledger |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/repost_payment_ledger/repost_payment_ledger.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Repost Payment Ledger", {
	setup: function (frm) {
		frm.set_query("voucher_type", () => {
			return {
				filters: {
					name: ["in", ["Purchase Invoice", "Sales Invoice", "Payment Entry", "Journal Entry"]],
				},
			};
		});

		frm.fields_dict["repost_vouchers"].grid.get_field("voucher_type").get_query = function (doc) {
			return {
				filters: {
					name: ["in", ["Purchase Invoice", "Sales Invoice", "Payment Entry", "Journal Entry"]],
				},
			};
		};

		frm.fields_dict["repost_vouchers"].grid.get_field("voucher_no").get_query = function (doc) {
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
		if (frm.doc.docstatus == 1 && ["Queued", "Failed"].find((x) => x == frm.doc.repost_status)) {
			frm.set_intro(
				__(
					"Use 'Repost in background' button to trigger background job. Job can only be triggered when document is in Queued or Failed status."
				)
			);
			var btn_label = __("Repost in background");

			frm.add_custom_button(btn_label, () => {
				frappe.call({
					method: "erpnext.accounts.doctype.repost_payment_ledger.repost_payment_ledger.execute_repost_payment_ledger",
					args: {
						docname: frm.doc.name,
					},
				});
				frappe.msgprint(__("Reposting in the background."));
			});
		}
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
