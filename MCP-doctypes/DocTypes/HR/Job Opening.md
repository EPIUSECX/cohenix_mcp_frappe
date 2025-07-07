# Master Control Plan: `Job Opening`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `HR-OPN-.YYYY.-.####`
- **Description:** Description of a Job Opening

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `job_details_section` | None | Section Break | None |  |  |  | None | None |
| `job_title` | Job Title | Data | None | ✅ |  |  | None | None |
| `designation` | Designation | Link | Designation | ✅ |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | Open
Closed |  |  |  | None | None |
| `posted_on` | Posted On | Datetime | None |  |  |  | Now | None |
| `closes_on` | Closes On | Date | None |  |  |  | None | If set, the job opening will be closed automatically after this date |
| `closed_on` | Closed On | Date | None |  |  |  | None | None |
| `section_break_nngy` | Company Details | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `column_break_dxpv` | None | Column Break | None |  |  |  | None | None |
| `employment_type` | Employment Type | Link | Employment Type |  |  |  | None | None |
| `location` | Location | Link | Branch |  |  |  | None | None |
| `references_section` | References | Section Break | None |  |  |  | None | None |
| `staffing_plan` | Staffing Plan | Link | Staffing Plan |  |  | ✅ | None | None |
| `planned_vacancies` | Planned number of Positions | Int | None |  |  | ✅ | None | None |
| `job_requisition` | Job Requisition | Link | Job Requisition |  |  | ✅ | None | None |
| `vacancies` | Vacancies | Int | None |  |  | ✅ | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `publish` | Publish on website | Check | None |  |  |  | 0 | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `publish_applications_received` | Publish Applications Received | Check | None |  |  |  | 1 | If enabled, the total no. of applications received for this opening will be displayed on the website |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `job_application_route` | Job Application Route | Data | None |  |  |  | None | Route to the custom Job Application Webform |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | Job profile, qualifications required etc. |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `lower_range` | Lower Range | Currency | currency |  |  |  | None | None |
| `upper_range` | Upper Range | Currency | currency |  |  |  | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `salary_per` | Salary Paid Per | Select | Month
Year |  |  |  | Month | None |
| `publish_salary_range` | Publish Salary Range | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/job_opening/job_opening.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Job Opening", {
	onload: function (frm) {
		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},
	designation: function (frm) {
		if (frm.doc.designation && frm.doc.company) {
			frappe.call({
				method: "hrms.hr.doctype.staffing_plan.staffing_plan.get_active_staffing_plan_details",
				args: {
					company: frm.doc.company,
					designation: frm.doc.designation,
					date: frappe.datetime.now_date(), // ToDo - Date in Job Opening?
				},
				callback: function (data) {
					if (data.message) {
						frm.set_value("staffing_plan", data.message[0].name);
						frm.set_value("planned_vacancies", data.message[0].vacancies);
					} else {
						frm.set_value("staffing_plan", "");
						frm.set_value("planned_vacancies", 0);
						frappe.show_alert({
							indicator: "orange",
							message: __("No Staffing Plans found for this Designation"),
						});
					}
				},
			});
		} else {
			frm.set_value("staffing_plan", "");
			frm.set_value("planned_vacancies", 0);
		}
	},
	company: function (frm) {
		frm.set_value("designation", "");
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
| `Department Wise Openings` | Department Wise Openings | Group By | HR |
| `Designation Wise Openings` | Designation Wise Openings | Group By | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Job Openings` | Job Openings | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
