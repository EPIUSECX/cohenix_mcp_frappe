# Master Control Plan: `System Health Report`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `background_jobs_tab` | Report | Tab Break | None |  |  |  | None | None |
| `background_jobs_section` | Background Jobs | Section Break | None |  |  |  | None | None |
| `total_background_workers` | Total Background Workers | Int | None |  |  |  | None | None |
| `column_break_klex` | None | Column Break | None |  |  |  | None | None |
| `background_jobs_check` | Background Jobs Check | Data | None |  |  |  | None | None |
| `test_job_id` | Test Job ID | Data | None |  | ✅ |  | None | None |
| `section_break_djoz` | None | Section Break | None |  |  |  | None | None |
| `queue_status` | Queue Status | Table | System Health Report Queue |  |  |  | None | None |
| `column_break_wjoz` | None | Column Break | None |  |  |  | None | None |
| `background_workers` | Background Workers | Table | System Health Report Workers |  |  |  | None | None |
| `scheduler_section` | Scheduler | Section Break | None |  |  |  | None | None |
| `scheduler_status` | Scheduler Status | Data | None |  |  |  | None | None |
| `column_break_bxog` | None | Column Break | None |  |  |  | None | None |
| `oldest_unscheduled_job` | Oldest Unscheduled Job | Link | Scheduled Job Type |  |  |  | None | None |
| `section_break_vpuw` | None | Section Break | None |  |  |  | None | None |
| `failing_scheduled_jobs` | Failing Scheduled Jobs (last 7 days) | Table | System Health Report Failing Jobs |  |  |  | None | None |
| `database_section` | Database | Section Break | None |  |  |  | None | None |
| `database` | Database | Data | None |  |  |  | None | None |
| `database_version` | Database Version | Data | None |  |  |  | None | None |
| `db_storage_usage` | Storage Usage (MB) | Float | None |  |  |  | None | None |
| `column_break_auhv` | None | Column Break | None |  |  |  | None | None |
| `top_db_tables` | Storage Usage By Table | Table | System Health Report Tables |  |  |  | None | None |
| `mariadb_variables_section` | MariaDB Variables | Section Break | None |  |  |  | None | None |
| `bufferpool_size` | Bufferpool Size | Data | None |  |  |  | None | None |
| `column_break_vztw` | None | Column Break | None |  |  |  | None | None |
| `binary_logging` | Binary Logging | Data | None |  |  |  | None | None |
| `cache_section` | Cache | Section Break | None |  |  |  | None | None |
| `cache_keys` | Number of keys | Int | None |  |  |  | None | None |
| `column_break_ccov` | None | Column Break | None |  |  |  | None | None |
| `cache_memory_usage` | Memory Usage | Data | None |  |  |  | None | None |
| `realtime_socketio_section` | Realtime (SocketIO) | Section Break | None |  |  |  | None | None |
| `socketio_ping_check` | SocketIO Ping Check | Select | Fail
Pass |  |  |  | Fail | None |
| `column_break_hgay` | None | Column Break | None |  |  |  | None | None |
| `socketio_transport_mode` | SocketIO Transport Mode | Select | Polling
Websocket |  |  |  | None | None |
| `section_break_ryki` | File Storage | Section Break | None |  |  |  | None | None |
| `storage_usage_column` | None | Column Break | None |  |  |  | None | None |
| `public_files_size` | Public Files (MB) | Float | None |  |  |  | None | None |
| `column_break_jnkt` | None | Column Break | None |  |  |  | None | None |
| `private_files_size` | Private Files (MB) | Float | None |  |  |  | None | None |
| `backups_section` | Backups | Section Break | None |  |  |  | None | None |
| `backups_column` | None | Column Break | None |  |  |  | None | None |
| `onsite_backups` | Number of onsite backups | Int | None |  |  |  | None | None |
| `column_break_luox` | None | Column Break | None |  |  |  | None | None |
| `backups_size` | Backups (MB) | Float | None |  |  |  | None | None |
| `users_section` | Users | Section Break | None |  |  |  | None | None |
| `total_users` | Total Users | Int | None |  |  |  | None | None |
| `new_users` | New Users (Last 30 days) | Int | None |  |  |  | None | None |
| `failed_logins` | Failed Logins (Last 30 days) | Int | None |  |  |  | None | None |
| `active_sessions` | Active Sessions | Int | None |  |  |  | None | None |
| `column_break_yfwd` | None | Column Break | None |  |  |  | None | None |
| `last_10_active_users` | Last 10 active users | Code | None |  |  |  | None | None |
| `section_break_udjs` | Emails | Section Break | None |  |  |  | None | None |
| `outgoing_emails_column` | Outgoing Emails (Last 7 days) | Column Break | None |  |  |  | None | None |
| `total_outgoing_emails` | Total Outgoing Emails | Int | None |  |  |  | None | None |
| `pending_emails` | Pending Emails | Int | None |  |  |  | None | None |
| `failed_emails` | Failed Emails | Int | None |  |  |  | None | None |
| `incoming_emails_last_7_days_column` | Incoming Emails (Last 7 days) | Column Break | None |  |  |  | None | None |
| `handled_emails` | Handled Emails | Int | None |  |  |  | None | None |
| `unhandled_emails` | Unhandled Emails | Int | None |  |  |  | None | None |
| `errors_generated_in_last_1_day_section` | Errors | Section Break | None |  |  |  | None | None |
| `total_errors` | Total Errors (last 1 day) | Int | None |  |  |  | None | None |
| `top_errors` | Top Errors | Table | System Health Report Errors |  |  |  | None | None |
| `column_break_fzke` | None | Column Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 5

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/system_health_report/system_health_report.js`
```javascript
// Copyright (c) 2024, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("System Health Report", {
	onload(frm) {
		let poll_attempts = 0;
		const interval = setInterval(() => {
			frappe
				.xcall(
					"frappe.desk.doctype.system_health_report.system_health_report.get_job_status",
					{ job_id: frm.doc.test_job_id }
				)
				.then((status) => {
					poll_attempts += 1;
					if (["finished", "failed"].includes(status) || poll_attempts > 30) {
						clearInterval(interval);
					}
					status && frm.set_value("background_jobs_check", status);
				});
		}, 1000);
	},
	refresh(frm) {
		frm.set_value("socketio_ping_check", "Fail");
		frappe.realtime.on("pong", () => {
			frm.set_value("socketio_ping_check", "Pass");
			frm.set_value(
				"socketio_transport_mode",
				frappe.realtime.socket.io?.engine?.transport?.name
			);
		});
		frappe.realtime.emit("ping");
		frm.disable_save();
		frm.trigger("setup_highlight");
	},

	setup_highlight(frm) {
		/// field => is bad?
		const conditions = {
			scheduler_status: (val) => val.toLowerCase() != "active",
			background_jobs_check: (val) => val.toLowerCase() != "finished",
			total_background_workers: (val) => val == 0,
			binary_logging: (val) => val.toLowerCase() != "on",
			socketio_ping_check: (val) => val != "Pass",
			socketio_transport_mode: (val) => val != "websocket",
			onsite_backups: (val) => val == 0,
			failed_logins: (val) => val > frm.doc.total_users,
			total_errors: (val) => val > 50,
			// 5% excluding very small numbers
			unhandled_emails: (val) =>
				val > 3 && frm.doc.handled_emails > 3 && val / frm.doc.handled_emails > 0.05,
			failed_emails: (val) =>
				val > 3 &&
				frm.doc.total_outgoing_emails > 3 &&
				val / frm.doc.total_outgoing_emails > 0.05,
			pending_emails: (val) =>
				val > 3 &&
				frm.doc.total_outgoing_emails > 3 &&
				val / frm.doc.total_outgoing_emails > 0.1,
			oldest_unscheduled_job: (val) => !!val,
			"queue_status.pending_jobs": (val) => val > 50,
			"background_workers.utilization": (val) => val > 70,
			"background_workers.failed_jobs": (val) => val > 50,
			"top_errors.occurrences": (val) => val > 10,
			"failing_scheduled_jobs.failure_rate": (val) => val > 10,
		};

		const style = document.createElement("style");
		style.innerText = `.health-check-failed {
				font-weight: bold;
				color: var(--text-colour) !important;
				background-color: var(--bg-red) !important;
			}`;
		document.head.appendChild(style);

		const update_fields = () => {
			if (!frappe.get_route().includes(frm.doc.name)) {
				clearInterval(interval);
			}
			Object.entries(conditions).forEach(([field, condition]) => {
				try {
					if (field.includes(".")) {
						let [table, fieldname] = field.split(".");

						frm.fields_dict[table].grid.grid_rows.forEach((row) => {
							let is_bad = condition(row.doc[fieldname]);
							$(row.columns[fieldname]).toggleClass("health-check-failed", is_bad);
						});
					} else {
						let is_bad = condition(frm.doc[field]);
						let df = frm.fields_dict[field];
						$(df.disp_area).toggleClass("health-check-failed", is_bad);
					}
				} catch (e) {
					console.log("Failed to evaluated", e);
				}
			});
		};

		update_fields();
		const interval = setInterval(update_fields, 1000);
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
