# Master Control Plan: `DocType`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** DocType is a Table / Form in the application.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `form_builder_tab` | Form | Tab Break | None |  |  |  | None | None |
| `form_builder` | Form Builder | HTML | None |  |  |  | None | None |
| `permissions_tab` | Permissions | Tab Break | None |  |  |  | None | None |
| `permissions` | Permissions | Table | DocPerm |  |  |  | None | None |
| `restrict_to_domain` | Restrict To Domain | Link | Domain |  |  |  | None | None |
| `read_only` | User Cannot Search | Check | None |  |  |  | 0 | None |
| `in_create` | User Cannot Create | Check | None |  |  |  | 0 | None |
| `protect_attached_files` | Protect Attached Files | Check | None |  |  |  | 0 | Users are only able to delete attached files if the document is either in draft or if the document is canceled and they are also able to delete the document. |
| `sb1` | Naming | Tab Break | None |  |  |  | None | None |
| `naming_rule` | Naming Rule | Select | 
Set by user
Autoincrement
By fieldname
By "Naming Series" field
Expression
Expression (old style)
Random
UUID
By script |  |  |  | None | None |
| `autoname` | Auto Name | Data | None |  |  |  | None | None |
| `column_break_nexu` | None | Column Break | None |  |  |  | None | None |
| `title_field` | Title Field | Data | None |  |  |  | None | None |
| `allow_rename` | Allow Rename | Check | None |  |  |  | 1 | None |
| `settings_tab` | Settings | Tab Break | None |  |  |  | None | None |
| `sb0` | None | Section Break | None |  |  |  | None | None |
| `module` | Module | Link | Module Def | ✅ |  |  | None | None |
| `is_submittable` | Is Submittable | Check | None |  |  |  | 0 | Once submitted, submittable documents cannot be changed. They can only be Cancelled and Amended. |
| `istable` | Is Child Table | Check | None |  |  |  | 0 | Child Tables are shown as a Grid in other DocTypes |
| `issingle` | Is Single | Check | None |  |  |  | 0 | Single Types have only one record no tables associated. Values are stored in tabSingles |
| `is_tree` | Is Tree | Check | None |  |  |  | 0 | Tree structures are implemented using Nested Set |
| `is_calendar_and_gantt` | Is Calendar and Gantt | Check | None |  |  |  | 0 | Enables Calendar and Gantt views. |
| `editable_grid` | Editable Grid | Check | None |  |  |  | 1 | None |
| `quick_entry` | Quick Entry | Check | None |  |  |  | 0 | Open a dialog with mandatory fields to create a new record quickly. There must be at least one mandatory field to show in dialog. |
| `grid_page_length` | Grid Page Length | Int | None |  |  |  | 50 | None |
| `rows_threshold_for_grid_search` | Rows Threshold for Grid Search | Int | None |  |  |  | 0 | None |
| `cb01` | None | Column Break | None |  |  |  | None | None |
| `track_changes` | Track Changes | Check | None |  |  |  | 0 | If enabled, changes to the document are tracked and shown in timeline |
| `track_seen` | Track Seen | Check | None |  |  |  | 0 | If enabled, the document is marked as seen, the first time a user opens it |
| `track_views` | Track Views | Check | None |  |  |  | 0 | If enabled, document views are tracked, this can happen multiple times |
| `custom` | Custom? | Check | None |  |  |  | 0 | None |
| `beta` | Beta | Check | None |  |  |  | 0 | None |
| `is_virtual` | Is Virtual | Check | None |  |  |  | 0 | None |
| `queue_in_background` | Queue in Background (BETA) | Check | None |  |  |  | 0 | Enabling this will submit documents in background |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `form_settings_section` | Form Settings | Section Break | None |  |  |  | None | None |
| `image_field` | Image Field | Data | None |  |  |  | None | Must be of type "Attach Image" |
| `timeline_field` | Timeline Field | Data | None |  |  |  | None | Comments and Communications will be associated with this linked document |
| `nsm_parent_field` | Parent Field (Tree) | Data | None |  |  |  | None | None |
| `max_attachments` | Max Attachments | Int | None |  |  |  | None | None |
| `documentation` | Documentation Link | Data | None |  |  |  | None | URL for documentation or help |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `hide_toolbar` | Hide Sidebar, Menu, and Comments | Check | None |  |  |  | 0 | None |
| `allow_copy` | Hide Copy | Check | None |  |  |  | 0 | None |
| `allow_import` | Allow Import (via Data Import Tool) | Check | None |  |  |  | 0 | None |
| `allow_events_in_timeline` | Allow events in timeline | Check | None |  |  |  | 0 | None |
| `allow_auto_repeat` | Allow Auto Repeat | Check | None |  |  |  | 0 | None |
| `make_attachments_public` | Make Attachments Public by Default | Check | None |  |  |  | 0 | None |
| `view_settings` | View Settings | Section Break | None |  |  |  | None | None |
| `show_title_field_in_link` | Show Title in Link Fields | Check | None |  |  |  | 0 | None |
| `translated_doctype` | Translate Link Fields | Check | None |  |  |  | 0 | None |
| `search_fields` | Search Fields | Data | None |  |  |  | None | None |
| `default_print_format` | Default Print Format | Data | None |  |  |  | None | None |
| `sort_field` | Default Sort Field | Data | None |  |  |  | creation | None |
| `sort_order` | Default Sort Order | Select | ASC
DESC |  |  |  | DESC | None |
| `default_view` | Default View | Select | None |  |  |  | None | None |
| `force_re_route_to_default_view` | Force Re-route to Default View | Check | None |  |  |  | 0 | None |
| `column_break_29` | None | Column Break | None |  |  |  | None | None |
| `document_type` | Show in Module Section | Select | 
Document
Setup
System
Other |  |  |  | None | None |
| `icon` | Icon | Data | None |  |  |  | None | None |
| `color` | Color | Data | None |  |  |  | None | None |
| `show_preview_popup` | Show Preview Popup | Check | None |  |  |  | 0 | None |
| `show_name_in_global_search` | Make "name" searchable in Global Search | Check | None |  |  |  | 0 | None |
| `email_settings_sb` | Email Settings | Section Break | None |  |  |  | None | None |
| `default_email_template` | Default Email Template | Link | Email Template |  |  |  | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `email_append_to` | Allow document creation via Email | Check | None |  |  |  | 0 | None |
| `sender_field` | Sender Email Field | Data | None |  |  |  | None | None |
| `sender_name_field` | Sender Name Field | Data | None |  |  |  | None | None |
| `subject_field` | Subject Field | Data | None |  |  |  | None | None |
| `fields_tab` | Fields | Tab Break | None |  |  |  | None | None |
| `fields_section` | Fields | Section Break | None |  |  |  | None | None |
| `fields` | Fields | Table | DocField |  |  |  | None | None |
| `actions_section` | Actions | Tab Break | None |  |  |  | None | None |
| `actions` | Document Actions | Table | DocType Action |  |  |  | None | None |
| `links_section` | Links | Tab Break | None |  |  |  | None | None |
| `links` | Document Links | Table | DocType Link |  |  |  | None | None |
| `document_states_section` | States | Tab Break | None |  |  |  | None | None |
| `states` | Document States | Table | DocType State |  |  |  | None | None |
| `web_view` | Web View | Tab Break | None |  |  |  | None | None |
| `has_web_view` | Has Web View | Check | None |  |  |  | 0 | None |
| `allow_guest_to_view` | Allow Guest to View | Check | None |  |  |  | 0 | None |
| `index_web_pages_for_search` | Index Web Pages for Search | Check | None |  |  |  | 1 | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `is_published_field` | Is Published Field | Data | None |  |  |  | None | None |
| `website_search_field` | Website Search Field | Data | None |  |  |  | None | None |
| `advanced` | Advanced | Section Break | None |  | ✅ |  | None | None |
| `engine` | Database Engine | Select | InnoDB
MyISAM |  |  |  | InnoDB | None |
| `migration_hash` | None | Data | None |  | ✅ |  | None | None |
| `row_format` | Row Format | Select | Dynamic
Compressed |  | ✅ |  | Dynamic | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 5

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/doctype/doctype.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

