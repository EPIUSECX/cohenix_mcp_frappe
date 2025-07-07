# Master Control Plan: `About Us Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Settings for the About Us Page

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `page_title` | Page Title | Data | None |  |  |  | None | None |
| `company_introduction` | Company Introduction | Text Editor | None |  |  |  | None | Introduce your company to the website visitor. |
| `sb0` | Org History | Section Break | None |  |  |  | None | None |
| `company_history_heading` | Org History Heading | Data | None |  |  |  | None | "Company History" |
| `company_history` | Org History | Table | Company History |  |  |  | None | None |
| `sb1` | Team Members | Section Break | None |  |  |  | None | None |
| `team_members_heading` | Team Members Heading | Data | None |  |  |  | None | "Team Members" or "Management" |
| `team_members_subtitle` | Team Members Subtitle | Small Text | None |  |  |  | None | None |
| `team_members` | Team Members | Table | About Us Team Member |  |  |  | None | None |
| `footer` | Footer | Text Editor | None |  |  |  | None | More content for the bottom of the page. |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/about_us_settings/about_us_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("About Us Settings", {
	refresh: function (frm) {
		frm.set_intro(__('Link for About Us Page is "/about".'));
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
