# Master Control Plan: `Scheduled Job Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `stopped` | Stopped | Check | None |  |  |  | 0 | None |
| `method` | Method | Data | None | ✅ |  | ✅ | None | None |
| `server_script` | Server Script | Link | Server Script |  |  | ✅ | None | None |
| `scheduler_event` | Scheduler Event | Link | Scheduler Event |  |  | ✅ | None | None |
| `frequency` | Frequency | Select | All
Hourly
Hourly Long
Hourly Maintenance
Daily
Daily Long
Daily Maintenance
Weekly
Weekly Long
Monthly
Monthly Long
Cron
Yearly
Annual | ✅ |  | ✅ | None | None |
| `cron_format` | Cron Format | Data | None |  |  | ✅ | None | <pre>*  *  *  *  *
┬  ┬  ┬  ┬  ┬
│  │  │  │  │
│  │  │  │  └ day of week (0 - 6) (0 is Sunday)
│  │  │  └───── month (1 - 12)
│  │  └────────── day of month (1 - 31)
│  └─────────────── hour (0 - 23)
└──────────────────── minute (0 - 59)

---

* - Any value
/ - Step values
</pre>
 |
| `create_log` | Create Log | Check | None |  |  |  | 0 | None |
| `status_section` | Status | Section Break | None |  |  |  | None | None |
| `last_execution` | Last Execution | Datetime | None |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `next_execution` | Next Execution | Datetime | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/scheduled_job_type/scheduled_job_type.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Scheduled Job Type", {
	// refresh: function(frm) {
	// }
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
