# Master Control Plan: `Asset Maintenance Log`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `asset_maintenance` | Asset Maintenance | Link | Asset Maintenance |  |  |  | None | None |
| `naming_series` | Series | Select | ACC-AML-.YYYY.- | ✅ |  |  | None | None |
| `asset_name` | Asset Name | Read Only | None |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `item_code` | Item Code | Read Only | None |  |  |  | None | None |
| `item_name` | Item Name | Read Only | None |  |  |  | None | None |
| `section_break_5` | Maintenance Details | Section Break | None |  |  |  | None | None |
| `task` | Task | Link | Asset Maintenance Task |  |  |  | None | None |
| `task_name` | Task Name | Data | None |  |  | ✅ | None | None |
| `maintenance_type` | Maintenance Type | Read Only | None |  |  |  | None | None |
| `periodicity` | Periodicity | Data | None |  |  | ✅ | None | None |
| `has_certificate` | Has Certificate  | Check | None |  |  |  | 0 | None |
| `certificate_attachement` | Certificate | Attach | None |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `maintenance_status` | Maintenance Status | Select | Planned
Completed
Cancelled
Overdue | ✅ |  |  | None | None |
| `assign_to_name` | Assign To | Read Only | None |  |  |  | None | None |
| `task_assignee_email` | Task Assignee Email | Data | None |  |  | ✅ | None | None |
| `due_date` | Due Date | Date | None |  |  | ✅ | None | None |
| `completion_date` | Completion Date | Date | None |  |  |  | None | None |
| `description` | Description | Read Only | None |  |  | ✅ | None | None |
| `column_break_9` | None | Section Break | None |  |  |  | None | None |
| `actions_performed` | Actions performed | Text Editor | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Asset Maintenance Log |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_maintenance_log/asset_maintenance_log.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Asset Maintenance Log", {
	asset_maintenance: (frm) => {
		frm.set_query("task", function (doc) {
			return {
				query: "erpnext.assets.doctype.asset_maintenance_log.asset_maintenance_log.get_maintenance_tasks",
				filters: {
					asset_maintenance: doc.asset_maintenance,
				},
			};
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
