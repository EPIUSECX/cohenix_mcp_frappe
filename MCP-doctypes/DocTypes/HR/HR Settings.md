# Master Control Plan: `HR Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee_settings` | Employee Settings | Section Break | None |  |  |  | None | None |
| `emp_created_by` | Employee Naming By | Select | Naming Series
Employee Number
Full Name |  |  |  | Naming Series | Employee records are created using the selected option |
| `standard_working_hours` | Standard Working Hours | Float | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `retirement_age` | Retirement Age (In Years) | Data | None |  |  |  | None | None |
| `reminders_section` | Reminders | Section Break | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `send_work_anniversary_reminders` | Work Anniversaries  | Check | None |  |  |  | 1 | None |
| `send_birthday_reminders` | Birthdays | Check | None |  |  |  | 1 | None |
| `send_holiday_reminders` | Holidays | Check | None |  |  |  | 1 | None |
| `frequency` | Set the frequency for holiday reminders | Select | Weekly
Monthly |  |  |  | Weekly | None |
| `column_break_hyec` | None | Column Break | None |  |  |  | None | None |
| `sender` | Sender | Link | Email Account |  |  |  | None | None |
| `sender_email` | Sender Email | Data | None |  |  | ✅ | None | None |
| `leave_and_expense_claim_settings` | Leave and Expense Claim Settings | Section Break | None |  |  |  | None | None |
| `send_leave_notification` | Send Leave Notification | Check | None |  |  |  | 1 | None |
| `leave_approval_notification_template` | Leave Approval Notification Template | Link | Email Template |  |  |  | None | None |
| `leave_status_notification_template` | Leave Status Notification Template | Link | Email Template |  |  |  | None | None |
| `leave_approver_mandatory_in_leave_application` | Leave Approver Mandatory In Leave Application | Check | None |  |  |  | 1 | None |
| `restrict_backdated_leave_application` | Restrict Backdated Leave Application | Check | None |  |  |  | 0 | None |
| `prevent_self_leave_approval` | Prevent self approval for leaves even if user has permissions | Check | None |  |  |  | 0 | None |
| `role_allowed_to_create_backdated_leave_application` | Role Allowed to Create Backdated Leave Application | Link | Role |  |  |  | None | None |
| `column_break_29` | None | Column Break | None |  |  |  | None | None |
| `expense_approver_mandatory_in_expense_claim` | Expense Approver Mandatory In Expense Claim | Check | None |  |  |  | 1 | None |
| `show_leaves_of_all_department_members_in_calendar` | Show Leaves Of All Department Members In Calendar | Check | None |  |  |  | 0 | None |
| `auto_leave_encashment` | Auto Leave Encashment | Check | None |  |  |  | 0 | None |
| `shift_settings_section` | Shift Settings | Section Break | None |  |  |  | None | None |
| `allow_multiple_shift_assignments` | Allow Multiple Shift Assignments for Same Date | Check | None |  |  |  | 0 | None |
| `hiring_settings_section` | Hiring Settings | Section Break | None |  |  |  | None | None |
| `check_vacancies` | Check Vacancies On Job Offer Creation | Check | None |  |  |  | 0 | None |
| `send_interview_reminder` | Send Interview Reminder | Check | None |  |  |  | 0 | None |
| `interview_reminder_template` | Interview Reminder Notification Template | Link | Email Template |  |  |  | None | None |
| `remind_before` | Remind Before | Time | None |  |  |  | 00:15:00 | None |
| `send_interview_feedback_reminder` | Send Interview Feedback Reminder | Check | None |  |  |  | 0 | None |
| `feedback_reminder_notification_template` | Feedback Reminder Notification Template | Link | Email Template |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `hiring_sender` | Sender | Link | Email Account |  |  |  | None | None |
| `hiring_sender_email` | Sender Email | Data | None |  |  | ✅ | None | None |
| `employee_exit_section` | Employee Exit Settings | Section Break | None |  |  |  | None | None |
| `exit_questionnaire_web_form` | Exit Questionnaire Web Form | Link | Web Form |  |  |  | None | None |
| `column_break_34` | None | Column Break | None |  |  |  | None | None |
| `exit_questionnaire_notification_template` | Exit Questionnaire Notification Template | Link | Email Template |  |  |  | None | None |
| `attendance_settings_section` | Attendance Settings | Section Break | None |  |  |  | None | None |
| `allow_employee_checkin_from_mobile_app` | Allow Employee Checkin from Mobile App | Check | None |  |  |  | 1 | None |
| `allow_geolocation_tracking` | Allow Geolocation Tracking | Check | None |  |  |  | 0 | None |
| `unlink_payment_section` | Unlink Payment | Section Break | None |  |  |  | None | None |
| `unlink_payment_on_cancellation_of_employee_advance` |  Unlink Payment on Cancellation of Employee Advance | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/hr_settings/hr_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("HR Settings", {
	refresh: function (frm) {
		frm.set_query("sender", () => {
			return {
				filters: {
					enable_outgoing: 1,
				},
			};
		});
		frm.set_query("hiring_sender", () => {
			return {
				filters: {
					enable_outgoing: 1,
				},
			};
		});
	},
});

frappe.tour["HR Settings"] = [
	{
		fieldname: "emp_created_by",
		title: "Employee Naming By",
		description: __(
			"Employee can be named by Employee ID if you assign one, or via Naming Series. Select your preference here.",
		),
	},
	{
		fieldname: "standard_working_hours",
		title: "Standard Working Hours",
		description: __(
			"Enter the Standard Working Hours for a normal work day. These hours will be used in calculations of reports such as Employee Hours Utilization and Project Profitability analysis.",
		),
	},
	{
		fieldname: "leave_and_expense_claim_settings",
		title: "Leave and Expense Claim Settings",
		description: __(
			"Review various other settings related to Employee Leaves and Expense Claim",
		),
	},
];

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
