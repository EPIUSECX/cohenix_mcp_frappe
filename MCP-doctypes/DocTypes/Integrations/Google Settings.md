# Master Control Plan: `Google Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enable` | Enable | Check | None |  |  |  | 0 | None |
| `sb_00` | OAuth Client ID | Section Break | None |  |  |  | None | None |
| `client_id` | Client ID | Data | None |  |  |  | None | The Client ID obtained from the Google Cloud Console under <a href="https://console.cloud.google.com/apis/credentials">
"APIs &amp; Services" &gt; "Credentials"
</a> |
| `client_secret` | Client Secret | Password | None |  |  |  | None | None |
| `sb_01` | API Key | Section Break | None |  |  |  | None | None |
| `api_key` | API Key | Data | None |  |  |  | None | The browser API key obtained from the Google Cloud Console under <a href="https://console.cloud.google.com/apis/credentials">
"APIs &amp; Services" &gt; "Credentials"
</a> |
| `section_break_7` | Google Drive Picker | Section Break | None |  |  |  | None | None |
| `google_drive_picker_enabled` | Google Drive Picker Enabled | Check | None |  |  |  | 0 | None |
| `app_id` | App ID | Data | None |  |  |  | None | The project number obtained from Google Cloud Console under <a href="https://console.cloud.google.com/iam-admin/settings">
"IAM &amp; Admin" &gt; "Settings"
</a> |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/google_settings/google_settings.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Google Settings", {
	refresh: function (frm) {
		frm.dashboard.set_headline(
			__("For more information, {0}.", [
				`<a href='https://erpnext.com/docs/user/manual/en/erpnext_integration/google_settings'>${__(
					"Click here"
				)}</a>`,
			])
		);
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
