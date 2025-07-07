# Master Control Plan: `Connected App`

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
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `provider_name` | Provider Name | Data | None | ✅ |  |  | None | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `openid_configuration` | OpenID Configuration | Data | None |  |  |  | None | None |
| `sb_client_credentials_section` | Client Credentials | Section Break | None |  |  |  | None | None |
| `client_id` | Client Id | Data | None |  |  |  | None | None |
| `redirect_uri` | Redirect URI | Data | None |  |  | ✅ | None | None |
| `cb_01` | None | Column Break | None |  |  |  | None | None |
| `client_secret` | Client Secret | Password | None |  |  |  | None | None |
| `sb_scope_section` | Scopes | Section Break | None |  |  |  | None | None |
| `scopes` | Scopes | Table | OAuth Scope |  |  |  | None | None |
| `sb_endpoints_section` | Endpoints | Section Break | None |  |  |  | None | None |
| `authorization_uri` | Authorization URI | Small Text | None |  |  |  | None | None |
| `token_uri` | Token URI | Data | None |  |  |  | None | None |
| `revocation_uri` | Revocation URI | Data | None |  |  |  | None | None |
| `cb_02` | None | Column Break | None |  |  |  | None | None |
| `userinfo_uri` | Userinfo URI | Data | None |  |  |  | None | None |
| `introspection_uri` | Introspection URI | Data | None |  |  |  | None | None |
| `section_break_18` | Extra Parameters | Section Break | None |  |  |  | None | None |
| `query_parameters` | Query Parameters | Table | Query Parameters |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/connected_app/connected_app.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Connected App", {
	refresh: (frm) => {
		frm.add_custom_button(__("Get OpenID Configuration"), async () => {
			if (!frm.doc.openid_configuration) {
				frappe.msgprint(__("Please enter OpenID Configuration URL"));
			} else {
				try {
					const response = await fetch(frm.doc.openid_configuration);
					const oidc = await response.json();
					frm.set_value("authorization_uri", oidc.authorization_endpoint);
					frm.set_value("token_uri", oidc.token_endpoint);
					frm.set_value("userinfo_uri", oidc.userinfo_endpoint);
					frm.set_value("introspection_uri", oidc.introspection_endpoint);
					frm.set_value("revocation_uri", oidc.revocation_endpoint);
				} catch (error) {
					frappe.msgprint(__("Please check OpenID Configuration URL"));
				}
			}
		});

		if (!frm.is_new()) {
			frm.add_custom_button(__("Connect to {}", [frm.doc.provider_name]), async () => {
				frappe.call({
					method: "initiate_web_application_flow",
					doc: frm.doc,
					callback: function (r) {
						window.open(r.message, "_blank");
					},
				});
			});
		}

		frm.toggle_display("sb_client_credentials_section", !frm.is_new());
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
