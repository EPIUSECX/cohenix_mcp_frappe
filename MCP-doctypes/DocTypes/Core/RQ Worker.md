# Master Control Plan: `RQ Worker`

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
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `worker_information_section` | Worker Information | Section Break | None |  |  |  | None | None |
| `queue` | Queue(s) | Data | None |  |  |  | None | None |
| `queue_type` | Queue Type(s) | Select | default
long
short |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `worker_name` | Worker Name | Data | None |  |  |  | None | None |
| `statistics_section` | Statistics | Section Break | None |  |  |  | None | None |
| `status` | Status | Data | None |  |  |  | None | None |
| `pid` | PID | Data | None |  |  |  | None | None |
| `current_job_id` | Current Job ID | Link | RQ Job |  |  |  | None | None |
| `successful_job_count` | Successful Job Count | Int | None |  |  |  | None | None |
| `failed_job_count` | Failed Job Count | Int | None |  |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `birth_date` | Start Time | Datetime | None |  |  |  | None | None |
| `last_heartbeat` | Last Heartbeat | Datetime | None |  |  |  | None | None |
| `total_working_time` | Total Working Time | Duration | None |  |  |  | None | None |
| `utilization_percent` | Utilization % | Percent | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/rq_worker/rq_worker.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("RQ Worker", {
	refresh: function (frm) {
		// Nothing in this form is supposed to be editable.
		frm.disable_form();
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
