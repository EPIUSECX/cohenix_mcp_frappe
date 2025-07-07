# Master Control Plan: `Payroll Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `working_days_section` | Working Days and Hours | Section Break | None |  |  |  | None | None |
| `payroll_based_on` | Calculate Payroll Working Days Based On | Select | Leave
Attendance |  |  |  | Leave | None |
| `consider_unmarked_attendance_as` | Consider Unmarked Attendance As | Select | Present
Absent |  |  |  | None | None |
| `include_holidays_in_total_working_days` | Include holidays in Total no. of Working Days | Check | None |  |  |  | 0 | If enabled, total no. of working days will include holidays, and this will reduce the value of Salary Per Day |
| `consider_marked_attendance_on_holidays` | Consider Marked Attendance on Holidays | Check | None |  |  |  | 0 | If enabled, deducts payment days for absent attendance on holidays. By default, holidays are considered as paid |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `max_working_hours_against_timesheet` | Max working hours against Timesheet | Float | None |  |  |  | None | None |
| `daily_wages_fraction_for_half_day` | Fraction of Daily Salary for Half Day | Float | None |  |  |  | 0.5 | The fraction of daily wages to be paid for half-day attendance |
| `column_break_rnoq` | Salary Slip | Section Break | None |  |  |  | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | If checked, hides and disables Rounded Total field in Salary Slips |
| `column_break_gzpl` | None | Column Break | None |  |  |  | None | None |
| `show_leave_balances_in_salary_slip` | Show Leave Balances in Salary Slip | Check | None |  |  |  | 0 | None |
| `email_section` | Email | Section Break | None |  |  |  | None | None |
| `email_salary_slip_to_employee` | Email Salary Slip to Employee | Check | None |  |  |  | 1 | Emails salary slip to employee based on preferred email selected in Employee |
| `sender` | Sender | Link | Email Account |  |  |  | None | None |
| `sender_email` | Sender Email | Data | None |  |  | ✅ | None | None |
| `email_template` | Email Template | Link | Email Template |  |  |  | None | None |
| `column_break_iewr` | None | Column Break | None |  |  |  | None | None |
| `encrypt_salary_slips_in_emails` | Encrypt Salary Slips in Emails | Check | None |  |  |  | 0 | The salary slip emailed to the employee will be password protected, the password will be generated based on the password policy. |
| `password_policy` | Password Policy | Data | None |  |  |  | None | <b>Example:</b> SAL-{first_name}-{date_of_birth.year} <br>This will generate a password like SAL-Jane-1972 |
| `other_settings_section` | Other Settings | Section Break | None |  |  |  | None | None |
| `process_payroll_accounting_entry_based_on_employee` | Process Payroll Accounting Entry based on Employee | Check | None |  |  |  | 0 | If checked, Payroll Payable will be booked against each employee |
| `column_break_zi9y` | None | Column Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/payroll_settings/payroll_settings.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Payroll Settings", {
	refresh: function (frm) {
		frm.set_query("sender", () => {
			return {
				filters: {
					enable_outgoing: 1,
				},
			};
		});
	},

	encrypt_salary_slips_in_emails: function (frm) {
		let encrypt_state = frm.doc.encrypt_salary_slips_in_emails;
		frm.set_df_property("password_policy", "reqd", encrypt_state);
	},

	validate: function (frm) {
		let policy = frm.doc.password_policy;
		if (policy) {
			if (policy.includes(" ") || policy.includes("--")) {
				frappe.msgprint(
					__(
						"Password policy cannot contain spaces or simultaneous hyphens. The format will be restructured automatically",
					),
				);
			}
			frm.set_value(
				"password_policy",
				policy
					.split(new RegExp(" |-", "g"))
					.filter((token) => token)
					.join("-"),
			);
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
