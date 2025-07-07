# Master Control Plan: `Kanban Board`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:kanban_board_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `kanban_board_name` | Kanban Board Name | Data | None | ✅ |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType | ✅ |  |  | None | None |
| `field_name` | Field Name | Select | None | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `private` | Private | Check | None |  |  | ✅ | 0 | None |
| `show_labels` | Show Labels | Check | None |  |  | ✅ | 0 | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `columns` | Columns | Table | Kanban Board Column |  |  |  | None | None |
| `filters` | Filters | Code | JSON |  |  | ✅ | None | None |
| `fields` | Fields | Code | JSON |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/kanban_board/kanban_board.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Kanban Board", {
	onload: function (frm) {
		frm.trigger("reference_doctype");
	},
	refresh: function (frm) {
		if (frm.is_new()) return;
		frm.add_custom_button("Show Board", function () {
			frappe.set_route("List", frm.doc.reference_doctype, "Kanban", frm.doc.name);
		});
	},
	reference_doctype: function (frm) {
		// set field options
		if (!frm.doc.reference_doctype) return;

		frappe.model.with_doctype(frm.doc.reference_doctype, function () {
			var options = $.map(frappe.get_meta(frm.doc.reference_doctype).fields, function (d) {
				if (
					d.fieldname &&
					d.fieldtype === "Select" &&
					frappe.model.no_value_type.indexOf(d.fieldtype) === -1
				) {
					return d.fieldname;
				}
				return null;
			});
			frm.set_df_property("field_name", "options", options);
			frm.get_field("field_name").refresh();
		});
	},
	field_name: function (frm) {
		var field = frappe.meta.get_field(frm.doc.reference_doctype, frm.doc.field_name);
		frm.doc.columns = [];
		field.options &&
			field.options.split("\n").forEach(function (o) {
				o = o.trim();
				if (!o) return;
				var d = frm.add_child("columns");
				d.column_name = o;
			});
		frm.refresh();
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
