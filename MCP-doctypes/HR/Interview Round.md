# Master Control Plan: `Interview Round`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:round_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Interviewer | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `round_name` | Round Name | Data | None | ✅ |  |  | None | None |
| `interview_type` | Interview Type | Link | Interview Type |  |  |  | None | None |
| `interviewers` | Interviewers | Table MultiSelect | Interviewer |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `expected_average_rating` | Expected Average Rating | Rating | None |  |  |  | None | None |
| `expected_skills_section` | None | Section Break | None |  |  |  | None | None |
| `designation` | Designation | Link | Designation |  |  |  | None | None |
| `expected_skill_set` | Expected Skillset | Table | Expected Skill Set | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/interview_round/interview_round.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Interview Round", {
	refresh: function (frm) {
		if (!frm.doc.__islocal) {
			frm.add_custom_button(__("Create Interview"), function () {
				frm.events.create_interview(frm);
			});
		}
	},
	designation: function (frm) {
		if (frm.doc.designation) {
			frappe.db.get_doc("Designation", frm.doc.designation).then((designation) => {
				frappe.model.clear_table(frm.doc, "expected_skill_set");

				designation.skills.forEach((designation_skill) => {
					const row = frm.add_child("expected_skill_set");
					row.skill = designation_skill.skill;
				});

				refresh_field("expected_skill_set");
			});
		}
	},
	create_interview: function (frm) {
		frappe.call({
			method: "hrms.hr.doctype.interview_round.interview_round.create_interview",
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
