# Master Control Plan: `Push Notification Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Enabling this will register your site on a central relay server to send push notifications for all installed apps through Firebase Cloud Messaging. This server only stores user tokens and error logs, and no messages are saved.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_qgjr` | Relay Settings | Section Break | None |  |  |  | None | Enabling this will register your site on a central relay server to send push notifications for all installed apps through Firebase Cloud Messaging. This server only stores user tokens and error logs, and no messages are saved.  |
| `enable_push_notification_relay` | Enable Push Notification Relay | Check | None |  |  |  | 0 | None |
| `authentication_credential_section` | Authentication | Section Break | None |  |  |  | None | API Key and Secret to interact with the relay server. These will be auto-generated when the first push notification is sent from any of the apps installed on this site. |
| `api_key` | API Key | Data | None |  |  |  | None | None |
| `api_secret` | API Secret | Password | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/push_notification_settings/push_notification_settings.js`
```javascript
// Copyright (c) 2024, Frappe Technologies and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Push Notification Settings", {
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
