# Master Control Plan: `Employee`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Setup`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `basic_details_tab` | Overview | Tab Break | None |  |  |  | None | None |
| `basic_information` | None | Section Break | None |  |  |  | None | None |
| `employee` | Employee | Data | None |  | ✅ |  | None | None |
| `naming_series` | Series | Select | HR-EMP- | ✅ |  |  | None | None |
| `first_name` | First Name | Data | None | ✅ |  |  | None | None |
| `middle_name` | Middle Name | Data | None |  |  |  | None | None |
| `last_name` | Last Name | Data | None |  |  |  | None | None |
| `employee_name` | Full Name | Data | None |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `gender` | Gender | Link | Gender | ✅ |  |  | None | None |
| `date_of_birth` | Date of Birth | Date | None | ✅ |  |  | None | None |
| `salutation` | Salutation | Link | Salutation |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `date_of_joining` | Date of Joining | Date | None | ✅ |  |  | None | None |
| `image` | Image | Attach Image | None |  | ✅ |  | None | None |
| `status` | Status | Select | Active
Inactive
Suspended
Left | ✅ |  |  | Active | None |
| `erpnext_user` | User Details | Section Break | None |  |  |  | None | None |
| `user_id` | User ID | Link | User |  |  |  | None | System User (login) ID. If set, it will become default for all HR forms. |
| `create_user` | Create User | Button | None |  |  |  | None | None |
| `create_user_permission` | Create User Permission | Check | None |  |  |  | 1 | This will restrict user access to other employee records |
| `company_details_section` | Company Details | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `department` | Department | Link | Department |  |  |  | None | None |
| `employment_type` | Employment Type | Link | Employment Type |  |  |  | None | None |
| `employee_number` | Employee Number | Data | None |  | ✅ |  | None | None |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `reports_to` | Reports to | Link | Employee |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `branch` | Branch | Link | Branch |  |  |  | None | None |
| `grade` | Grade | Link | Employee Grade |  |  |  | None | None |
| `employment_details` | Joining | Tab Break | None |  |  |  | None | None |
| `job_applicant` | Job Applicant | Link | Job Applicant |  |  |  | None | None |
| `scheduled_confirmation_date` | Offer Date | Date | None |  |  |  | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `final_confirmation_date` | Confirmation Date | Date | None |  |  |  | None | None |
| `contract_end_date` | Contract End Date | Date | None |  |  |  | None | None |
| `col_break_22` | None | Column Break | None |  |  |  | None | None |
| `notice_number_of_days` | Notice (days) | Int | None |  |  |  | None | None |
| `date_of_retirement` | Date Of Retirement | Date | None |  |  |  | None | None |
| `contact_details` | Address & Contacts | Tab Break | None |  |  |  | None | None |
| `cell_number` | Mobile | Data | Phone |  |  |  | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `personal_email` | Personal Email | Data | Email |  |  |  | None | None |
| `company_email` | Company Email | Data | Email |  |  |  | None | Provide Email Address registered in company |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `prefered_contact_email` | Preferred Contact Email | Select | 
Company Email
Personal Email
User ID |  |  |  | None | None |
| `prefered_email` | Preferred Email | Data | Email |  |  | ✅ | None | None |
| `unsubscribed` | Unsubscribed | Check | None |  |  |  | 0 | None |
| `address_section` | Address | Section Break | None |  |  |  | None | None |
| `current_address` | Current Address | Small Text | None |  |  |  | None | None |
| `current_accommodation_type` | Current Address Is | Select | 
Rented
Owned |  |  |  | None | None |
| `column_break_46` | None | Column Break | None |  |  |  | None | None |
| `permanent_address` | Permanent Address | Small Text | None |  |  |  | None | None |
| `permanent_accommodation_type` | Permanent Address Is | Select | 
Rented
Owned |  |  |  | None | None |
| `emergency_contact_details` | Emergency Contact | Section Break | None |  |  |  | None | None |
| `person_to_be_contacted` | Emergency Contact Name | Data | None |  |  |  | None | None |
| `column_break_55` | None | Column Break | None |  |  |  | None | None |
| `emergency_phone_number` | Emergency Phone | Data | Phone |  |  |  | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `relation` | Relation | Data | None |  |  |  | None | None |
| `attendance_and_leave_details` | Attendance & Leaves | Tab Break | None |  |  |  | None | None |
| `attendance_device_id` | Attendance Device ID (Biometric/RF tag ID) | Data | None |  |  |  | None | None |
| `column_break_44` | None | Column Break | None |  |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List |  |  |  | None | Applicable Holiday List |
| `default_shift` | Default Shift | Link | Shift Type |  |  |  | None | None |
| `approvers_section` | Approvers | Section Break | None |  |  |  | None | None |
| `expense_approver` | Expense Approver | Link | User |  |  |  | None | None |
| `leave_approver` | Leave Approver | Link | User |  |  |  | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `shift_request_approver` | Shift Request Approver | Link | User |  |  |  | None | None |
| `salary_information` | Salary | Tab Break | None |  |  |  | None | None |
| `ctc` | Cost to Company (CTC) | Currency | salary_currency |  |  |  | None | None |
| `salary_currency` | Salary Currency | Link | Currency |  |  |  | None | None |
| `salary_mode` | Salary Mode | Select | 
Bank
Cash
Cheque |  |  |  | None | None |
| `salary_cb` | None | Column Break | None |  |  |  | None | None |
| `payroll_cost_center` | Payroll Cost Center | Link | Cost Center |  |  |  | None | None |
| `bank_details_section` | Bank Details | Section Break | None |  |  |  | None | None |
| `bank_name` | Bank Name | Data | None |  |  |  | None | None |
| `column_break_heye` | None | Column Break | None |  |  |  | None | None |
| `bank_ac_no` | Bank A/C No. | Data | None |  |  |  | None | None |
| `iban` | IBAN | Data | None |  |  |  | None | None |
| `personal_details` | Personal Details | Tab Break | None |  |  |  | None | None |
| `marital_status` | Marital Status | Select | 
Single
Married
Divorced
Widowed |  |  |  | None | None |
| `family_background` | Family Background | Small Text | None |  |  |  | None | Here you can maintain family details like name and occupation of parent, spouse and children |
| `column_break6` | None | Column Break | None |  |  |  | None | None |
| `blood_group` | Blood Group | Select | 
A+
A-
B+
B-
AB+
AB-
O+
O- |  |  |  | None | None |
| `health_details` | Health Details | Small Text | None |  |  |  | None | Here you can maintain height, weight, allergies, medical concerns etc |
| `health_insurance_section` | Health Insurance | Section Break | None |  |  |  | None | None |
| `health_insurance_provider` | Health Insurance Provider | Link | Employee Health Insurance |  |  |  | None | None |
| `health_insurance_no` | Health Insurance No | Data | None |  |  |  | None | None |
| `passport_details_section` | Passport Details | Section Break | None |  |  |  | None | None |
| `passport_number` | Passport Number | Data | None |  |  |  | None | None |
| `valid_upto` | Valid Up To | Date | None |  |  |  | None | None |
| `column_break_73` | None | Column Break | None |  |  |  | None | None |
| `date_of_issue` | Date of Issue | Date | None |  |  |  | None | None |
| `place_of_issue` | Place of Issue | Data | None |  |  |  | None | None |
| `profile_tab` | Profile | Tab Break | None |  |  |  | None | None |
| `bio` | Bio / Cover Letter | Text Editor | None |  |  |  | None | Short biography for website and other publications. |
| `educational_qualification` | Educational Qualification | Section Break | None |  |  |  | None | None |
| `education` | Education | Table | Employee Education |  |  |  | None | None |
| `previous_work_experience` | Previous Work Experience | Section Break | Simple |  |  |  | None | None |
| `external_work_history` | External Work History | Table | Employee External Work History |  |  |  | None | None |
| `history_in_company` | History In Company | Section Break | Simple |  |  |  | None | None |
| `internal_work_history` | Internal Work History | Table | Employee Internal Work History |  |  |  | None | None |
| `exit` | Exit | Tab Break | None |  |  |  | None | None |
| `resignation_letter_date` | Resignation Letter Date | Date | None |  |  |  | None | None |
| `relieving_date` | Relieving Date | Date | None |  |  |  | None | None |
| `exit_interview_details` | None | Column Break | None |  |  |  | None | None |
| `held_on` | Exit Interview Held On | Date | None |  |  |  | None | None |
| `new_workplace` | New Workplace | Data | None |  |  |  | None | None |
| `column_break_99` | None | Column Break | None |  |  |  | None | None |
| `leave_encashed` | Leave Encashed? | Select | 
Yes
No |  |  |  | None | None |
| `encashment_date` | Encashment Date | Date | None |  |  |  | None | None |
| `feedback_section` | Feedback | Section Break | None |  |  |  | None | None |
| `reason_for_leaving` | Reason for Leaving | Small Text | None |  |  |  | None | None |
| `column_break_104` | None | Column Break | None |  |  |  | None | None |
| `feedback` | Feedback | Small Text | None |  |  |  | None | None |
| `lft` | lft | Int | None |  | ✅ | ✅ | None | None |
| `rgt` | rgt | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | Old Parent | Data | None |  | ✅ |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `payroll_cost_center` | Payroll Cost Center | Link | Cost Center |  |  |  | None | None |
| `salary_cb` | None | Column Break | None |  |  |  | None | None |
| `shift_request_approver` | Shift Request Approver | Link | User |  |  |  | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `leave_approver` | Leave Approver | Link | User |  |  |  | None | None |
| `expense_approver` | Expense Approver | Link | User |  |  |  | None | None |
| `approvers_section` | Approvers | Section Break | None |  |  |  | None | None |
| `health_insurance_no` | Health Insurance No | Data | None |  |  |  | None | None |
| `health_insurance_provider` | Health Insurance Provider | Link | Employee Health Insurance |  |  |  | None | None |
| `health_insurance_section` | Health Insurance | Section Break | None |  |  |  | None | None |
| `default_shift` | Default Shift | Link | Shift Type |  |  |  | None | None |
| `grade` | Grade | Link | Employee Grade |  |  |  | None | None |
| `job_applicant` | Job Applicant | Link | Job Applicant |  |  |  | None | None |
| `employment_type` | Employment Type | Link | Employment Type |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 28
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/employee/employee.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.setup");
erpnext.setup.EmployeeController = class EmployeeController extends frappe.ui.form.Controller {
	setup() {
		this.frm.fields_dict.user_id.get_query = function (doc, cdt, cdn) {
			return {
				query: "frappe.core.doctype.user.user.user_query",
				filters: { ignore_user_type: 1 },
			};
		};
		this.frm.fields_dict.reports_to.get_query = function (doc, cdt, cdn) {
			return { query: "erpnext.controllers.queries.employee_query" };
		};
	}

	refresh() {
		erpnext.toggle_naming_series();
	}
};

