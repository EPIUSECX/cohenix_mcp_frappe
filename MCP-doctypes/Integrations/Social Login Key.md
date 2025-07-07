# Master Control Plan: `Social Login Key`

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
| `enable_social_login` | Enable Social Login | Check | None |  |  |  | 0 | None |
| `client_credentials` | Client Credentials | Section Break | None |  |  |  | None | None |
| `social_login_provider` | Social Login Provider | Select | Custom
Facebook
Frappe
GitHub
Google
Office 365
Salesforce
fairlogin
Keycloak |  |  |  | Custom | None |
| `client_id` | Client ID | Data | None |  |  |  | None | None |
| `column_break_0` | None | Column Break | None |  |  |  | None | None |
| `provider_name` | Provider Name | Data | None | ✅ |  |  | None | None |
| `client_secret` | Client Secret | Password | None |  |  |  | None | None |
| `sb_identity_details` | Identity Details | Section Break | None |  |  |  | None | None |
| `icon` | Icon | Data | None |  |  |  | None | None |
| `column_break_1` | None | Column Break | None |  |  |  | None | None |
| `base_url` | Base URL | Data | None |  |  |  | None | None |
| `configuration_section` | Configuration | Section Break | None |  |  |  | None | None |
| `sign_ups` | Sign ups | Select | 
Allow
Deny |  |  |  | None | Controls whether new users can sign up using this Social Login Key. If unset, Website Settings is respected. |
| `client_urls` | Client URLs | Section Break | None |  |  |  | None | None |
| `authorize_url` | Authorize URL | Data | None |  |  |  | None | None |
| `access_token_url` | Access Token URL | Data | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `redirect_url` | Redirect URL | Data | None |  |  |  | None | None |
| `api_endpoint` | API Endpoint | Data | None |  |  |  | None | None |
| `custom_base_url` | Custom Base URL | Check | None |  | ✅ |  | 0 | None |
| `client_information` | Client Information | Section Break | None |  |  |  | None | None |
| `api_endpoint_args` | API Endpoint Args | Code | None |  |  |  | None | None |
| `auth_url_data` | Auth URL Data | Code | None |  |  |  | None | None |
| `user_id_property` | User ID Property | Data | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/social_login_key/social_login_key.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt
const fields = [
	"provider_name",
	"base_url",
	"custom_base_url",
	"icon",
	"authorize_url",
	"access_token_url",
	"redirect_url",
	"api_endpoint",
	"api_endpoint_args",
	"auth_url_data",
];

frappe.ui.form.on("Social Login Key", {
	refresh(frm) {
		frm.trigger("setup_fields");
	},

	custom_base_url(frm) {
		frm.trigger("setup_fields");
	},

	social_login_provider(frm) {
		if (frm.doc.social_login_provider != "Custom") {
			frappe
				.call({
					doc: frm.doc,
					method: "get_social_login_provider",
					args: {
						provider: frm.doc.social_login_provider,
					},
				})
				.done((r) => {
					const provider = r.message;
					for (var field of fields) {
						frm.set_value(field, provider[field]);
						frm.set_df_property(field, "read_only", 1);
						if (frm.doc.custom_base_url) {
							frm.toggle_enable("base_url", 1);
						}
					}
				});
		} else {
			frm.trigger("clear_fields");
			frm.trigger("setup_fields");
		}
	},

	setup_fields(frm) {
		// set custom_base_url to read only for "Custom" provider
		if (frm.doc.social_login_provider == "Custom") {
			frm.set_value("custom_base_url", 1);
			frm.set_df_property("custom_base_url", "read_only", 1);
		}

		// set fields to read only for providers from template
		for (var f of fields) {
			if (frm.doc.social_login_provider != "Custom") {
				frm.set_df_property(f, "read_only", 1);
			}
		}

		// enable base_url for providers with custom_base_url
		if (frm.doc.custom_base_url) {
			frm.set_df_property("base_url", "read_only", 0);
			frm.fields_dict["sb_identity_details"].collapse(false);
		}

		// hide social_login_provider and provider_name for non local
		if (!frm.doc.__islocal && (frm.doc.social_login_provider || frm.doc.provider_name)) {
			frm.set_df_property("social_login_provider", "hidden", 1);
			frm.set_df_property("provider_name", "hidden", 1);
		}
	},

	clear_fields(frm) {
		for (var field of fields) {
			frm.set_value(field, "");
			frm.set_df_property(field, "read_only", 0);
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
