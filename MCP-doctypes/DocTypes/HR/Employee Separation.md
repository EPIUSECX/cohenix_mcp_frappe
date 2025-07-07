# Master Control Plan: `Employee Separation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-EMP-SEP-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `employee_grade` | Employee Grade | Link | Employee Grade |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `boarding_status` | Status | Select | Pending
In Process
Completed |  |  | ✅ | Pending | None |
| `resignation_letter_date` | Resignation Letter Date | Date | None |  |  | ✅ | None | None |
| `boarding_begins_on` | Separation Begins On | Date | None | ✅ |  |  | None | None |
| `project` | Project | Link | Project |  |  | ✅ | None | None |
| `table_for_activity` | Separation Activities | Section Break | None |  |  |  | None | None |
| `employee_separation_template` | Employee Separation Template | Link | Employee Separation Template |  |  |  | None | None |
| `activities` | Activities | Table | Employee Boarding Activity |  |  |  | None | None |
| `notify_users_by_email` | Notify users by email | Check | None |  |  |  | 0 | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `exit_interview` | Exit Interview Summary | Text Editor | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Separation |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_separation/employee_separation.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Separation", {
	setup: function (frm) {
		frm.add_fetch("employee_separation_template", "company", "company");
		frm.add_fetch("employee_separation_template", "department", "department");
		frm.add_fetch("employee_separation_template", "designation", "designation");
		frm.add_fetch("employee_separation_template", "employee_grade", "employee_grade");
	},

	refresh: function (frm) {
		if (frm.doc.employee) {
			frm.add_custom_button(
				__("Employee"),
				function () {
					frappe.set_route("Form", "Employee", frm.doc.employee);
				},
				__("View"),
			);
		}
		if (frm.doc.project) {
			frm.add_custom_button(
				__("Project"),
				function () {
					frappe.set_route("Form", "Project", frm.doc.project);
				},
				__("View"),
			);
			frm.add_custom_button(
				__("Task"),
				function () {
					frappe.set_route("List", "Task", { project: frm.doc.project });
				},
				__("View"),
			);
		}
	},

	employee_separation_template: function (frm) {
		frm.set_value("activities", "");
		if (frm.doc.employee_separation_template) {
			frappe.call({
				method: "hrms.controllers.employee_boarding_controller.get_onboarding_details",
				args: {
					parent: frm.doc.employee_separation_template,
					parenttype: "Employee Separation Template",
				},
				callback: function (r) {
					if (r.message) {
						$.each(r.message, function (i, d) {
							var row = frappe.model.add_child(
								frm.doc,
								"Employee Boarding Activity",
								"activities",
							);
							$.extend(row, d);
						});
					}
					refresh_field("activities");
				},
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
| Name | Label | Function | Module |
|---|---|---|---|
| `Separations (This Month)` | Separations (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
