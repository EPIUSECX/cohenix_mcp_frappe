# Master Control Plan: `Audit Trail`

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
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `doctype_name` | DocType | Link | DocType | ✅ |  |  | None | None |
| `column_break_peck` | None | Column Break | None |  |  |  | None | None |
| `document` | Document | Dynamic Link | doctype_name | ✅ |  |  | None | None |
| `section_break_dfrx` | Date Range | Section Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | None | None |
| `column_break_ytzm` | None | Column Break | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `section_break_gppi` | None | Section Break | None |  |  |  | None | None |
| `version_table` | version_table | HTML | None |  | ✅ |  | None | None |
| `rows_added_section` | Rows Added | Section Break | None |  | ✅ |  | None | None |
| `rows_added` | None | HTML | None |  |  |  | None | None |
| `rows_removed_section` | Rows Removed | Section Break | None |  | ✅ |  | None | None |
| `rows_removed` | None | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/audit_trail/audit_trail.js`
```javascript
// Copyright (c) 2023, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Audit Trail", {
	refresh(frm) {
		let prev_route = frappe.get_prev_route();
		if (
			prev_route.length > 2 &&
			prev_route[0] == "Form" &&
			!prev_route.includes("Audit Trail")
		) {
			frm.set_value("doctype_name", prev_route[1]);
			frm.set_value("document", prev_route[2]);
			frm.set_value("start_date", "");
			frm.set_value("end_date", "");
			if (frm.doc.doctype_name && frm.doc.document)
				frm.events.get_audit_trail_for_document(frm);
		}

		frm.page.clear_indicator();

		frm.disable_save();

		frm.set_query("doctype_name", () => {
			return {
				filters: {
					track_changes: 1,
					is_submittable: 1,
				},
			};
		});

		frm.set_query("document", () => {
			let filters = {
				amended_from: ["!=", ""],
			};
			if (frm.doc.start_date && frm.doc.end_date)
				filters["creation"] = ["between", [frm.doc.start_date, frm.doc.end_date]];
			else if (frm.doc.start_date) filters["creation"] = [">=", frm.doc.start_date];
			else if (frm.doc.end_date) filters["creation"] = ["<=", frm.doc.end_date];
			return {
				filters: filters,
			};
		});

		frm.page.set_primary_action("Compare", () => {
			frm.events.get_audit_trail_for_document(frm);
		});
	},

	start_date(frm) {
		if (frm.doc.start_date > frm.doc.end_date) {
			frm.doc.end_date = "";
			frm.refresh_fields();
		}

		frappe.db
			.get_value(frm.doc.doctype_name, frm.doc.document, "creation")
			.then((creation) => {
				if (frappe.datetime.obj_to_str(creation) < frm.doc.start_date) {
					frm.doc.document = "";
					frm.refresh_fields();
				}
			});
	},

	end_date(frm) {
		frappe.db
			.get_value(frm.doc.doctype_name, frm.doc.document, "creation")
			.then((creation) => {
				if (frappe.datetime.obj_to_str(creation) > frm.doc.end_date) {
					frm.doc.document = "";
					frm.refresh_fields();
				}
			});
	},

	get_audit_trail_for_document(frm) {
		frm.call({
			doc: frm.doc,
			method: "compare_document",
			callback: function (r) {
				let document_names = r.message[0];
				let changed_fields = r.message[1];
				frm.events.render_changed_fields(frm, document_names, changed_fields);
				frm.events.render_rows_added_or_removed(frm, changed_fields);
			},
		});
	},

	render_changed_fields(frm, document_names, changed_fields) {
		let render_dict = {
			documents: document_names,
			changed: changed_fields.changed,
			row_changed: changed_fields.row_changed,
		};
		$(frappe.render_template("audit_trail", render_dict)).appendTo(
			frm.fields_dict.version_table.$wrapper.empty()
		);
		frm.set_df_property("version_table", "hidden", 0);
	},

	render_rows_added_or_removed(frm, changed_fields) {
		let added_or_removed = {
			rows_added: changed_fields.added,
			rows_removed: changed_fields.removed,
		};

		let hide_section = 0;
		let section_dict = {};

		for (let key in added_or_removed) {
			hide_section = 0;
			section_dict = {
				added_or_removed: added_or_removed[key],
			};
			$(frappe.render_template("audit_trail_rows_added_removed", section_dict)).appendTo(
				frm.fields_dict[key].$wrapper.empty()
			);

			if (!frm.fields_dict[key].disp_area.innerHTML.includes("<table")) hide_section = 1;
			frm.set_df_property(key + "_section", "hidden", hide_section);
		}
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
