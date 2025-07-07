# Master Control Plan: `Process Payment Reconciliation Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:PPR-LOG-{##}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `process_pr` | Parent Document | Link | Process Payment Reconciliation | ✅ |  | ✅ | None | None |
| `section_break_fvdw` | Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | Running
Paused
Reconciled
Partially Reconciled
Failed
Cancelled |  |  | ✅ | None | None |
| `tasks_section` | Tasks | Section Break | None |  |  |  | None | None |
| `allocated` | Allocated | Check | None |  |  | ✅ | 0 | Invoices and Payments have been Fetched and Allocated |
| `reconciled` | Reconciled | Check | None |  |  | ✅ | 0 | All allocations have been successfully reconciled |
| `column_break_yhin` | None | Column Break | None |  |  |  | None | None |
| `total_allocations` | Total Allocations | Int | None |  |  | ✅ | None | None |
| `reconciled_entries` | Reconciled Entries | Int | None |  |  | ✅ | None | None |
| `section_break_4ywv` | None | Section Break | None |  |  |  | None | None |
| `error_log` | Reconciliation Error Log | Long Text | None |  |  | ✅ | None | None |
| `allocations_section` | Allocations | Section Break | None |  |  |  | None | None |
| `allocations` | Allocations | Table | Process Payment Reconciliation Log Allocations |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_payment_reconciliation_log/process_payment_reconciliation_log.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Process Payment Reconciliation Log", {
	refresh(frm) {
		if (["Completed", "Running", "Paused", "Partially Reconciled"].find((x) => x == frm.doc.status)) {
			let progress = 0;
			if (frm.doc.reconciled_entries != 0) {
				progress = (frm.doc.reconciled_entries / frm.doc.total_allocations) * 100;
			} else if (frm.doc.total_allocations == 0 && frm.doc.status == "Completed") {
				progress = 100;
			}
			frm.dashboard.add_progress(__("Reconciliation Progress"), progress);
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
