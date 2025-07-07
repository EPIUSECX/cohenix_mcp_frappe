# Master Control Plan: `Job Applicant`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `HR-APP-.YYYY.-.#####`
- **Description:** Applicant for a Job

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details_section` | Details | Section Break | None |  |  |  | None | None |
| `applicant_name` | Applicant Name | Data | None | ✅ |  |  | None | None |
| `email_id` | Email Address | Data | Email | ✅ |  |  | None | None |
| `phone_number` | Phone Number | Data | Phone |  |  |  | None | None |
| `country` | Country | Link | Country |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `job_title` | Job Opening | Link | Job Opening |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `status` | Status | Select | Open
Replied
Rejected
Hold
Accepted | ✅ |  |  | None | None |
| `source_and_rating_section` | Source and Rating | Section Break | None |  |  |  | None | None |
| `source` | Source | Link | Job Applicant Source |  |  |  | None | None |
| `source_name` | Source Name | Link | Employee |  |  |  | None | None |
| `employee_referral` | Employee Referral | Link | Employee Referral |  |  | ✅ | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `applicant_rating` | Applicant Rating | Rating | None |  |  |  | None | None |
| `section_break_6` | Resume | Section Break | None |  |  |  | None | None |
| `notes` | Notes | Data | None |  |  | ✅ | None | None |
| `cover_letter` | Cover Letter | Text | None |  |  |  | None | None |
| `resume_attachment` | Resume Attachment | Attach | None |  |  |  | None | None |
| `resume_link` | Resume Link | Data | None |  |  |  | None | None |
| `section_break_16` | Salary Expectation | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `lower_range` | Lower Range | Currency | currency |  |  |  | None | None |
| `upper_range` | Upper Range | Currency | currency |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/job_applicant/job_applicant.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

// For license information, please see license.txt

// for communication
cur_frm.email_field = "email_id";

frappe.ui.form.on("Job Applicant", {
	refresh: function (frm) {
		frm.set_query("job_title", function () {
			return {
				filters: {
					status: "Open",
				},
			};
		});
		frm.events.create_custom_buttons(frm);
		frm.events.make_dashboard(frm);
	},

	create_custom_buttons: function (frm) {
		if (!frm.doc.__islocal && frm.doc.status !== "Rejected" && frm.doc.status !== "Accepted") {
			frm.add_custom_button(
				__("Interview"),
				function () {
					frm.events.create_dialog(frm);
				},
				__("Create"),
			);
		}

		if (!frm.doc.__islocal && frm.doc.status == "Accepted") {
			if (frm.doc.__onload && frm.doc.__onload.job_offer) {
				$('[data-doctype="Employee Onboarding"]').find("button").show();
				$('[data-doctype="Job Offer"]').find("button").hide();
				frm.add_custom_button(
					__("Job Offer"),
					function () {
						frappe.set_route("Form", "Job Offer", frm.doc.__onload.job_offer);
					},
					__("View"),
				);
			} else {
				$('[data-doctype="Employee Onboarding"]').find("button").hide();
				$('[data-doctype="Job Offer"]').find("button").show();
				frm.add_custom_button(
					__("Job Offer"),
					function () {
						frappe.route_options = {
							job_applicant: frm.doc.name,
							applicant_name: frm.doc.applicant_name,
							designation: frm.doc.job_opening || frm.doc.designation,
						};
						frappe.new_doc("Job Offer");
					},
					__("Create"),
				);
			}
		}
	},

	make_dashboard: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.job_applicant.job_applicant.get_interview_details",
			args: {
				job_applicant: frm.doc.name,
			},
			callback: function (r) {
				if (r.message) {
					$("div").remove(".form-dashboard-section.custom");
					frm.dashboard.add_section(
						frappe.render_template("job_applicant_dashboard", {
							data: r.message.interviews,
							number_of_stars: r.message.stars,
						}),
						__("Interview Summary"),
					);
				}
			},
		});
	},

	create_dialog: function (frm) {
		let d = new frappe.ui.Dialog({
			title: "Enter Interview Round",
			fields: [
				{
					label: "Interview Round",
					fieldname: "interview_round",
					fieldtype: "Link",
					options: "Interview Round",
				},
			],
			primary_action_label: __("Create Interview"),
			primary_action(values) {
				frm.events.create_interview(frm, values);
				d.hide();
			},
		});
		d.show();
	},

	create_interview: function (frm, values) {
		frappe.call({
			method: "hrms.hr.doctype.job_applicant.job_applicant.create_interview",
			args: {
				doc: frm.doc,
				interview_round: values.interview_round,
			},
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
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
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Job Applicants by Country` | Job Applicants by Country | Group By | HR |
| `Job Applicant Source` | Job Applicant Source | Group By | HR |
| `Job Application Frequency` | Job Application Frequency | Count | HR |
| `Job Applicant Pipeline` | Job Applicant Pipeline | Group By | HR |
| `Job Application Status` | Job Application Status | Group By | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Rejected Job Applicants` | Rejected Job Applicants | Count | HR |
| `Accepted Job Applicants` | Accepted Job Applicants | Count | HR |
| `Total Applicants (This month)` | Total Applicants (This Month) | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
