# Master Control Plan: `Training Feedback`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `HR-TRF-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Employee | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `employee` | Employee | Link | Employee | ✅ |  |  | None | None |
| `employee_name` | Employee Name | Read Only | None |  |  |  | None | None |
| `department` | Department | Link | Department |  |  | ✅ | None | None |
| `course` | Course | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `training_event` | Training Event | Link | Training Event | ✅ |  |  | None | None |
| `event_name` | Event Name | Data | None |  |  | ✅ | None | None |
| `trainer_name` | Trainer Name | Data | None |  |  | ✅ | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `feedback` | Feedback | Text | None | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Training Feedback |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/training_feedback/training_feedback.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Training Feedback", {
	onload: function (frm) {
		frm.add_fetch("training_event", "course", "course");
		frm.add_fetch("training_event", "event_name", "event_name");
		frm.add_fetch("training_event", "trainer_name", "trainer_name");
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
