# Master Control Plan: `Project Update`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Projects User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Data | PROJ-UPD-.YYYY.- |  | ✅ |  | None | None |
| `project` | Project | Link | Project | ✅ |  |  | None | None |
| `sent` | Sent | Check | None |  |  | ✅ | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `date` | Date | Date | None |  |  | ✅ | None | None |
| `time` | Time | Time | None |  |  | ✅ | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `users` | Users | Table | Project User |  |  |  | None | None |
| `amended_from` | Amended From | Link | Project Update |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/project_update/project_update.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Project Update", {
	refresh: function () {},

	onload: function (frm) {
		frm.set_value("naming_series", "UPDATE-.project.-.YY.MM.DD.-.####");
	},

	validate: function (frm) {
		frm.set_value("time", frappe.datetime.now_time());
		frm.set_value("date", frappe.datetime.nowdate());
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