frappe.ui.form.on("DocType", {
	onload: function (frm) {
		if (frm.is_new() && !frm.doc?.fields) {
			frappe.listview_settings["DocType"].new_doctype_dialog();
		}
		frm.call("check_pending_migration");
	},

	before_save: function (frm) {
		let form_builder = frappe.form_builder;
		if (form_builder?.store) {
			let fields = form_builder.store.update_fields();

			// if fields is a string, it means there is an error
			if (typeof fields === "string") {
				frappe.throw(fields);
			}
		}
	},

	after_save: function (frm) {
		if (
			frappe.form_builder &&
			frappe.form_builder.doctype === frm.doc.name &&
			frappe.form_builder.store
		) {
			frappe.form_builder.store.fetch();
		}
	},

	refresh: function (frm) {
		frm.set_query("role", "permissions", function (doc) {
			if (doc.custom && frappe.session.user != "Administrator") {
				return {
					query: "frappe.core.doctype.role.role.role_query",
				};
			}
		});

		if (frappe.session.user !== "Administrator" || !frappe.boot.developer_mode) {
			if (frm.is_new()) {
				frm.set_value("custom", 1);
			}
			frm.toggle_enable("custom", 0);
			frm.toggle_enable("is_virtual", 0);
			frm.toggle_enable("beta", 0);
		}

		if (!frm.is_new() && !frm.doc.istable) {
			const button_text = frm.doc.issingle
				? __("Go to {0}", [__(frm.doc.name)])
				: __("Go to {0} List", [__(frm.doc.name)]);
			frm.add_custom_button(button_text, () => {
				window.open(`/app/${frappe.router.slug(frm.doc.name)}`);
			});
		}

		const customize_form_link = `<a href="/app/customize-form">${__("Customize Form")}</a>`;
		if (!frappe.boot.developer_mode && !frm.doc.custom) {
			// make the document read-only
			frm.set_read_only();
			frm.dashboard.clear_comment();
			frm.dashboard.add_comment(
				__("DocTypes cannot be modified, please use {0} instead", [customize_form_link]),
				"blue",
				true
			);
		} else if (frappe.boot.developer_mode) {
			frm.dashboard.clear_comment();
			let msg = __(
				"This site is running in developer mode. Any change made here will be updated in code."
			);
			frm.dashboard.add_comment(msg, "yellow", true);
		}

		if (frm.is_new()) {
			frm.events.set_default_permission(frm);
			frm.set_value("default_view", "List");
		} else {
			frm.toggle_enable("engine", 0);
		}

		// set label for "In List View" for child tables
		frm.get_docfield("fields", "in_list_view").label = frm.doc.istable
			? __("In Grid View")
			: __("In List View");

		frm.cscript.autoname(frm);
		frm.cscript.set_naming_rule_description(frm);
		frm.trigger("setup_default_views");

		render_form_builder(frm);
	},

	istable: (frm) => {
		if (frm.doc.istable && frm.is_new()) {
			frm.set_value("default_view", null);
		} else if (!frm.doc.istable && !frm.is_new()) {
			frm.events.set_default_permission(frm);
		}
	},

	set_default_permission: (frm) => {
		if (!(frm.doc.permissions && frm.doc.permissions.length)) {
			frm.add_child("permissions", { role: "System Manager" });
		}
	},

	is_tree: (frm) => {
		frm.trigger("setup_default_views");
	},

	is_calendar_and_gantt: (frm) => {
		frm.trigger("setup_default_views");
	},

	setup_default_views: (frm) => {
		frappe.model.set_default_views_for_doctype(frm.doc.name, frm);
	},

	on_tab_change: (frm) => {
		let current_tab = frm.get_active_tab().label;

		if (current_tab === "Form") {
			frm.footer.wrapper.hide();
			frm.form_wrapper.find(".form-message").hide();
			frm.form_wrapper.addClass("mb-1");
		} else {
			frm.footer.wrapper.show();
			frm.form_wrapper.find(".form-message").show();
			frm.form_wrapper.removeClass("mb-1");
		}
	},
});

