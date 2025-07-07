# Master Control Plan: `Stock Closing Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Naming Series | Select | CBAL-.##### |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `status` | Status | Select | Draft
Queued
In Progress
Completed
Failed
Canceled |  |  | ✅ | Draft | None |
| `column_break_p0s0` | None | Column Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Stock Closing Entry |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_closing_entry/stock_closing_entry.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Stock Closing Entry", {
	refresh(frm) {
		frm.trigger("generate_closing_balance");
		frm.trigger("regenerate_closing_balance");
	},

	generate_closing_balance(frm) {
		if (["Queued", "Failed"].includes(frm.doc.status)) {
			frm.add_custom_button(__("Generate Stock Closing Entry"), () => {
				frm.call({
					method: "enqueue_job",
					doc: frm.doc,
					freeze: true,
					callback: () => {
						frm.reload_doc();
					},
				});
			});
		}
	},

	regenerate_closing_balance(frm) {
		if (frm.doc.status == "Completed") {
			frm.add_custom_button(__("Regenerate Stock Closing Entry"), () => {
				frm.call({
					method: "regenerate_closing_balance",
					doc: frm.doc,
					freeze: true,
					callback: () => {
						frm.reload_doc();
					},
				});
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
