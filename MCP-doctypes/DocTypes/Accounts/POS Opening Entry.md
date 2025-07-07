# Master Control Plan: `POS Opening Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `POS-OPE-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `period_start_date` | Period Start Date | Datetime | None | ✅ |  |  | None | None |
| `period_end_date` | Period End Date | Date | None |  |  | ✅ | None | None |
| `status` | Status | Select | Draft
Open
Closed
Cancelled |  | ✅ | ✅ | Draft | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `set_posting_date` | Set Posting Date | Check | None |  |  |  | 0 | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `pos_profile` | POS Profile | Link | POS Profile | ✅ |  |  | None | None |
| `pos_closing_entry` | POS Closing Entry | Data | None |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `user` | Cashier | Link | User | ✅ |  |  | None | None |
| `opening_balance_details_section` | None | Section Break | None |  |  |  | None | None |
| `balance_details` | Opening Balance Details | Table | POS Opening Entry Detail | ✅ |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | POS Opening Entry |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_opening_entry/pos_opening_entry.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("POS Opening Entry", {
	setup(frm) {
		if (frm.doc.docstatus == 0) {
			frm.trigger("set_posting_date_read_only");
			frm.set_value("period_start_date", frappe.datetime.now_datetime());
			frm.set_value("user", frappe.session.user);
		}

		frm.set_query("user", function (doc) {
			return {
				query: "erpnext.accounts.doctype.pos_closing_entry.pos_closing_entry.get_cashiers",
				filters: { parent: doc.pos_profile },
			};
		});
	},

	refresh(frm) {
		// set default posting date / time
		if (frm.doc.docstatus == 0) {
			if (!frm.doc.posting_date) {
				frm.set_value("posting_date", frappe.datetime.nowdate());
			}
			frm.trigger("set_posting_date_read_only");
		}
	},

	set_posting_date_read_only(frm) {
		if (frm.doc.docstatus == 0 && frm.doc.set_posting_date) {
			frm.set_df_property("posting_date", "read_only", 0);
		} else {
			frm.set_df_property("posting_date", "read_only", 1);
		}
	},

	set_posting_date(frm) {
		frm.trigger("set_posting_date_read_only");
	},

	pos_profile: (frm) => {
		if (frm.doc.pos_profile) {
			frappe.db.get_doc("POS Profile", frm.doc.pos_profile).then(({ payments }) => {
				if (payments.length) {
					frm.doc.balance_details = [];
					payments.forEach(({ mode_of_payment }) => {
						frm.add_child("balance_details", { mode_of_payment });
					});
					frm.refresh_field("balance_details");
				}
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
