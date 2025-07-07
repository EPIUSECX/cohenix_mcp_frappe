# Master Control Plan: `BOM Update Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `BOM-UPDT-LOG-.#####`
- **Description:** BOM Update Tool Log with job status maintained

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing Manager | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `update_type` | Update Type | Select | Replace BOM
Update Cost |  |  |  | None | None |
| `status` | Status | Select | Queued
In Progress
Completed
Failed |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `current_bom` | Current BOM | Link | BOM |  |  |  | None | None |
| `new_bom` | New BOM | Link | BOM |  |  |  | None | None |
| `error_log` | Error Log | Link | Error Log |  |  |  | None | None |
| `progress_section` | Progress | Section Break | None |  |  |  | None | None |
| `current_level` | Current Level | Int | None |  |  |  | None | None |
| `processed_boms` | Processed BOMs | Long Text | None |  | ✅ |  | None | None |
| `bom_batches` | None | Table | BOM Update Batch |  |  |  | None | None |
| `amended_from` | Amended From | Link | BOM Update Log |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/bom_update_log/bom_update_log.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("BOM Update Log", {
	// refresh: function(frm) {
	// }
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
