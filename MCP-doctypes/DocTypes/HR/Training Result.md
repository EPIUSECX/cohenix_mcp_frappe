# Master Control Plan: `Training Result`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-TRR-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `training_event` | Training Event | Link | Training Event | ✅ |  |  | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `employees` | Employees | Table | Training Result Employee |  |  |  | None | None |
| `amended_from` | Amended From | Link | Training Result |  |  | ✅ | None | None |
| `employee_emails` | Employee Emails | Small Text | Email |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/training_result/training_result.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Training Result", {
	training_event: function (frm) {
		if (frm.doc.training_event && !frm.doc.docstatus) {
			frappe.call({
				method: "hrms.hr.doctype.training_result.training_result.get_employees",
				args: {
					training_event: frm.doc.training_event,
				},
				callback: function (r) {
					frm.set_value("employees", "");
					if (r.message) {
						$.each(r.message, function (i, d) {
							var row = frappe.model.add_child(
								frm.doc,
								"Training Result Employee",
								"employees",
							);
							row.employee = d.employee;
							row.employee_name = d.employee_name;
						});
					}
					refresh_field("employees");
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
| Name | Event | Channel | Subject |
|---|---|---|---|
| `Training Feedback` | Submit | Email | Please Share your Feedback For {{ doc.training_event }} |



### Webhooks
No enabled webhooks found.