frappe.ui.form.on("DocField", {
	form_render(frm, doctype, docname) {
		frm.trigger("setup_fetch_from_fields", doctype, docname);
	},

	fieldtype: function (frm) {
		frm.trigger("max_attachments");
	},

	fields_add: (frm) => {
		frm.trigger("setup_default_views");
	},
});

function render_form_builder(frm) {
	if (frappe.form_builder && frappe.form_builder.doctype === frm.doc.name) {
		frappe.form_builder.setup_page_actions();
		frappe.form_builder.store.fetch();
		return;
	}

	if (frappe.form_builder) {
		frappe.form_builder.wrapper = $(frm.fields_dict["form_builder"].wrapper);
		frappe.form_builder.frm = frm;
		frappe.form_builder.doctype = frm.doc.name;
		frappe.form_builder.customize = false;
		frappe.form_builder.init(true);
		frappe.form_builder.store.fetch();
	} else {
		frappe.require("form_builder.bundle.js").then(() => {
			frappe.form_builder = new frappe.ui.FormBuilder({
				wrapper: $(frm.fields_dict["form_builder"].wrapper),
				frm: frm,
				doctype: frm.doc.name,
				customize: false,
			});
		});
	}
}

extend_cscript(cur_frm.cscript, new frappe.model.DocTypeController({ frm: cur_frm }));

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
