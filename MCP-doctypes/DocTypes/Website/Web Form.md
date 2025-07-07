# Master Control Plan: `Web Form`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `form_tab` | Form | Tab Break | None |  |  |  | None | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `published` | Published | Check | None |  | ✅ |  | 0 | None |
| `column_break_vdhm` | None | Column Break | None |  |  |  | None | None |
| `doc_type` | Select DocType | Link | DocType | ✅ |  |  | None | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `is_standard` | Is standard | Check | None |  |  |  | 0 | None |
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `introduction_text` | Introduction | Text Editor | None |  |  |  | None | None |
| `web_form_fields` | Web Form Fields | Table | Web Form Field |  |  |  | None | None |
| `settings_tab` | Settings | Tab Break | None |  |  |  | None | None |
| `access_control_section` | Access Control | Section Break | None |  |  |  | None | None |
| `anonymous` | Anonymous responses | Check | None |  |  |  | 0 | If enabled, all responses on the web form will be submitted anonymously |
| `login_required` | Login required | Check | None |  |  |  | 0 | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `apply_document_permissions` | Apply document permissions | Check | None |  |  |  | 0 | None |
| `allow_edit` | Allow editing after submit | Check | None |  |  |  | 0 | None |
| `allow_multiple` | Allow multiple responses | Check | None |  |  |  | 0 | None |
| `allow_delete` | Allow delete | Check | None |  |  |  | 0 | None |
| `form_settings_section` | Form Settings | Section Break | None |  |  |  | None | None |
| `allow_incomplete` | Allow incomplete forms | Check | None |  |  |  | 0 | Allow saving if mandatory fields are not filled |
| `allow_comments` | Allow comments | Check | None |  |  |  | 0 | None |
| `allow_print` | Allow print | Check | None |  |  |  | 0 | None |
| `print_format` | Print Format | Link | Print Format |  |  |  | None | None |
| `max_attachment_size` | Max attachment size | Int | None |  |  |  | None | Set size in MB |
| `show_attachments` | Show attachments | Check | None |  |  |  | 0 | None |
| `column_break_hhec` | None | Column Break | None |  |  |  | None | None |
| `hide_navbar` | Hide navbar | Check | None |  |  |  | 0 | None |
| `hide_footer` | Hide footer | Check | None |  |  |  | 0 | None |
| `allowed_embedding_domains` | Allowed embedding domains | Small Text | None |  |  |  | None | Specify the domains or origins that are permitted to embed this form. Enter one domain per line (e.g., https://example.com). If no domains are specified, the form can only be embedded on the same origin. |
| `condition_section` | None | Section Break | None |  |  |  | None | None |
| `condition_description` | Condition description | HTML | <p>Multiple webforms can be created for a single doctype. Add filters specific to this webform to display correct record after submission.</p><p>For Example:</p>
<p>If you create a separate webform every year to capture feedback from employees add a 
 field named year in doctype and add a filter <b>year = 2023</b></p>
 |  |  |  | None | None |
| `condition_json` | Condition JSON | JSON | None |  |  |  | None | None |
| `section_break_3` | List Settings | Section Break | None |  |  |  | None | None |
| `list_setting_message` | List setting message | HTML | None |  |  |  | None | None |
| `show_list` | Show list | Check | None |  |  |  | 0 | None |
| `list_title` | Title | Data | None |  |  |  | None | None |
| `list_columns` | List Columns | Table | Web Form List Column |  |  |  | None | None |
| `section_break_4` | Sidebar Settings | Section Break | None |  |  |  | None | None |
| `show_sidebar` | Show sidebar | Check | None |  |  |  | 0 | None |
| `website_sidebar` | Website Sidebar | Link | Website Sidebar |  |  |  | None | None |
| `customization_tab` | Customization | Tab Break | None |  |  |  | None | None |
| `button_label` | Submit button label | Data | None |  |  |  | Save | None |
| `banner_image` | Banner Image | Attach Image | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `breadcrumbs` | Breadcrumbs | Code | None |  |  |  | None | List as [{"label": _("Jobs"), "route":"jobs"}] |
| `section_break_5` | After Submission | Section Break | None |  |  |  | None | None |
| `success_title` | Success title | Data | None |  |  |  | None | None |
| `success_url` | Success URL | Data | None |  |  |  | None | Go to this URL after completing the form |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `success_message` | Success message | Text | None |  |  |  | None | Message to be displayed on successful completion |
| `meta_section` | Meta | Section Break | None |  |  |  | None | None |
| `meta_title` | Meta title | Data | None |  |  |  | None | None |
| `meta_description` | Meta description | Small Text | None |  |  |  | None | None |
| `column_break_khxs` | None | Column Break | None |  |  |  | None | None |
| `meta_image` | Meta image | Attach Image | None |  |  |  | None | None |
| `section_break_6` | Scripting / Style | Section Break | None |  |  |  | None | None |
| `client_script` | Client script | Code | Javascript |  |  |  | None | For help see <a href="https://frappeframework.com/docs/user/en/guides/portal-development/web-forms" target="_blank">Client Script API and Examples</a> |
| `custom_css` | Custom CSS | Code | CSS |  |  |  | None | None |
| `payments_tab` | Payments | Tab Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `amount_field` | Amount Field | Select | None |  |  |  | None | None |
| `payment_button_help` | Button Help | Text | None |  |  |  | None | None |
| `amount_based_on_field` | Amount Based On Field | Check | None |  |  |  | 0 | None |
| `amount` | Amount | Currency | None |  |  |  | None | None |
| `payments_cb` | None | Column Break | None |  |  |  | None | None |
| `payment_gateway` | Payment Gateway | Link | Payment Gateway |  |  |  | None | None |
| `payment_button_label` | Button Label | Data | None |  |  |  | Buy Now | None |
| `accept_payment` | Accept Payment | Check | None |  |  |  | 0 | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `amount` | Amount | Currency | None |  |  |  | None | None |
| `amount_field` | Amount Field | Select | None |  |  |  | None | None |
| `amount_based_on_field` | Amount Based On Field | Check | None |  |  |  | 0 | None |
| `payments_cb` | None | Column Break | None |  |  |  | None | None |
| `payment_button_help` | Button Help | Text | None |  |  |  | None | None |
| `payment_button_label` | Button Label | Data | None |  |  |  | Buy Now | None |
| `payment_gateway` | Payment Gateway | Link | Payment Gateway |  |  |  | None | None |
| `accept_payment` | Accept Payment | Check | None |  |  |  | 0 | None |
| `payments_tab` | Payments | Tab Break | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 8
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_form/web_form.js`
```javascript
frappe.ui.form.on("Web Form", {
	setup: function () {
		frappe.meta.docfield_map["Web Form Field"].fieldtype.formatter = (value) => {
			const prefix = {
				"Page Break": "--red-600",
				"Section Break": "--blue-600",
				"Column Break": "--yellow-600",
			};
			if (prefix[value]) {
				value = `<span class="bold" style="color: var(${prefix[value]})">${value}</span>`;
			}
			return value;
		};

		frappe.meta.docfield_map["Web Form Field"].fieldname.formatter = (value) => {
			if (!value) return;
			return frappe.unscrub(value);
		};

		frappe.meta.docfield_map["Web Form List Column"].fieldname.formatter = (value) => {
			if (!value) return;
			return frappe.unscrub(value);
		};
	},

	refresh: function (frm) {
		// get iframe url for web form
		frm.sidebar
			.add_user_action(__("Copy embed code"))
			.attr("href", "#")
			.on("click", () => {
				const url = frappe.urllib.get_full_url(frm.doc.route);
				const code = `<iframe src="${url}" style="border: none; width: 100%; height: inherit;"></iframe>`;
				frappe.utils.copy_to_clipboard(code, __("Embed code copied"));
			});

		if (frm.doc.is_standard && !frappe.boot.developer_mode) {
			frm.disable_form();
			frappe.show_alert(
				__("Standard Web Forms can not be modified, duplicate the Web Form instead.")
			);
		}
		render_list_settings_message(frm);

		frm.trigger("set_fields");
		frm.trigger("add_get_fields_button");
		frm.trigger("add_publish_button");
		frm.trigger("render_condition_table");
	},

	login_required: function (frm) {
		render_list_settings_message(frm);
	},

	anonymous: function (frm) {
		if (frm.doc.anonymous) {
			frm.set_value("login_required", 0);
		}
	},

	validate: function (frm) {
		if (!frm.doc.login_required) {
			frm.set_value("allow_multiple", 0);
			frm.set_value("allow_edit", 0);
			frm.set_value("show_list", 0);
		}

		!frm.doc.allow_multiple && frm.set_value("allow_delete", 0);
		frm.doc.allow_multiple && frm.set_value("show_list", 1);

		if (!frm.doc.web_form_fields) {
			frm.scroll_to_field("web_form_fields");
			frappe.throw(__("At least one field is required in Web Form Fields Table"));
		}

		let page_break_count = frm.doc.web_form_fields.filter(
			(f) => f.fieldtype == "Page Break"
		).length;

		if (page_break_count >= 10) {
			frappe.throw(__("There can be only 9 Page Break fields in a Web Form"));
		}
	},

	add_publish_button(frm) {
		frm.add_custom_button(frm.doc.published ? __("Unpublish") : __("Publish"), () => {
			frm.set_value("published", !frm.doc.published);
			frm.save();
		});
	},

	add_get_fields_button(frm) {
		frm.add_custom_button(__("Get Fields"), () => {
			let webform_fieldtypes = frappe.meta
				.get_field("Web Form Field", "fieldtype")
				.options.split("\n");

			let added_fields = (frm.doc.web_form_fields || []).map((d) => d.fieldname);

			get_fields_for_doctype(frm.doc.doc_type).then((fields) => {
				for (let df of fields) {
					let fieldtype = df.fieldtype;
					if (fieldtype == "Tab Break") {
						fieldtype = "Page Break";
					}
					if (
						webform_fieldtypes.includes(fieldtype) &&
						!added_fields.includes(df.fieldname) &&
						!df.hidden
					) {
						frm.add_child("web_form_fields", {
							fieldname: df.fieldname,
							label: df.label,
							fieldtype: fieldtype,
							options: df.options,
							reqd: df.reqd,
							default: df.default,
							read_only: df.read_only,
							precision: df.precision,
							depends_on: df.depends_on,
							mandatory_depends_on: df.mandatory_depends_on,
							read_only_depends_on: df.read_only_depends_on,
						});
					}
				}
				frm.refresh_field("web_form_fields");
				frm.scroll_to_field("web_form_fields");
			});
		});
	},

	set_fields(frm) {
		let doc = frm.doc;

		let update_options = (options) => {
			[frm.fields_dict.web_form_fields.grid, frm.fields_dict.list_columns.grid].forEach(
				(obj) => {
					obj.update_docfield_property("fieldname", "options", options);
				}
			);
		};

		if (!doc.doc_type) {
			update_options([]);
			frm.set_df_property("amount_field", "options", []);
			return;
		}

		update_options([`Fetching fields from ${doc.doc_type}...`]);

		get_fields_for_doctype(doc.doc_type).then((fields) => {
			let as_select_option = (df) => ({
				label: df.label,
				value: df.fieldname,
			});
			update_options(fields.map(as_select_option));

			let currency_fields = fields
				.filter((df) => ["Currency", "Float"].includes(df.fieldtype))
				.map(as_select_option);
			if (!currency_fields.length) {
				currency_fields = [
					{
						label: `No currency fields in ${doc.doc_type}`,
						value: "",
						disabled: true,
					},
				];
			}
			frm.set_df_property("amount_field", "options", currency_fields);
		});
	},

	title: function (frm) {
		if (frm.doc.__islocal) {
			var page_name = frm.doc.title.toLowerCase().replace(/ /g, "-");
			frm.set_value("route", page_name);
		}
	},

	doc_type: function (frm) {
		frm.trigger("set_fields");
	},

	allow_multiple: function (frm) {
		frm.doc.allow_multiple && frm.set_value("show_list", 1);
	},

	before_save: function (frm) {
		let static_filters = JSON.parse(frm.doc.condition_json || "[]");
		frm.set_value("condition_json", JSON.stringify(static_filters));
		frm.trigger("render_condition_table");
	},

	render_condition_table: function (frm) {
		let wrapper = $(frm.get_field("condition_json").wrapper).empty();
		let table = $(`
			<style>
			.table-bordered th, .table-bordered td {
				border: none;
				border-right: 1px solid var(--border-color);
			}
			.table-bordered td {
				border-top: 1px solid var(--border-color);
			}
			.table thead th {
				border-bottom: none;
				font-weight: var(--weight-regular);
			}
			tr th:last-child, tr td:last-child{
				border-right: none;
			}
			thead {
				font-size: var(--text-sm);
				color: var(--gray-600);
				background-color: var(--subtle-fg);
			}
			thead th:first-child {
				border-top-left-radius: 9px;
			}
			thead th:last-child {
				border-top-right-radius: 9px;
			}
			</style>

			<table class="table table-bordered" style="cursor:pointer; margin:0px; border-radius: 10px; border-spacing: 0; border-collapse: separate;">
			<thead>
				<tr>
					<th>${__("Filter")}</th>
					<th style="width: 20%">${__("Condition")}</th>
					<th>${__("Value")}</th>
				</tr>
			</thead>
			<tbody></tbody>
		</table>`).appendTo(wrapper);
		$(`<p class="text-muted small mt-2">${__("Click table to edit")}</p>`).appendTo(wrapper);

		let filters = JSON.parse(frm.doc.condition_json || "[]");
		let filters_set = false;

		let fields = [
			{
				fieldtype: "HTML",
				fieldname: "filter_area",
			},
		];

		if (filters?.length) {
			filters.forEach((filter) => {
				const filter_row = $(`<tr>
							<td>${filter[1]}</td>
							<td>${filter[2] || ""}</td>
							<td>${filter[3]}</td>
						</tr>`);

				table.find("tbody").append(filter_row);
			});
			filters_set = true;
		}

		if (!filters_set) {
			const filter_row = $(`<tr><td colspan="3" class="text-muted text-center">
				${__("Click to Set Filters")}</td></tr>`);
			table.find("tbody").append(filter_row);
		}

		table.on("click", () => {
			let dialog = new frappe.ui.Dialog({
				title: __("Set Filters"),
				fields: fields,
				primary_action: function () {
					let values = this.get_values();
					if (values) {
						this.hide();
						let filters = frm.filter_group.get_filters();
						frm.set_value("condition_json", JSON.stringify(filters));
						frm.trigger("render_condition_table");
					}
				},
				primary_action_label: "Set",
			});

			frm.filter_group = new frappe.ui.FilterGroup({
				parent: dialog.get_field("filter_area").$wrapper,
				doctype: frm.doc.doc_type,
				on_change: () => {},
			});
			filters && frm.filter_group.add_filters_to_filter_group(filters);

			dialog.show();

			dialog.set_values(filters);
		});
	},
});

frappe.ui.form.on("Web Form List Column", {
	fieldname: function (frm, doctype, name) {
		let doc = frappe.get_doc(doctype, name);
		let df = frappe.meta.get_docfield(frm.doc.doc_type, doc.fieldname);
		if (!df) return;
		doc.fieldtype = df.fieldtype;
		doc.label = df.label;
		frm.refresh_field("list_columns");
	},
});

frappe.ui.form.on("Web Form Field", {
	fieldtype: function (frm, doctype, name) {
		let doc = frappe.get_doc(doctype, name);

		if (doc.fieldtype == "Page Break") {
			let page_break_count = frm.doc.web_form_fields.filter(
				(f) => f.fieldtype == "Page Break"
			).length;
			page_break_count >= 10 &&
				frappe.throw(__("There can be only 9 Page Break fields in a Web Form"));
		}

		if (["Section Break", "Column Break", "Page Break"].includes(doc.fieldtype)) {
			doc.fieldname = "";
			doc.label = "";
			doc.options = "";
			frm.refresh_field("web_form_fields");
		}
	},
	fieldname: function (frm, doctype, name) {
		let doc = frappe.get_doc(doctype, name);
		let df = frappe.meta.get_docfield(frm.doc.doc_type, doc.fieldname);
		if (!df) return;

		doc.label = df.label;
		doc.fieldtype = df.fieldtype;
		doc.options = df.options;
		doc.reqd = df.reqd;
		doc.default = df.default;
		doc.read_only = df.read_only;
		doc.depends_on = df.depends_on;
		doc.mandatory_depends_on = df.mandatory_depends_on;
		doc.read_only_depends_on = df.read_only_depends_on;

		frm.refresh_field("web_form_fields");
	},
});

function get_fields_for_doctype(doctype) {
	return new Promise((resolve) => frappe.model.with_doctype(doctype, resolve)).then(() => {
		return frappe.meta.get_docfields(doctype).filter((df) => {
			return (
				(frappe.model.is_value_type(df.fieldtype) &&
					!["lft", "rgt"].includes(df.fieldname)) ||
				["Table", "Table Multiselect"].includes(df.fieldtype) ||
				frappe.model.layout_fields.includes(df.fieldtype)
			);
		});
	});
}

function render_list_settings_message(frm) {
	// render list setting message
	if (frm.fields_dict["list_setting_message"] && !frm.doc.login_required) {
		const go_to_login_required_field = `
			<code class="pointer" title="${__("Go to Login Required field")}">
				${__("login_required")}
			</code>
		`;
		let message = __(
			"Login is required to see web form list view. Enable {0} to see list settings",
			[go_to_login_required_field]
		);
		$(frm.fields_dict["list_setting_message"].wrapper)
			.html($(`<div class="form-message blue">${message}</div>`))
			.find("code")
			.click(() => frm.scroll_to_field("login_required"));
	} else {
		$(frm.fields_dict["list_setting_message"].wrapper).empty();
	}
}

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
