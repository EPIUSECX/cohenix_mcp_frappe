# Master Control Plan: `Error Log`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `seen` | Seen | Check | None |  | ✅ |  | 0 | None |
| `reference_doctype` | Reference DocType | Link | DocType |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `reference_name` | Reference Name | Data | None |  |  | ✅ | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `method` | Title | Data | None |  |  | ✅ | None | None |
| `error` | Error | Code | None |  |  | ✅ | None | None |
| `trace_id` | Trace ID | Data | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/error_log/error_log.js`
```javascript
// Copyright (c) 2022, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Error Log", {
	refresh: function (frm) {
		frm.disable_save();

		if (frm.doc.reference_doctype && frm.doc.reference_name) {
			frm.add_custom_button(__("Show Related Errors"), function () {
				frappe.set_route("List", "Error Log", {
					reference_doctype: frm.doc.reference_doctype,
					reference_name: frm.doc.reference_name,
				});
			});
			frm.add_custom_button(__("Open reference document"), function () {
				frappe.set_route("Form", frm.doc.reference_doctype, frm.doc.reference_name);
			});
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Database Storage Usage By Tables` | Script Report | Core |



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
