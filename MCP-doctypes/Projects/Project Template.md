# Master Control Plan: `Project Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `project_type` | Project Type | Link | Project Type |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `tasks` | Tasks | Table | Project Template Task | ✅ |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/project_template/project_template.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Project Template", {
	// refresh: function(frm) {

	// }
	setup: function (frm) {
		frm.set_query("task", "tasks", function () {
			return {
				filters: {
					is_template: 1,
				},
			};
		});
	},
});

frappe.ui.form.on("Project Template Task", {
	task: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		frappe.db.get_value("Task", row.task, "subject", (value) => {
			row.subject = value.subject;
			refresh_field("tasks");
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
