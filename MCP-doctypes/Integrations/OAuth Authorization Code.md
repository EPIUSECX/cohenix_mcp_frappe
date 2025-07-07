# Master Control Plan: `OAuth Authorization Code`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Integrations`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:authorization_code`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `client` | Client | Link | OAuth Client |  |  | ✅ | None | None |
| `user` | User | Link | User |  |  | ✅ | None | None |
| `scopes` | Scopes | Text | None |  |  | ✅ | None | None |
| `authorization_code` | Authorization Code | Data | None |  |  | ✅ | None | None |
| `expiration_time` | Expiration time | Datetime | None |  |  | ✅ | None | None |
| `redirect_uri_bound_to_authorization_code` | Redirect URI Bound To Auth Code | Data | None |  |  | ✅ | None | None |
| `validity` | Validity | Select | Valid
Invalid |  |  | ✅ | None | None |
| `nonce` | nonce | Data | None |  |  | ✅ | None | None |
| `code_challenge` | Code Challenge | Data | None |  |  | ✅ | None | None |
| `code_challenge_method` | Code challenge method | Select | 
s256
plain |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/oauth_authorization_code/oauth_authorization_code.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("OAuth Authorization Code", {
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
