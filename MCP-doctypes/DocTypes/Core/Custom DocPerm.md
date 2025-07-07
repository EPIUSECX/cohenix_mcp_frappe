# Master Control Plan: `Custom DocPerm`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `parent` | Reference Document Type | Data | None |  |  | ✅ | None | None |
| `role_and_level` | Role and Level | Section Break | None |  |  |  | None | None |
| `role` | Role | Link | Role | ✅ |  |  | None | None |
| `if_owner` | If user is the owner | Check | None |  |  |  | 0 | Apply this rule if the User is the Owner |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `permlevel` | Level | Int | None |  |  |  | 0 | None |
| `section_break_4` | Permissions | Section Break | None |  |  |  | None | None |
| `select` | Select | Check | None |  |  |  | 0 | None |
| `read` | Read | Check | None |  |  |  | 1 | None |
| `write` | Write | Check | None |  |  |  | 0 | None |
| `create` | Create | Check | None |  |  |  | 0 | None |
| `delete` | Delete | Check | None |  |  |  | 0 | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `submit` | Submit | Check | None |  |  |  | 0 | None |
| `cancel` | Cancel | Check | None |  |  |  | 0 | None |
| `amend` | Amend | Check | None |  |  |  | 0 | None |
| `additional_permissions` | Additional Permissions | Section Break | None |  |  |  | None | None |
| `report` | Report | Check | None |  |  |  | 0 | None |
| `export` | Export | Check | None |  |  |  | 1 | None |
| `import` | Import | Check | None |  |  |  | 0 | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `share` | Share | Check | None |  |  |  | 0 | None |
| `print` | Print | Check | None |  |  |  | 0 | None |
| `email` | Email | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/custom_docperm/custom_docperm.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Custom DocPerm", {
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
