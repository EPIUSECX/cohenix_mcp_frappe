# Master Control Plan: `Interview Feedback`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-INT-FEED-.####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Interviewer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `details_section` | Details | Section Break | None |  |  |  | None | None |
| `interview` | Interview | Link | Interview | ✅ |  |  | None | None |
| `interview_round` | Interview Round | Link | Interview Round | ✅ |  | ✅ | None | None |
| `job_applicant` | Job Applicant | Link | Job Applicant |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `interviewer` | Interviewer | Link | User | ✅ |  |  | None | None |
| `result` | Result | Select | 
Cleared
Rejected | ✅ |  |  | None | None |
| `section_break_4` | Skill Assessment | Section Break | None |  |  |  | None | None |
| `skill_assessment` | None | Table | Skill Assessment | ✅ |  |  | None | None |
| `average_rating` | Average Rating | Rating | None |  |  | ✅ | None | None |
| `section_break_7` | Feedback | Section Break | None |  |  |  | None | None |
| `feedback` | None | Text | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Interview Feedback |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/interview_feedback/interview_feedback.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Interview Feedback", {
	onload: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Interview"];

		frm.set_query("interview", function () {
			return {
				filters: {
					docstatus: ["!=", 2],
				},
			};
		});
	},

	interview_round: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.interview.interview.get_expected_skill_set",
			args: {
				interview_round: frm.doc.interview_round,
			},
			callback: function (r) {
				frm.set_value("skill_assessment", r.message);
			},
		});
	},

	interview: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.interview_feedback.interview_feedback.get_applicable_interviewers",
			args: {
				interview: frm.doc.interview || "",
			},
			callback: function (r) {
				frm.set_query("interviewer", function () {
					return {
						filters: {
							name: ["in", r.message],
						},
					};
				});
			},
		});
	},

	interviewer: function (frm) {
		if (!frm.doc.interview) {
			frappe.throw(__("Select Interview first"));
			frm.set_value("interviewer", "");
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
