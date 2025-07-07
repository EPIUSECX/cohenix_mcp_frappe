# Master Control Plan: `Desktop Icon`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
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
| `module_name` | Module Name | Data | None |  |  |  | None | None |
| `label` | Label | Data | None |  |  |  | None | None |
| `standard` | Standard | Check | None |  |  |  | 0 | None |
| `custom` | Custom | Check | None |  |  | ✅ | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `app` | App | Data | None |  |  | ✅ | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `category` | Category | Data | None |  |  |  | None | None |
| `hidden` | Hidden | Check | None |  |  |  | 0 | None |
| `blocked` | Blocked | Check | None |  |  |  | 0 | None |
| `force_show` | Force Show | Check | None |  |  | ✅ | 0 | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `type` | Type | Select | module
list
link
page
query-report |  |  |  | None | None |
| `_doctype` | _doctype | Link | DocType |  |  |  | None | None |
| `_report` | _report | Link | Report |  |  |  | None | None |
| `link` | Link | Small Text | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `color` | Color | Data | None |  |  |  | None | None |
| `icon` | Icon | Data | None |  |  |  | None | None |
| `reverse` | Reverse Icon Color | Check | None |  |  |  | 0 | None |
| `idx` | Idx | Int | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/desktop_icon/desktop_icon.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Desktop Icon", {
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
