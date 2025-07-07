# Master Control Plan: `Print Format`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Printing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `doc_type` | DocType | Link | DocType | ✅ |  |  | None | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `default_print_language` | Default Print Language | Link | Language |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `standard` | Standard | Select | No
Yes | ✅ |  |  | No | None |
| `custom_format` | Custom Format | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `pdf_generator` | PDF Generator | Select | wkhtmltopdf |  |  |  | wkhtmltopdf | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `print_format_type` | Print Format Type | Select | Jinja
JS |  |  |  | Jinja | None |
| `raw_printing` | Raw Printing | Check | None |  |  |  | 0 | None |
| `html` | HTML | Code | Jinja |  |  |  | None | None |
| `raw_commands` | Raw Commands | Code | Jinja |  |  |  | None | Any string-based printer languages can be used. Writing raw commands requires knowledge of the printer's native language provided by the printer manufacturer. Please refer to the developer manual provided by the printer manufacturer on how to write their native commands. These commands are rendered on the server side using the Jinja Templating Language. |
| `section_break_9` | Style Settings | Section Break | None |  |  |  | None | None |
| `margin_top` | Margin Top | Float | None |  |  |  | 15 | None |
| `margin_bottom` | Margin Bottom | Float | None |  |  |  | 15 | None |
| `margin_left` | Margin Left | Float | None |  |  |  | 15 | None |
| `margin_right` | Margin Right | Float | None |  |  |  | 15 | None |
| `align_labels_right` | Align Labels to the Right | Check | None |  |  |  | 0 | None |
| `show_section_headings` | Show Section Headings | Check | None |  |  |  | 0 | None |
| `line_breaks` | Show Line Breaks after Sections | Check | None |  |  |  | 0 | None |
| `absolute_value` | Show Absolute Values | Check | None |  |  |  | 0 | If checked, negative numeric values of Currency, Quantity or Count would be shown as positive |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `font_size` | Font Size | Int | None |  | ✅ |  | 14 | None |
| `font` | Google Font | Data | None |  |  |  | None | None |
| `page_number` | Page Number | Select | Hide
Top Left
Top Center
Top Right
Bottom Left
Bottom Center
Bottom Right |  |  |  | Hide | None |
| `css_section` | None | Section Break | None |  |  |  | None | None |
| `css` | Custom CSS | Code | CSS |  |  |  | None | None |
| `custom_html_help` | Custom HTML Help | HTML | <h3>Custom CSS Help</h3>

<p>Notes:</p>

<ol>
<li>All field groups (label + value) are set attributes <code>data-fieldtype</code> and <code>data-fieldname</code></li>
<li>All values are given class <code>value</code></li>
<li>All Section Breaks are given class <code>section-break</code></li>
<li>All Column Breaks are given class <code>column-break</code></li>
</ol>

<h4>Examples</h4>

<p>1. Left align integers</p>

<pre><code>[data-fieldtype="Int"] .value { text-align: left; }</code></pre>

<p>1. Add border to sections except the last section</p>

