# Master Control Plan: `Appointment Letter`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `HR-APP-LETTER-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `job_applicant` | Job Applicant | Link | Job Applicant | ✅ |  |  | None | None |
| `applicant_name` | Applicant Name | Data | None | ✅ |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `appointment_date` | Appointment Date | Date | None | ✅ |  |  | None | None |
| `appointment_letter_template` | Appointment Letter Template | Link | Appointment Letter Template | ✅ |  |  | None | None |
| `body_section` | Body | Section Break | None |  |  |  | None | None |
| `introduction` | Introduction | Long Text | None | ✅ |  |  | None | None |
| `terms` | Terms | Table | Appointment Letter content | ✅ |  |  | None | None |
| `closing_notes` | Closing Notes | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/appointment_letter/appointment_letter.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Appointment Letter", {
	appointment_letter_template: function (frm) {
		if (frm.doc.appointment_letter_template) {
			frappe.call({
				method: "hrms.hr.doctype.appointment_letter.appointment_letter.get_appointment_letter_details",
				args: {
					template: frm.doc.appointment_letter_template,
				},
				callback: function (r) {
					if (r.message) {
						let message_body = r.message;
						frm.set_value("introduction", message_body[0].introduction);
						frm.set_value("closing_notes", message_body[0].closing_notes);
						frm.doc.terms = [];
						for (var i in message_body[1].description) {
							frm.add_child("terms");
							frm.fields_dict.terms.get_value()[i].title =
								message_body[1].description[i].title;
							frm.fields_dict.terms.get_value()[i].description =
								message_body[1].description[i].description;
						}
						frm.refresh();
					}
				},
			});
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
