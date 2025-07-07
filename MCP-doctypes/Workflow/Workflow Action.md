# Master Control Plan: `Workflow Action`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Workflow`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `status` | Status | Select | Open
Completed |  |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_doctype |  |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `workflow_state` | Workflow State | Data | None |  | ✅ |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `completed_by_role` | Completed By Role | Link | Role |  |  | ✅ | None | None |
| `completed_by` | Completed By User | Link | User |  |  | ✅ | None | None |
| `permitted_roles` | Permitted Roles | Table MultiSelect | Workflow Action Permitted Role |  |  | ✅ | None | None |
| `user` | User | Link | User |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/workflow/doctype/workflow_action/workflow_action.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Workflow Action", {
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