<pre><code>.section-break { padding: 30px 0px; border-bottom: 1px solid #eee; }
.section-break:last-child { padding-bottom: 0px; border-bottom: 0px;  }</code></pre>
 |  |  |  | None | None |
| `section_break_13` | None | Section Break | None |  |  |  | None | None |
| `print_format_help` | Print Format Help | HTML | <h3>Print Format Help</h3>
<hr>
<h4>Introduction</h4>
<p>Print Formats are rendered on the server side using the Jinja Templating Language. All forms have access to the <code>doc</code> object which contains information about the document that is being formatted. You can also access common utilities via the <code>frappe</code> module.</p>
<p>For styling, the Boostrap CSS framework is provided and you can enjoy the full range of classes.</p>
<hr>
<h4>References</h4>
<ol>
	<li><a href="http://jinja.pocoo.org/docs/templates/" target="_blank">Jinja Templating Language</a></li>
	<li><a href="http://getbootstrap.com" target="_blank">Bootstrap CSS Framework</a></li>
</ol>
<hr>
<h4>Example</h4>
<pre><code>&lt;h3&gt;{{ doc.select_print_heading or "Invoice" }}&lt;/h3&gt;
&lt;div class="row"&gt;
	&lt;div class="col-md-3 text-right"&gt;Customer Name&lt;/div&gt;
	&lt;div class="col-md-9"&gt;{{ doc.customer_name }}&lt;/div&gt;
&lt;/div&gt;
&lt;div class="row"&gt;
	&lt;div class="col-md-3 text-right"&gt;Date&lt;/div&gt;
	&lt;div class="col-md-9"&gt;{{ doc.get_formatted("invoice_date") }}&lt;/div&gt;
&lt;/div&gt;
&lt;table class="table table-bordered"&gt;
	&lt;tbody&gt;
		&lt;tr&gt;
			&lt;th&gt;Sr&lt;/th&gt;
			&lt;th&gt;Item Name&lt;/th&gt;
			&lt;th&gt;Description&lt;/th&gt;
			&lt;th class="text-right"&gt;Qty&lt;/th&gt;
			&lt;th class="text-right"&gt;Rate&lt;/th&gt;
			&lt;th class="text-right"&gt;Amount&lt;/th&gt;
		&lt;/tr&gt;
		{%- for row in doc.items -%}
		&lt;tr&gt;
			&lt;td style="width: 3%;"&gt;{{ row.idx }}&lt;/td&gt;
			&lt;td style="width: 20%;"&gt;
				{{ row.item_name }}
				{% if row.item_code != row.item_name -%}
				&lt;br&gt;Item Code: {{ row.item_code}}
				{%- endif %}
			&lt;/td&gt;
			&lt;td style="width: 37%;"&gt;
				&lt;div style="border: 0px;"&gt;{{ row.description }}&lt;/div&gt;&lt;/td&gt;
			&lt;td style="width: 10%; text-align: right;"&gt;{{ row.qty }} {{ row.uom or row.stock_uom }}&lt;/td&gt;
			&lt;td style="width: 15%; text-align: right;"&gt;{{
				row.get_formatted("rate", doc) }}&lt;/td&gt;
			&lt;td style="width: 15%; text-align: right;"&gt;{{
				row.get_formatted("amount", doc) }}&lt;/td&gt;
		&lt;/tr&gt;
		{%- endfor -%}
	&lt;/tbody&gt;
&lt;/table&gt;</code></pre>
<hr>
<h4>Common Functions</h4>
<table class="table table-bordered">
	<tbody>
		<tr>
			<td style="width: 30%;"><code>doc.get_formatted("[fieldname]", [parent_doc])</code></td>
			<td>Get document value formatted as Date, Currency, etc. Pass parent <code>doc</code> for currency type fields.</td>
		</tr>
		<tr>
			<td style="width: 30%;"><code>frappe.db.get_value("[doctype]", "[name]", "fieldname")</code></td>
			<td>Get value from another document.</td>
		</tr>
	</tbody>
</table>
 |  |  |  | None | None |
| `format_data` | Format Data | Code | None |  | ✅ |  | None | None |
| `print_format_builder` | Print Format Builder | Check | None |  | ✅ |  | 0 | None |
| `print_format_builder_beta` | Print Format Builder Beta | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/printing/doctype/print_format/print_format.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Print Format", "onload", function (frm) {
	frm.add_fetch("doc_type", "module", "module");
});

frappe.ui.form.on("Print Format", {
	refresh: function (frm) {
		frm.set_intro("");
		frm.toggle_enable(["html", "doc_type", "module"], false);
		if (frappe.session.user === "Administrator" || frm.doc.standard === "No") {
			frm.toggle_enable(["html", "doc_type", "module"], true);
			frm.enable_save();
		}

		if (frm.doc.standard === "Yes" && frappe.session.user !== "Administrator") {
			frm.set_intro(__("Please duplicate this to make changes"));
		}
		frm.trigger("render_buttons");
		frm.toggle_display("standard", frappe.boot.developer_mode);
		frm.trigger("hide_absolute_value_field");
	},
	render_buttons: function (frm) {
		frm.page.clear_inner_toolbar();
		if (!frm.is_new()) {
			if (!frm.doc.custom_format) {
				frm.add_custom_button(__("Edit Format"), function () {
					if (!frm.doc.doc_type) {
						frappe.msgprint(__("Please select DocType first"));
						return;
					}
					if (frm.doc.print_format_builder_beta) {
						frappe.set_route("print-format-builder-beta", frm.doc.name);
					} else {
						frappe.set_route("print-format-builder", frm.doc.name);
					}
				});
			} else if (frm.doc.custom_format && !frm.doc.raw_printing) {
				frm.set_df_property("html", "reqd", 1);
			}
			if (frappe.model.can_write("Customize Form")) {
				frappe.model.with_doctype(frm.doc.doc_type, function () {
					let current_format = frappe.get_meta(frm.doc.doc_type).default_print_format;
					if (current_format == frm.doc.name) {
						return;
					}

					frm.add_custom_button(__("Set as Default"), function () {
						frappe.call({
							method: "frappe.printing.doctype.print_format.print_format.make_default",
							args: {
								name: frm.doc.name,
							},
							callback: function () {
								frm.refresh();
							},
						});
					});
				});
			}
		}
	},
	custom_format: function (frm) {
		var value = frm.doc.custom_format ? 0 : 1;
		frm.set_value("align_labels_right", value);
		frm.set_value("show_section_headings", value);
		frm.set_value("line_breaks", value);
		frm.trigger("render_buttons");
	},
	doc_type: function (frm) {
		frm.trigger("hide_absolute_value_field");
	},
	hide_absolute_value_field: function (frm) {
		// TODO: make it work with frm.doc.doc_type
		// Problem: frm isn't updated in some random cases
		const doctype = locals[frm.doc.doctype][frm.doc.name].doc_type;
		if (doctype) {
			frappe.model.with_doctype(doctype, () => {
				const meta = frappe.get_meta(doctype);
				const has_int_float_currency_field = meta.fields.filter((df) =>
					["Int", "Float", "Currency"].includes(df.fieldtype)
				);
				frm.toggle_display("absolute_value", has_int_float_currency_field.length);
			});
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
