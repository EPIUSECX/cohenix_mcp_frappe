# Master Control Plan: `List View Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `disable_count` | Disable Count | Check | None |  |  |  | 0 | None |
| `disable_comment_count` | Disable Comment Count | Check | None |  |  |  | 0 | None |
| `disable_sidebar_stats` | Disable Sidebar Stats | Check | None |  |  |  | 0 | None |
| `disable_auto_refresh` | Disable Auto Refresh | Check | None |  |  |  | 0 | None |
| `allow_edit` | Allow Bulk Editing | Check | None |  |  |  | 0 | Allow editing even if the doctype has a workflow set up.

Does nothing if a workflow isn't set up. |
| `disable_automatic_recency_filters` | Disable Automatic Recency Filters | Check | None |  |  |  | 0 | None |
| `total_fields` | Maximum Number of Fields | Select | 
4
5
6
7
8
9
10 |  |  |  | None | None |
| `fields_html` | Fields | HTML | None |  |  |  | None | None |
| `fields` | Fields | Code | None |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/list_view_settings/list_view_settings.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("List View Settings", {
	// refresh: function(frm) {
	// }
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
