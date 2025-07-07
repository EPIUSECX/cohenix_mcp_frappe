# Master Control Plan: `OAuth Client`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `client_id` | App Client ID | Data | None |  |  | ✅ | None | None |
| `app_name` | App Name | Data | None | ✅ |  |  | None | None |
| `user` | User | Link | User |  | ✅ |  | None | None |
| `allowed_roles` | Allowed Roles | Table MultiSelect | OAuth Client Role |  |  |  | None | None |
| `cb_1` | None | Column Break | None |  |  |  | None | None |
| `client_secret` | App Client Secret | Data | None |  |  | ✅ | None | None |
| `skip_authorization` | Skip Authorization | Check | None |  |  |  | 0 | If checked, users will not see the Confirm Access dialog. |
| `sb_1` | None | Section Break | None |  |  |  | None | None |
| `scopes` | Scopes | Text | None | ✅ |  |  | all openid | A list of resources which the Client App will have access to after the user allows it.<br> e.g. project |
| `cb_3` | None | Column Break | None |  |  |  | None | None |
| `redirect_uris` | Redirect URIs | Text | None |  |  |  | None | URIs for receiving authorization code once the user allows access, as well as failure responses. Typically a REST endpoint exposed by the Client App.
<br>e.g. http://hostname/api/method/frappe.integrations.oauth2_logins.login_via_facebook |
| `default_redirect_uri` | Default Redirect URI | Data | None | ✅ |  |  | None | None |
| `sb_advanced` | Advanced Settings | Section Break | None |  |  |  | None | None |
| `grant_type` | Grant Type | Select | Authorization Code
Implicit |  |  |  | None | None |
| `cb_2` | None | Column Break | None |  |  |  | None | None |
| `response_type` | Response Type | Select | Code
Token |  |  |  | Code | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/oauth_client/oauth_client.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("OAuth Client", {
	refresh: function (frm) {},
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
