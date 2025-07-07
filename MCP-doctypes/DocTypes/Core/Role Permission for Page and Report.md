# Master Control Plan: `Role Permission for Page and Report`

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
| `set_role_for` | Set Role For | Select | 
Page
Report | ✅ |  |  | None | None |
| `page` | Page | Link | Page |  |  |  | None | None |
| `report` | Report | Link | Report |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `enable_prepared_report` | Enable Prepared Report | Check | None |  |  |  | 0 | None |
| `roles_permission` | Allow Roles | Section Break | None |  |  |  | None | None |
| `roles_html` | Roles Html | HTML | None |  |  |  | None | None |
| `roles` | Roles | Table | Has Role |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/role_permission_for_page_and_report/role_permission_for_page_and_report.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Role Permission for Page and Report", {
	setup: function (frm) {
		frm.trigger("set_queries");
	},

	refresh: function (frm) {
		frm.disable_save();
		frm.role_area.hide();
		frm.events.setup_buttons(frm);
	},

	setup_buttons: function (frm) {
		frm.clear_custom_buttons();
		frm.page.clear_actions();
		if (frm.doc.set_role_for && frm.doc[frappe.model.scrub(frm.doc.set_role_for)]) {
			frm.add_custom_button(__("Reset to defaults"), function () {
				frm.trigger("reset_roles");
			});

			frm.page.set_primary_action(__("Update"), () => {
				frm.trigger("update_report_page_data");
			});
		}
	},

	onload: function (frm) {
		if (!frm.roles_editor) {
			frm.role_area = $(frm.fields_dict.roles_html.wrapper);
			frm.roles_editor = new frappe.RoleEditor(frm.role_area, frm);
		}
	},

	set_queries: function (frm) {
		frm.set_query("page", function () {
			return {
				filters: {
					system_page: 0,
				},
			};
		});
	},

	set_role_for: function (frm) {
		frm.trigger("clear_fields");
		frm.toggle_display("roles_html", false);
	},

	clear_fields: function (frm) {
		var field = frm.doc.set_role_for == "Report" ? "page" : "report";
		frm.set_value(field, "");
	},

	page: function (frm) {
		frm.events.setup_buttons(frm);
		if (frm.doc.page) {
			frm.trigger("set_report_page_data");
		} else {
			frm.trigger("set_role_for");
		}
	},

	report: function (frm) {
		frm.events.setup_buttons(frm);
		if (frm.doc.report) {
			frm.trigger("set_report_page_data");
		} else {
			frm.trigger("set_role_for");
		}
	},

	set_report_page_data: function (frm) {
		frm.toggle_display("roles_html", true);
		frm.role_area.show();

		return frm.call({
			method: "set_report_page_data",
			doc: frm.doc,
			callback: function (r) {
				refresh_field("roles");
				frm.roles_editor.show();
			},
		});
	},

	update_report_page_data: function (frm) {
		frm.trigger("validate_mandatory_fields");
		if (frm.roles_editor) {
			frm.roles_editor.set_roles_in_table();
		}

		return frm.call({
			method: "update_report_page_data",
			doc: frm.doc,
			callback: function (r) {
				refresh_field("roles");
				frm.roles_editor.show();
				frappe.msgprint(__("Successfully Updated"));
			},
		});
	},

	reset_roles: function (frm) {
		frm.trigger("validate_mandatory_fields");
		return frm.call({
			method: "reset_roles",
			doc: frm.doc,
			callback: function (r) {
				refresh_field("roles");
				frm.roles_editor.show();
				frappe.msgprint(__("Successfully Updated"));
			},
		});
	},

	validate_mandatory_fields: function (frm) {
		if (!frm.doc.set_role_for) {
			frappe.throw(__("Mandatory field: set role for"));
		}

		if (frm.doc.set_role_for && !frm.doc[frm.doc.set_role_for.toLocaleLowerCase()]) {
			frappe.throw(__("Mandatory field: {0}", [frm.doc.set_role_for]));
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
