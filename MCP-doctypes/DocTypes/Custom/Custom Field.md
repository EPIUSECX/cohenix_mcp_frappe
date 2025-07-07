# Master Control Plan: `Custom Field`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Custom`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Adds a custom field to a DocType

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_system_generated` | Is System Generated | Check | None |  |  | ✅ | 0 | None |
| `dt` | DocType | Link | DocType | ✅ |  |  | None | None |
| `module` | Module (for export) | Link | Module Def |  |  |  | None | None |
| `label` | Label | Data | None |  |  |  | None | None |
| `placeholder` | Placeholder | Data | None |  |  |  | None | None |
| `label_help` | Label Help | HTML | None |  |  |  | None | None |
| `fieldname` | Fieldname | Data | None |  |  | ✅ | None | None |
| `insert_after` | Insert After | Select | None |  |  |  | None | Select the label after which you want to insert new field. |
| `length` | Length | Int | None |  |  |  | None | None |
| `link_filters` | Link Filters | JSON | None |  | ✅ |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `fieldtype` | Field Type | Select | Autocomplete
Attach
Attach Image
Barcode
Button
Check
Code
Color
Column Break
Currency
Data
Date
Datetime
Duration
Dynamic Link
Float
Fold
Geolocation
Heading
HTML
HTML Editor
Icon
Image
Int
JSON
Link
Long Text
Markdown Editor
Password
Percent
Phone
Read Only
Rating
Section Break
Select
Signature
Small Text
Tab Break
Table
Table MultiSelect
Text
Text Editor
Time | ✅ |  |  | Data | None |
| `precision` | Precision | Select | 
0
1
2
3
4
5
6
7
8
9 |  |  |  | None | Set non-standard precision for a Float or Currency field |
| `hide_seconds` | Hide Seconds | Check | None |  |  |  | 0 | None |
| `hide_days` | Hide Days | Check | None |  |  |  | 0 | None |
| `options` | Options | Small Text | None |  |  |  | None | None |
| `sort_options` | Sort Options | Check | None |  |  |  | 0 | None |
| `fetch_from` | Fetch From | Small Text | None |  |  |  | None | None |
| `fetch_if_empty` | Fetch on Save if Empty | Check | None |  |  |  | 0 | If unchecked, the value will always be re-fetched on save. |
| `options_help` | Options Help | HTML | None |  |  |  | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `collapsible` | Collapsible | Check | None |  |  |  | 0 | None |
| `collapsible_depends_on` | Collapsible Depends On | Code | None |  |  |  | None | None |
| `default` | Default Value | Text | None |  |  |  | None | None |
| `depends_on` | Depends On | Code | None |  |  |  | None | None |
| `mandatory_depends_on` | Mandatory Depends On | Code | None |  |  |  | None | None |
| `read_only_depends_on` | Read Only Depends On | Code | None |  |  |  | None | None |
| `properties` | None | Column Break | None |  |  |  | None | None |
| `non_negative` | Non Negative | Check | None |  |  |  | 0 | None |
| `reqd` | Is Mandatory Field | Check | None |  |  |  | 0 | None |
| `unique` | Unique | Check | None |  |  |  | 0 | None |
| `is_virtual` | Is Virtual | Check | None |  |  |  | 0 | None |
| `read_only` | Read Only | Check | None |  |  |  | 0 | None |
| `ignore_user_permissions` | Ignore User Permissions | Check | None |  |  |  | 0 | None |
| `hidden` | Hidden | Check | None |  |  |  | 0 | None |
| `print_hide` | Print Hide | Check | None |  |  |  | 0 | None |
| `print_hide_if_no_value` | Print Hide If No Value | Check | None |  |  |  | 0 | None |
| `print_width` | Print Width | Data | None |  | ✅ |  | None | None |
| `no_copy` | No Copy | Check | None |  |  |  | 0 | None |
| `allow_on_submit` | Allow on Submit | Check | None |  |  |  | 0 | None |
| `in_list_view` | In List View | Check | None |  |  |  | 0 | None |
| `in_standard_filter` | In Standard Filter | Check | None |  |  |  | 0 | None |
| `in_global_search` | In Global Search | Check | None |  |  |  | 0 | None |
| `in_preview` | In Preview | Check | None |  |  |  | 0 | None |
| `bold` | Bold | Check | None |  |  |  | 0 | None |
| `report_hide` | Report Hide | Check | None |  |  |  | 0 | None |
| `search_index` | Index | Check | None |  | ✅ |  | 0 | None |
| `allow_in_quick_entry` | Allow in Quick Entry | Check | None |  |  |  | 0 | None |
| `ignore_xss_filter` | Ignore XSS Filter | Check | None |  |  |  | 0 | Don't HTML Encode HTML tags like &lt;script&gt; or just characters like &lt; or &gt;, as they could be intentionally used in this field |
| `translatable` | Translatable | Check | None |  |  |  | 0 | None |
| `hide_border` | Hide Border | Check | None |  |  |  | 0 | None |
| `show_dashboard` | Show Dashboard | Check | None |  |  |  | 0 | None |
| `description` | Field Description | Text | None |  |  |  | None | None |
| `permlevel` | Permission Level | Int | None |  |  |  | 0 | None |
| `width` | Width | Data | None |  |  |  | None | None |
| `columns` | Columns | Int | None |  |  |  | None | Number of columns for a field in a List View or a Grid (Total Columns should be less than 11) |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/custom_field/custom_field.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

// Refresh
// --------

frappe.ui.form.on("Custom Field", {
	setup: function (frm) {
		frm.set_query("dt", function (doc) {
			var filters = [
				["DocType", "issingle", "=", 0],
				["DocType", "custom", "=", 0],
				["DocType", "name", "not in", frappe.model.core_doctypes_list],
				["DocType", "restrict_to_domain", "in", frappe.boot.active_domains],
			];
			if (frappe.session.user !== "Administrator") {
				filters.push(["DocType", "module", "not in", ["Core", "Custom"]]);
			}
			return {
				filters: filters,
			};
		});
	},
	refresh: function (frm) {
		frm.toggle_enable("dt", frm.doc.__islocal);
		frm.trigger("dt");
		frm.toggle_reqd("label", !frm.doc.fieldname);
		frm.trigger("add_rename_field");

		if (frm.doc.is_system_generated) {
			frm.dashboard.add_comment(
				__(
					"<strong>Warning:</strong> This field is system generated and may be overwritten by a future update. Modify it using {0} instead.",
					[
						frappe.utils.get_form_link(
							"Customize Form",
							"Customize Form",
							true,
							__("Customize Form"),
							{
								doc_type: frm.doc.dt,
							}
						),
					]
				),
				"yellow",
				true
			);
		}
	},
	dt: function (frm) {
		if (!frm.doc.dt) {
			set_field_options("insert_after", "");
			return;
		}
		var insert_after = frm.doc.insert_after || null;
		return frappe.call({
			method: "frappe.custom.doctype.custom_field.custom_field.get_fields_label",
			args: { doctype: frm.doc.dt, fieldname: frm.doc.fieldname },
			callback: function (r) {
				if (r) {
					if (r._server_messages && r._server_messages.length) {
						frm.set_value("dt", "");
					} else {
						set_field_options("insert_after", r.message);
						var fieldnames = $.map(r.message, function (v) {
							return v.value;
						});

						if (insert_after == null || !fieldnames.includes(insert_after)) {
							insert_after = fieldnames[-1];
						}

						frm.set_value("insert_after", insert_after);
					}
				}
			},
		});
	},
	label: function (frm) {
		if (frm.doc.label && frappe.utils.has_special_chars(frm.doc.label)) {
			frm.fields_dict["label_help"].disp_area.innerHTML =
				'<font color = "red">' + __("Special Characters are not allowed") + "</font>";
			frm.set_value("label", "");
		} else {
			frm.fields_dict["label_help"].disp_area.innerHTML = "";
		}
	},
	fieldtype: function (frm) {
		if (frm.doc.fieldtype == "Link") {
			frm.fields_dict["options_help"].disp_area.innerHTML = __(
				"Name of the Document Type (DocType) you want this field to be linked to. e.g. Customer"
			);
		} else if (frm.doc.fieldtype == "Select") {
			frm.fields_dict["options_help"].disp_area.innerHTML =
				__("Options for select. Each option on a new line.") +
				" " +
				__("e.g.:") +
				"<br>" +
				__("Option 1") +
				"<br>" +
				__("Option 2") +
				"<br>" +
				__("Option 3") +
				"<br>";
		} else if (frm.doc.fieldtype == "Dynamic Link") {
			frm.fields_dict["options_help"].disp_area.innerHTML = __(
				"Fieldname which will be the DocType for this link field."
			);
		} else {
			frm.fields_dict["options_help"].disp_area.innerHTML = "";
		}
	},
	add_rename_field(frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(__("Rename Fieldname"), () => {
				frappe.prompt(
					{
						fieldtype: "Data",
						label: __("Fieldname"),
						fieldname: "fieldname",
						reqd: 1,
						default: frm.doc.fieldname,
					},
					function (data) {
						frappe
							.xcall(
								"frappe.custom.doctype.custom_field.custom_field.rename_fieldname",
								{
									custom_field: frm.doc.name,
									fieldname: data.fieldname,
								}
							)
							.then(() => frm.reload());
					},
					__("Rename Fieldname"),
					__("Rename")
				);
			});
		}
	},
});

frappe.utils.has_special_chars = function (t) {
	var iChars = "!@#$%^&*()+=-[]\\';,./{}|\":<>?";
	for (var i = 0; i < t.length; i++) {
		if (iChars.indexOf(t.charAt(i)) != -1) {
			return true;
		}
	}
	return false;
};

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
