# Master Control Plan: `RQ Job`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:job_id`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Administrator | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `job_info_section` | Job Info | Section Break | None |  |  |  | None | None |
| `job_id` | Job ID | Data | None |  |  |  | None | None |
| `job_name` | Job Name | Data | None |  |  |  | None | None |
| `queue` | Queue | Select | default
short
long |  |  |  | None | None |
| `timeout` | Timeout | Duration | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `arguments` | Arguments | Code | None |  |  |  | None | None |
| `job_status_section` | Job Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | queued
started
finished
failed
deferred
scheduled
canceled |  |  |  | None | None |
| `time_taken` | Time Taken | Duration | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `started_at` | Started At | Datetime | None |  |  |  | None | None |
| `ended_at` | Ended At | Datetime | None |  |  |  | None | None |
| `exception_section` | None | Section Break | None |  |  |  | None | None |
| `exc_info` | Exception | Code | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/rq_job/rq_job.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("RQ Job", {
	refresh: function (frm) {
		// Nothing in this form is supposed to be editable.
		frm.disable_form();
		frm.dashboard.set_headline_alert(
			__("This is a virtual doctype and data is cleared periodically.")
		);

		if (["started", "queued"].includes(frm.doc.status)) {
			frm.add_custom_button(__("Force Stop job"), () => {
				frappe.confirm(
					__(
						"This will terminate the job immediately and might be dangerous, are you sure? "
					),
					() => {
						frappe
							.xcall("frappe.core.doctype.rq_job.rq_job.stop_job", {
								job_id: frm.doc.name,
							})
							.then((r) => {
								frappe.show_alert(__("Job Stopped Successfully"));
								frm.reload_doc();
							});
					}
				);
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
