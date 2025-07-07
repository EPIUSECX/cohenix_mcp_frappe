# Master Control Plan: `Employee Performance Feedback`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `format:HR-PF-{YYYY}-{#####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_details_tab` | Employee Details | Tab Break | None |  |  |  | None | None |
| `employee` | For Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `reviewer` | Reviewer | Link | Employee | ✅ |  |  | None | None |
| `reviewer_name` | Reviewer Name | Data | None |  |  | ✅ | None | None |
| `reviewer_designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `user` | User | Link | User |  |  | ✅ | None | None |
| `column_break_f0bz` | None | Column Break | None |  |  |  | None | None |
| `added_on` | Added On | Datetime | None | ✅ |  |  | Now | None |
| `appraisal_cycle` | Appraisal Cycle | Link | Appraisal Cycle |  |  | ✅ | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `appraisal` | Appraisal | Link | Appraisal | ✅ |  |  | None | None |
| `feedback_ratings` | Feedback Ratings | Table | Employee Feedback Rating |  |  |  | None | None |
| `total_score` | Total Score | Float | None |  |  | ✅ | None | None |
| `feedback_tab` | Feedback | Tab Break | Feedback |  |  |  | None | None |
| `feedback` | None | Text Editor | None | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Performance Feedback |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_performance_feedback/employee_performance_feedback.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Performance Feedback", {
	onload(frm) {
		frm.trigger("set_reviewer");
	},

	refresh(frm) {
		frm.trigger("set_filters");
	},

	employee(frm) {
		frm.set_value("appraisal", "");
	},

	appraisal(frm) {
		if (frm.doc.employee) {
			frm.call("set_feedback_criteria", () => {
				frm.refresh_field("feedback_ratings");
			});
		}
	},

	set_filters(frm) {
		frm.set_query("appraisal", () => {
			return {
				filters: {
					employee: frm.doc.employee,
				},
			};
		});

		frm.set_query("reviewer", () => {
			return {
				filters: {
					employee: ["!=", frm.doc.employee],
				},
			};
		});
	},

	set_reviewer(frm) {
		if (!frm.doc.reviewer) {
			frappe.db
				.get_value("Employee", { user_id: frappe.session.user }, "name")
				.then((employee_record) => {
					const session_employee = employee_record?.message?.name;
					if (session_employee) frm.set_value("reviewer", session_employee);
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
