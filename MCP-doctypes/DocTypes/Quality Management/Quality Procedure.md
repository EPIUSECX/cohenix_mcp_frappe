# Master Control Plan: `Quality Procedure`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Quality Management`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:quality_procedure_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `quality_procedure_name` | Quality Procedure | Data | None | ✅ |  |  | None | None |
| `process_owner` | Process Owner | Link | User |  |  |  | None | None |
| `process_owner_full_name` | Process Owner Full Name | Data | None |  | ✅ |  | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `processes` | Processes | Table | Quality Procedure Process |  |  |  | None | None |
| `sb_00` | Parent | Section Break | None |  |  |  | None | None |
| `parent_quality_procedure` | Parent Procedure | Link | Quality Procedure |  |  |  | None | None |
| `is_group` | Is Group | Check | None |  |  | ✅ | 0 | None |
| `rgt` | Right Index | Int | None |  | ✅ | ✅ | None | None |
| `lft` | Left Index | Int | None |  | ✅ | ✅ | None | None |
| `old_parent` | old_parent | Data | None |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/quality_management/doctype/quality_procedure/quality_procedure.js`
```javascript
// Copyright (c) 2018, Frappe and contributors
// For license information, please see license.txt

frappe.ui.form.on("Quality Procedure", {
	refresh: function (frm) {
		frm.set_query("procedure", "processes", (frm) => {
			return {
				filters: {
					name: ["not in", [frm.parent_quality_procedure, frm.name]],
				},
			};
		});

		frm.set_query("parent_quality_procedure", function () {
			return {
				filters: {
					is_group: 1,
					name: ["!=", frm.doc.name],
				},
			};
		});
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
