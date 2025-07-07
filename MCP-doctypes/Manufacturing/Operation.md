# Master Control Plan: `Operation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ |
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `workstation` | Default Workstation | Link | Workstation |  |  |  | None | None |
| `data_2` | None | Column Break | None |  |  |  | None | None |
| `is_corrective_operation` | Is Corrective Operation | Check | None |  |  |  | 0 | None |
| `job_card_section` | Job Card | Section Break | None |  |  |  | None | None |
| `create_job_card_based_on_batch_size` | Create Job Card based on Batch Size | Check | None |  |  |  | 0 | None |
| `quality_inspection_template` | Quality Inspection Template | Link | Quality Inspection Template |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `batch_size` | Batch Size | Int | None |  |  |  | 1 | None |
| `sub_operations_section` | Sub Operations | Section Break | None |  |  |  | None | None |
| `sub_operations` | None | Table | Sub Operation |  |  |  | None | None |
| `total_operation_time` | Total Operation Time | Float | None |  |  | ✅ | None | Time in mins. |
| `section_break_4` | Operation Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/operation/operation.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Operation", {
	setup: function (frm) {
		frm.set_query("operation", "sub_operations", function () {
			return {
				filters: {
					name: ["not in", [frm.doc.name]],
				},
			};
		});
	},
});

frappe.tour["Operation"] = [
	{
		fieldname: "__newname",
		title: "Operation Name",
		description: __("Enter a name for the Operation, for example, Cutting."),
	},
	{
		fieldname: "workstation",
		title: "Default Workstation",
		description: __(
			"Select the Default Workstation where the Operation will be performed. This will be fetched in BOMs and Work Orders."
		),
	},
	{
		fieldname: "sub_operations",
		title: "Sub Operations",
		description: __("If an operation is divided into sub operations, they can be added here."),
	},
];

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
