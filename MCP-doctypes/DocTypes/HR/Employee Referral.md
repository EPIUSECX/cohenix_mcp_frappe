# Master Control Plan: `Employee Referral`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `format:HR-REF-{####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `first_name` | First Name  | Data | None | ✅ |  |  | None | None |
| `last_name` | Last Name | Data | None | ✅ |  |  | None | None |
| `full_name` | Full Name | Data | None |  |  | ✅ | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `date` | Date | Date | None | ✅ |  |  | None | None |
| `status` | Status | Select | Pending
In Process
Accepted
Rejected | ✅ |  | ✅ | None | None |
| `for_designation` | For Designation  | Link | Designation | ✅ |  |  | None | None |
| `referral_details_section` | Referral Details | Section Break | None |  |  |  | None | None |
| `email` | Email | Data | Email | ✅ |  |  | None | None |
| `contact_no` | Contact No. | Data | Phone |  |  |  | None | None |
| `resume_link` | Resume Link | Data | None |  |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `current_employer` | Current Employer  | Data | None |  |  |  | None | None |
| `current_job_title` | Current Job Title | Data | None |  |  |  | None | None |
| `resume` | Resume | Attach | None |  |  |  | None | None |
| `referrer_details_section` | Referrer Details | Section Break | None |  |  |  | None | None |
| `referrer` | Referrer | Link | Employee | ✅ |  |  | None | None |
| `referrer_name` | Referrer Name | Data | None |  |  | ✅ | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `is_applicable_for_referral_bonus` | Is Applicable for Referral Bonus | Check | None |  |  |  | 1 | None |
| `referral_payment_status` | Referral Bonus Payment Status | Select | 
Unpaid
Paid |  |  | ✅ | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `additional_information_section` | Additional Information  | Section Break | None |  |  |  | None | None |
| `qualification_reason` | Why is this Candidate Qualified for this Position? | Text Editor | None |  |  |  | None | None |
| `work_references` | Work References | Text Editor | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Employee Referral |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_referral/employee_referral.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Employee Referral", {
	refresh: function (frm) {
		if (frm.doc.docstatus === 1 && frm.doc.status === "Pending") {
			frm.add_custom_button(__("Reject Employee Referral"), function () {
				frappe.confirm(
					__("Are you sure you want to reject the Employee Referral?"),
					function () {
						frm.doc.status = "Rejected";
						frm.dirty();
						frm.save_or_update();
					},
					function () {
						window.close();
					},
				);
			});

			frm.add_custom_button(__("Create Job Applicant"), function () {
				frm.events.create_job_applicant(frm);
			}).addClass("btn-primary");
		}

		// To check whether Payment is done or not
		if (frm.doc.docstatus === 1 && frm.doc.status === "Accepted") {
			frappe.db
				.get_list("Additional Salary", {
					filters: {
						ref_docname: cur_frm.doc.name,
						docstatus: 1,
					},
					fields: ["count(name) as additional_salary_count"],
				})
				.then((data) => {
					let additional_salary_count = data[0].additional_salary_count;

					if (frm.doc.is_applicable_for_referral_bonus && !additional_salary_count) {
						frm.add_custom_button(__("Create Additional Salary"), function () {
							frm.events.create_additional_salary(frm);
						}).addClass("btn-primary");
					}
				});
		}
	},
	create_job_applicant: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.employee_referral.employee_referral.create_job_applicant",
			args: {
				source_name: frm.docname,
			},
		});
	},

	create_additional_salary: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.employee_referral.employee_referral.create_additional_salary",
			args: {
				doc: frm.doc,
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
