# Master Control Plan: `Training Event`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `field:event_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `event_name` | Event Name | Data | None | ✅ |  |  | None | None |
| `training_program` | Training Program | Link | Training Program |  |  |  | None | None |
| `event_status` | Event Status | Select | Scheduled
Completed
Cancelled | ✅ |  |  | None | None |
| `has_certificate` | Has Certificate | Check | None |  |  |  | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `type` | Type | Select | Seminar
Theory
Workshop
Conference
Exam
Internet
Self-Study | ✅ |  |  | None | None |
| `level` | Level | Select | 
Beginner
Intermediate
Advance |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `trainer_name` | Trainer Name | Data | None |  |  |  | None | None |
| `trainer_email` | Trainer Email | Data | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `contact_number` | Contact Number | Data | None |  |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `course` | Course | Data | None |  |  |  | None | None |
| `location` | Location | Data | None | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `start_time` | Start Time | Datetime | None | ✅ |  |  | None | None |
| `end_time` | End Time | Datetime | None | ✅ |  |  | None | None |
| `section_break_15` | None | Section Break | None |  |  |  | None | None |
| `introduction` | Introduction | Text Editor | None | ✅ |  |  | None | None |
| `section_break_18` | Attendees | Section Break | None |  |  |  | None | None |
| `employees` | Employees | Table | Training Event Employee |  |  |  | None | None |
| `amended_from` | Amended From | Link | Training Event |  |  | ✅ | None | None |
| `employee_emails` | Employee Emails | Small Text | Email |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/training_event/training_event.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Training Event", {
	onload_post_render: function (frm) {
		frm.get_field("employees").grid.set_multiple_add("employee");
	},
	refresh: function (frm) {
		if (!frm.doc.__islocal) {
			frm.add_custom_button(__("Training Result"), function () {
				frappe.route_options = {
					training_event: frm.doc.name,
				};
				frappe.set_route("List", "Training Result");
			});
			frm.add_custom_button(__("Training Feedback"), function () {
				frappe.route_options = {
					training_event: frm.doc.name,
				};
				frappe.set_route("List", "Training Feedback");
			});
		}
		frm.events.set_employee_query(frm);
	},

	set_employee_query: function (frm) {
		let emp = [];
		for (let d in frm.doc.employees) {
			if (frm.doc.employees[d].employee) {
				emp.push(frm.doc.employees[d].employee);
			}
		}
		frm.set_query("employee", "employees", function () {
			return {
				filters: {
					name: ["NOT IN", emp],
					status: "Active",
				},
			};
		});
	},
});

frappe.ui.form.on("Training Event Employee", {
	employee: function (frm) {
		frm.events.set_employee_query(frm);
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Training Type` | Training Type | Group By | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Trainings (This Month)` | Trainings (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
| Name | Event | Channel | Subject |
|---|---|---|---|
| `Training Scheduled` | Submit | Email | Training Scheduled: {{ doc.name }} |



### Webhooks
No enabled webhooks found.
