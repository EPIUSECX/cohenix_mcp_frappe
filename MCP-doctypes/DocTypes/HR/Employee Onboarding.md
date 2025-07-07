# Master Control Plan: `Employee Onboarding`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-EMP-ONB-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `job_applicant` | Job Applicant | Link | Job Applicant | ✅ |  |  | None | None |
| `job_offer` | Job Offer | Link | Job Offer | ✅ |  |  | None | None |
| `employee_onboarding_template` | Employee Onboarding Template | Link | Employee Onboarding Template |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `boarding_status` | Status | Select | Pending
In Process
Completed |  |  | ✅ | Pending | None |
| `project` | Project | Link | Project |  |  | ✅ | None | None |
| `details_section` | Employee Details | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Link | Employee |  |  | ✅ | None | None |
| `employee_name` | Employee Name | Data | None | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `employee_grade` | Employee Grade | Link | Employee Grade |  |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `date_of_joining` | Date of Joining | Date | None | ✅ |  |  | None | None |
| `boarding_begins_on` | Onboarding Begins On | Date | None | ✅ |  |  | None | None |
| `table_for_activity` | Onboarding Activities | Section Break | None |  |  |  | None | None |
| `activities` | Activities | Table | Employee Boarding Activity |  |  |  | None | None |
| `notify_users_by_email` | Notify users by email | Check | None |  |  |  | 0 | None |
| `amended_from` | Amended From | Link | Employee Onboarding |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 11
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_onboarding/employee_onboarding.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Onboarding", {
	setup: function (frm) {
		frm.set_query("job_applicant", function () {
			return {
				filters: {
					status: "Accepted",
				},
			};
		});

		frm.set_query("job_offer", function () {
			return {
				filters: {
					job_applicant: frm.doc.job_applicant,
					docstatus: 1,
				},
			};
		});
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
		if (!frm.doc.employee && frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Employee"),
				function () {
					frappe.model.open_mapped_doc({
						method: "hrms.hr.doctype.employee_onboarding.employee_onboarding.make_employee",
						frm: frm,
					});
				},
				__("Create"),
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}
		if (
			frm.doc.docstatus === 1 &&
			(frm.doc.boarding_status === "Pending" || frm.doc.boarding_status === "In Process")
		) {
			frm.add_custom_button(__("Mark as Completed"), function () {
				frm.trigger("mark_as_completed");
			});
		}
	},

	employee_onboarding_template: function (frm) {
		frm.set_value("activities", "");
		if (frm.doc.employee_onboarding_template) {
			frappe.call({
				method: "hrms.controllers.employee_boarding_controller.get_onboarding_details",
				args: {
					parent: frm.doc.employee_onboarding_template,
					parenttype: "Employee Onboarding Template",
				},
				callback: function (r) {
					if (r.message) {
						r.message.forEach((d) => {
							frm.add_child("activities", d);
						});
						refresh_field("activities");
					}
				},
			});
		}
	},

	job_applicant: function (frm) {
		if (frm.doc.job_applicant) {
			frappe.db.get_value(
				"Employee",
				{ job_applicant: frm.doc.job_applicant },
				"name",
				(r) => {
					if (r.name) {
						frm.set_value("employee", r.name);
					} else {
						frm.set_value("employee", "");
					}
				},
			);
		} else {
			frm.set_value("employee", "");
		}
	},

	mark_as_completed(frm) {
		frm.call({
			method: "mark_onboarding_as_completed",
			doc: frm.doc,
			freeze: true,
			freeze_message: __("Completing onboarding"),
		}).then((r) => {
			frm.refresh();
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
| Name | Label | Function | Module |
|---|---|---|---|
| `Onboardings (This Month)` | Onboardings (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
