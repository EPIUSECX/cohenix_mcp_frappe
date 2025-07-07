# Master Control Plan: `Bulk Transaction Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Bulk Transaction`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `date` | Date | Date | None |  |  | ✅ | None | None |
| `column_break_bsan` | None | Column Break | None |  |  |  | None | None |
| `log_entries` | Log Entries | Int | None |  |  | ✅ | None | None |
| `section_break_mdmv` | None | Section Break | None |  |  |  | None | None |
| `succeeded` | Succeeded | Int | None |  |  | ✅ | None | None |
| `column_break_qryp` | None | Column Break | None |  |  |  | None | None |
| `failed` | Failed | Int | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/bulk_transaction/doctype/bulk_transaction_log/bulk_transaction_log.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bulk Transaction Log", {
	refresh(frm) {
		frm.add_custom_button(
			__("Succeeded Entries"),
			function () {
				frappe.set_route("List", "Bulk Transaction Log Detail", {
					date: frm.doc.date,
					transaction_status: "Success",
				});
			},
			__("View")
		);
		frm.add_custom_button(
			__("Failed Entries"),
			function () {
				frappe.set_route("List", "Bulk Transaction Log Detail", {
					date: frm.doc.date,
					transaction_status: "Failed",
				});
			},
			__("View")
		);
		if (frm.doc.failed) {
			frm.add_custom_button(__("Retry Failed Transactions"), function () {
				frappe.call({
					method: "erpnext.utilities.bulk_transaction.retry",
					args: { date: frm.doc.date },
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
