# Master Control Plan: `Daily Work Summary Group`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| HR Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `select_users` | Select Users | Section Break | None |  |  |  | None | None |
| `users` | Users | Table | Daily Work Summary Group User | ✅ |  |  | None | None |
| `send_emails_at` | Send Emails At | Select | 00:00
01:00
02:00
03:00
04:00
05:00
06:00
07:00
08:00
09:00
10:00
11:00
12:00
13:00
14:00
15:00
16:00
17:00
18:00
19:00
20:00
21:00
22:00
23:00 |  |  |  | None | None |
| `holiday_list` | Holiday List | Link | Holiday List |  |  |  | None | None |
| `mail_details` | Reminder | Section Break | None |  |  |  | None | None |
| `subject` | Subject | Data | None |  |  |  | What did you work on today? | None |
| `message` | Message | Text Editor | None |  |  |  | <p>Please share what did you do today. If you reply by midnight, your response will be recorded!</p> | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/daily_work_summary_group/daily_work_summary_group.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Daily Work Summary Group", {
	refresh: function (frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(__("Daily Work Summary"), function () {
				frappe.set_route("List", "Daily Work Summary");
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
