# Master Control Plan: `Google Calendar`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:calendar_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enable` | Enable | Check | None |  |  |  | 1 | None |
| `sb_00` | Google Calendar | Section Break | None |  |  |  | None | None |
| `calendar_name` | Calendar Name | Data | None | ✅ |  |  | None | The name that will appear in Google Calendar |
| `user` | User | Link | User | ✅ |  |  | None | None |
| `authorize_google_calendar_access` | Authorize Google Calendar Access | Button | None |  |  |  | None | None |
| `sb_01` | Sync | Section Break | None |  |  |  | None | None |
| `pull_from_google_calendar` | Pull from Google Calendar | Check | None |  |  |  | 1 | None |
| `sync_as_public` | Sync events from Google as public | Check | None |  |  |  | 0 | None |
| `cb_01` | None | Column Break | None |  |  |  | None | None |
| `push_to_google_calendar` | Push to Google Calendar | Check | None |  |  |  | 1 | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `google_calendar_id` | Google Calendar ID | Data | None |  |  | ✅ | None | None |
| `refresh_token` | Refresh Token | Password | None |  | ✅ |  | None | None |
| `authorization_code` | Authorization Code | Password | None |  | ✅ |  | None | None |
| `next_sync_token` | Next Sync Token | Password | None |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/google_calendar/google_calendar.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Google Calendar", {
	refresh: function (frm) {
		if (frm.is_new()) {
			frm.dashboard.set_headline(
				__("To use Google Calendar, enable {0}.", [
					`<a href='/app/google-settings'>${__("Google Settings")}</a>`,
				])
			);
		}

		frappe.realtime.on("import_google_calendar", (data) => {
			if (data.progress) {
				frm.dashboard.show_progress(
					"Syncing Google Calendar",
					(data.progress / data.total) * 100,
					__("Syncing {0} of {1}", [data.progress, data.total])
				);
				if (data.progress === data.total) {
					frm.dashboard.hide_progress("Syncing Google Calendar");
				}
			}
		});

		if (frm.doc.refresh_token) {
			frm.add_custom_button(__("Sync Calendar"), function () {
				frappe.show_alert({
					indicator: "green",
					message: __("Syncing"),
				});
				frappe
					.call({
						method: "frappe.integrations.doctype.google_calendar.google_calendar.sync",
						args: {
							g_calendar: frm.doc.name,
						},
					})
					.then((r) => {
						frappe.hide_progress();
						frappe.msgprint(r.message);
					});
			});
		}
	},
	authorize_google_calendar_access: function (frm) {
		let reauthorize = 0;
		if (frm.doc.authorization_code) {
			reauthorize = 1;
		}

		frappe.call({
			method: "frappe.integrations.doctype.google_calendar.google_calendar.authorize_access",
			args: {
				g_calendar: frm.doc.name,
				reauthorize: reauthorize,
			},
			callback: function (r) {
				if (!r.exc) {
					frm.save();
					window.open(r.message.url);
				}
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
