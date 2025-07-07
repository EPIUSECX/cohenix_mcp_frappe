# Master Control Plan: `Reminder`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Automation`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `user` | User | Link | User | ✅ | ✅ |  | __user | None |
| `remind_at` | Remind At | Datetime | None | ✅ |  |  | now | None |
| `description` | Description | Small Text | None | ✅ |  |  | None | None |
| `reminder_doctype` | Document Type | Link | DocType |  |  | ✅ | None | None |
| `reminder_docname` | Document Name | Dynamic Link | reminder_doctype |  |  | ✅ | None | None |
| `notified` | notified | Check | None |  | ✅ |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/reminder/reminder.js`
```javascript
// Copyright (c) 2023, Frappe Technologies and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Reminder", {
// 	refresh(frm) {

// 	},
// });

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