frappe.ui.form.on("Employee", {
	onload: function (frm) {
		frm.set_query("department", function () {
			return {
				filters: {
					company: frm.doc.company,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.fields_dict.date_of_birth.datepicker.update({ maxDate: new Date() });
	},

	prefered_contact_email: function (frm) {
		frm.events.update_contact(frm);
	},

	personal_email: function (frm) {
		frm.events.update_contact(frm);
	},

	company_email: function (frm) {
		frm.events.update_contact(frm);
	},

	user_id: function (frm) {
		frm.events.update_contact(frm);
	},

	update_contact: function (frm) {
		var prefered_email_fieldname = frappe.model.scrub(frm.doc.prefered_contact_email) || "user_id";
		frm.set_value("prefered_email", frm.fields_dict[prefered_email_fieldname].value);
	},

	status: function (frm) {
		return frm.call({
			method: "deactivate_sales_person",
			args: {
				employee: frm.doc.employee,
				status: frm.doc.status,
			},
		});
	},

	create_user: function (frm) {
		if (!frm.doc.prefered_email) {
			frappe.throw(__("Please enter Preferred Contact Email"));
		}
		frappe.call({
			method: "erpnext.setup.doctype.employee.employee.create_user",
			args: {
				employee: frm.doc.name,
				email: frm.doc.prefered_email,
			},
			freeze: true,
			freeze_message: __("Creating User..."),
			callback: function (r) {
				frm.reload_doc();
			},
		});
	},
});

cur_frm.cscript = new erpnext.setup.EmployeeController({
	frm: cur_frm,
});

frappe.tour["Employee"] = [
	{
		fieldname: "first_name",
		title: "First Name",
		description: __(
			"Enter First and Last name of Employee, based on Which Full Name will be updated. IN transactions, it will be Full Name which will be fetched."
		),
	},
	{
		fieldname: "company",
		title: "Company",
		description: __("Select a Company this Employee belongs to."),
	},
	{
		fieldname: "date_of_birth",
		title: "Date of Birth",
		description: __(
			"Select Date of Birth. This will validate Employees age and prevent hiring of under-age staff."
		),
	},
	{
		fieldname: "date_of_joining",
		title: "Date of Joining",
		description: __(
			"Select Date of joining. It will have impact on the first salary calculation, Leave allocation on pro-rata bases."
		),
	},
	{
		fieldname: "reports_to",
		title: "Reports To",
		description: __(
			"Here, you can select a senior of this Employee. Based on this, Organization Chart will be populated."
		),
	},
];

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Employee Analytics` | Script Report | HR |
| `Employee Leave Balance Summary` | Script Report | HR |
| `Employee Information` | Report Builder | HR |
| `Employee Birthday` | Script Report | HR |
| `Employee Leave Balance` | Script Report | HR |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Employees by Type` | Employees by Type | Group By | HR |
| `Employees by Branch` | Employees by Branch | Group By | HR |
| `Employees by Grade` | Employees by Grade | Group By | HR |
| `Designation Wise Employee Count` | Designation Wise Employee Count | Group By | HR |
| `Department Wise Employee Count` | Department Wise Employee Count | Group By | HR |
| `Gender Diversity Ratio` | Gender Diversity Ratio | Group By | HR |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Employees Relieving (This Quarter)` | Employees Relieving (This Quarter) | Count | HR |
| `Employees Joining (This Quarter)` | Employees Joining (This Quarter) | Count | HR |
| `Employee Exits (This Year)` | Employee Exits (This Year) | Count | HR |
| `New Hires (This Year)` | New Hires (This Year) | Count | HR |
| `Total Employees` | Active Employees | Count | HR |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
