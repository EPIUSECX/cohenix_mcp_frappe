# Master Control Plan: `Process Deferred Accounting`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `ACC-PDA-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `type` | Type | Select | 
Income
Expense | ✅ |  |  | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None | ✅ |  |  | Today | None |
| `start_date` | Service Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | Service End Date | Date | None | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Process Deferred Accounting |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_deferred_accounting/process_deferred_accounting.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Process Deferred Accounting", {
	setup: function (frm) {
		frm.set_query("document_type", function () {
			return {
				filters: {
					name: ["in", ["Sales Invoice", "Purchase Invoice"]],
				},
			};
		});
	},

	type: function (frm) {
		if (frm.doc.company && frm.doc.type) {
			frm.set_query("account", function () {
				return {
					filters: {
						company: frm.doc.company,
						root_type: frm.doc.type === "Income" ? "Liability" : "Asset",
						is_group: 0,
					},
				};
			});
		}
	},

	validate: function () {
		return new Promise((resolve) => {
			return frappe.db
				.get_single_value("Accounts Settings", "automatically_process_deferred_accounting_entry")
				.then((value) => {
					if (value) {
						frappe.throw(
							__(
								"Manual entry cannot be created! Disable automatic entry for deferred accounting in accounts settings and try again"
							)
						);
					}
					resolve(value);
				});
		});
	},

	end_date: function (frm) {
		if (frm.doc.end_date && frm.doc.end_date < frm.doc.start_date) {
			frappe.throw(__("End date cannot be before start date"));
		}
	},

	onload: function (frm) {
		if (frm.doc.posting_date && frm.doc.docstatus === 0) {
			frm.set_value("start_date", frappe.datetime.add_months(frm.doc.posting_date, -1));
			frm.set_value("end_date", frm.doc.posting_date);
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
