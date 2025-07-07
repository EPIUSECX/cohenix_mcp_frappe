# Master Control Plan: `Exit Interview`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Naming Series | Select | HR-EXIT-INT- |  |  |  | None | None |
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Data | None |  |  | ✅ | None | None |
| `email` | Email ID | Data | Email |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `status` | Status | Select | Pending
Scheduled
Completed
Cancelled | ✅ |  |  | None | None |
| `date` | Date | Date | None |  |  |  | None | None |
| `employee_details_section` | Employee Details | Section Break | None |  |  |  | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `designation` | Designation | Link | Designation |  |  | ✅ | None | None |
| `reports_to` | Reports To | Link | Employee |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `date_of_joining` | Date of Joining | Date | None |  |  | ✅ | None | None |
| `relieving_date` | Relieving Date | Date | None |  |  | ✅ | None | None |
| `exit_questionnaire_section` | Exit Questionnaire | Section Break | None |  |  |  | None | None |
| `ref_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `questionnaire_email_sent` | Questionnaire Email Sent | Check | None |  |  | ✅ | 0 | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `reference_document_name` | Reference Document Name | Dynamic Link | ref_doctype |  |  |  | None | None |
| `interview_summary_section` | Interview Details | Section Break | None |  |  |  | None | None |
| `interviewers` | Interviewers | Table MultiSelect | Interviewer |  |  |  | None | None |
| `interview_summary` | Interview Summary | Text Editor | None |  |  |  | None | None |
| `employee_status_section` | None | Section Break | None |  |  |  | None | None |
| `employee_status` | Final Decision | Select | 
Employee Retained
Exit Confirmed |  |  |  | None | None |
| `amended_from` | Amended From | Link | Exit Interview |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/exit_interview/exit_interview.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Exit Interview", {
	refresh: function (frm) {
		if (
			!frm.doc.__islocal &&
			!frm.doc.questionnaire_email_sent &&
			frappe.boot.user.can_write.includes("Exit Interview")
		) {
			frm.add_custom_button(__("Send Exit Questionnaire"), function () {
				frm.trigger("send_exit_questionnaire");
			});
		}
	},

	employee: function (frm) {
		frappe.db.get_value("Employee", frm.doc.employee, "relieving_date", (message) => {
			if (!message.relieving_date) {
				frappe.throw({
					message: __("Please set the relieving date for employee {0}", [
						'<a href="/app/employee/' +
							frm.doc.employee +
							'">' +
							frm.doc.employee +
							"</a>",
					]),
					title: __("Relieving Date Missing"),
				});
			}
		});
	},

	send_exit_questionnaire: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.exit_interview.exit_interview.send_exit_questionnaire",
			args: {
				interviews: [frm.doc],
			},
			callback: function (r) {
				if (!r.exc) {
					frm.refresh_field("questionnaire_email_sent");
				}
			},
		});
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Employee Exits` | Script Report | HR |



### Dashboard Charts
No dashboard charts found.


### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
| Name | Event | Channel | Subject |
|---|---|---|---|
| `Exit Interview Scheduled` | Days Before | Email | Exit Interview Scheduled: {{ doc.name }} |



### Webhooks
No enabled webhooks found.
