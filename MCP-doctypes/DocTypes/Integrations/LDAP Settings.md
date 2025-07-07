# Master Control Plan: `LDAP Settings`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `enabled` | Enabled | Check | None |  |  |  | 0 | None |
| `ldap_server_settings_section` | LDAP Server Settings | Section Break | None |  |  |  | None | None |
| `ldap_directory_server` | Directory Server | Select | 
Active Directory
OpenLDAP
Custom | ✅ |  |  | None | Please select the LDAP Directory being used |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `ldap_server_url` | LDAP Server Url | Data | None | ✅ |  |  | None | None |
| `ldap_auth_section` | LDAP Auth | Section Break | None |  |  |  | None | None |
| `base_dn` | Base Distinguished Name (DN) | Data | None | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `password` | Password for Base DN | Password | None | ✅ |  |  | None | None |
| `ldap_search_and_paths_section` | LDAP Search and Paths | Section Break | None |  |  |  | None | None |
| `ldap_search_path_user` | LDAP search path for Users | Data | None | ✅ |  |  | None | Requires any valid fdn path. i.e. ou=users,dc=example,dc=com |
| `ldap_search_string` | LDAP Search String | Data | None | ✅ |  |  | None | Must be enclosed in '()' and include '{0}', which is a placeholder for the user/login name. i.e. (&(objectclass=user)(uid={0})) |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `ldap_search_path_group` | LDAP search path for Groups | Data | None | ✅ |  |  | None | Requires any valid fdn path. i.e. ou=groups,dc=example,dc=com |
| `ldap_user_creation_and_mapping_section` | LDAP User Creation and Mapping | Section Break | None |  |  |  | None | None |
| `ldap_email_field` | LDAP Email Field | Data | None | ✅ |  |  | None | None |
| `ldap_username_field` | LDAP Username Field | Data | None | ✅ |  |  | None | None |
| `ldap_first_name_field` | LDAP First Name Field | Data | None | ✅ |  |  | None | None |
| `do_not_create_new_user` | Do Not Create New User  | Check | None |  |  |  | 0 | Do not create new user if user with email does not exist in the system |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `ldap_middle_name_field` | LDAP Middle Name Field | Data | None |  |  |  | None | None |
| `ldap_last_name_field` | LDAP Last Name Field | Data | None |  |  |  | None | None |
| `ldap_phone_field` | LDAP Phone Field | Data | None |  |  |  | None | None |
| `ldap_mobile_field` | LDAP Mobile Field | Data | None |  |  |  | None | None |
| `ldap_security` | LDAP Security | Section Break | None |  |  |  | None | None |
| `ssl_tls_mode` | SSL/TLS Mode | Select | Off
StartTLS |  |  |  | Off | None |
| `require_trusted_certificate` | Require Trusted Certificate | Select | No
Yes | ✅ |  |  | No | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `local_private_key_file` | Path to private Key File | Data | None |  |  |  | None | None |
| `local_server_certificate_file` | Path to Server Certificate | Data | None |  |  |  | None | None |
| `local_ca_certs_file` | Path to CA Certs File | Data | None |  |  |  | None | None |
| `ldap_custom_settings_section` | LDAP Custom Settings | Section Break | None |  |  |  | None | These settings are required if 'Custom' LDAP Directory is used |
| `ldap_group_objectclass` | Group Object Class | Data | None |  |  |  | None | string value, i.e. group |
| `ldap_custom_group_search` | Custom Group Search | Data | None |  |  |  | None | string value, i.e. {0} or uid={0},ou=users,dc=example,dc=com |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `ldap_group_member_attribute` | LDAP Group Member attribute | Data | None |  |  |  | None | string value, i.e. member |
| `ldap_group_mappings_section` | LDAP Group Mappings | Section Break | None |  |  |  | None | None |
| `default_user_type` | Default User Type | Link | User Type | ✅ |  |  | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `default_role` | Default User Role | Link | Role |  |  |  | None | None |
| `section_break_40` | None | Section Break | None |  |  |  | None | None |
| `ldap_groups` | LDAP Group Mappings | Table | LDAP Group Mapping |  |  |  | None | None |
| `ldap_group_field` | LDAP Group Field | Data | None |  |  |  | None | NOTE: This box is due for depreciation. Please re-setup LDAP to work with the newer settings |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/ldap_settings/ldap_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("LDAP Settings", {
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
