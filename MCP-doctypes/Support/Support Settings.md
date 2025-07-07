# Master Control Plan: `Support Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Support`
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
| `sb_00` | Service Level Agreements | Section Break | None |  |  |  | None | None |
| `track_service_level_agreement` | Track Service Level Agreement | Check | None |  |  |  | 0 | None |
| `allow_resetting_service_level_agreement` | Allow Resetting Service Level Agreement | Check | None |  |  |  | 0 | None |
| `issues_sb` | Issues | Section Break | None |  |  |  | None | None |
| `close_issue_after_days` | Close Issue After Days | Int | None |  |  |  | 7 | None |
| `portal_sb` | Support Portal | Section Break | None |  |  |  | None | None |
| `get_started_sections` | Get Started Sections | Code | None |  |  |  | None | None |
| `show_latest_forum_posts` | Show Latest Forum Posts | Check | None |  |  |  | 0 | None |
| `forum_sb` | Forum Posts | Section Break | None |  |  |  | None | None |
| `forum_url` | Forum URL | Data | None |  |  |  | None | None |
| `get_latest_query` | Get Latest Query | Data | None |  |  |  | None | None |
| `response_key_list` | Response Key List | Data | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `post_title_key` | Post Title Key | Data | None |  |  |  | None | None |
| `post_description_key` | Post Description Key | Data | None |  |  |  | None | None |
| `post_route_key` | Post Route Key | Data | None |  |  |  | None | None |
| `post_route_string` | Post Route String | Data | None |  |  |  | None | None |
| `greetings_section_section` | Greetings Section | Section Break | None |  |  |  | None | None |
| `greeting_title` | Greeting Title | Data | None |  |  |  | We're here to help | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `greeting_subtitle` | Greeting Subtitle | Data | None |  |  |  | Browse help topics | None |
| `search_apis_sb` | Search APIs | Section Break | None |  |  |  | None | None |
| `search_apis` | Search APIs | Table | Support Search Source |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/support_settings/support_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Support Settings", {
	refresh: function (frm) {
		//
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
