# Master Control Plan: `Navbar Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
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
| `logo_section` | Application Logo | Section Break | None |  |  |  | None | None |
| `app_logo` | Application Logo | Attach Image | None |  |  |  | None | None |
| `section_break_2` | Dropdowns | Section Break | None |  |  |  | None | None |
| `settings_dropdown` | Settings Dropdown | Table | Navbar Item |  |  |  | None | None |
| `help_dropdown` | Help Dropdown | Table | Navbar Item |  |  |  | None | None |
| `announcements_section` | Announcements | Section Break | None |  |  |  | None | None |
| `announcement_widget` | Announcement Widget | Text Editor | None |  |  |  | None | These announcements will appear inside a dismissible alert below the Navbar. |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/navbar_settings/navbar_settings.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Navbar Settings", {
	after_save: function (frm) {
		frappe.ui.toolbar.clear_cache();
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
