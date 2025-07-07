# Master Control Plan: `Employee Skill Map`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:employee`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee |  |  |  | None | None |
| `employee_name` | Employee Name | Read Only | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `designation` | Designation | Read Only | None |  |  |  | None | None |
| `skills_section` | Skills | Section Break | None |  |  |  | None | None |
| `employee_skills` | Employee Skills | Table | Employee Skill |  |  |  | None | None |
| `trainings_section` | Trainings | Section Break | None |  |  |  | None | None |
| `trainings` | Trainings | Table | Employee Training |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_skill_map/employee_skill_map.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Skill Map", {
	// refresh: function(frm) {

	// }
	designation: (frm) => {
		frm.set_value("employee_skills", null);
		if (frm.doc.designation) {
			frappe.db.get_doc("Designation", frm.doc.designation).then((designation) => {
				designation.skills.forEach((designation_skill) => {
					let row = frappe.model.add_child(frm.doc, "Employee Skill", "employee_skills");
					row.skill = designation_skill.skill;
					row.proficiency = 1;
				});
				refresh_field("employee_skills");
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
