# Master Control Plan: `Notification Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| All | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 1 | None |
| `subscribed_documents` | Open Documents | Table MultiSelect | Notification Subscribed Document |  |  |  | None | None |
| `column_break_3` | Email Settings | Section Break | None |  |  |  | None | None |
| `enable_email_notifications` | Enable Email Notifications | Check | None |  |  |  | 1 | None |
| `enable_email_mention` | Mentions | Check | None |  |  |  | 1 | None |
| `enable_email_assignment` | Assignments | Check | None |  |  |  | 1 | None |
| `enable_email_threads_on_assigned_document` | Email Threads on Assigned Document | Check | None |  |  |  | 1 | Get notified when an email is received on any of the documents assigned to you. |
| `enable_email_share` | Document Share | Check | None |  |  |  | 1 | None |
| `enable_email_event_reminders` | Event Reminders | Check | None |  |  |  | 1 | None |
| `user` | User | Link | User |  | ✅ | ✅ | __user | None |
| `seen` | Seen | Check | None |  | ✅ |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/notification_settings/notification_settings.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Notification Settings", {
	onload: (frm) => {
		frm.set_query("subscribed_documents", () => {
			return {
				filters: {
					istable: 0,
				},
			};
		});
	},

	refresh: (frm) => {
		if (frappe.user.has_role("System Manager")) {
			frm.add_custom_button(__("Go to Notification Settings List"), () => {
				frappe.set_route("List", "Notification Settings");
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
