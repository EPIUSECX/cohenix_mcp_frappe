# Master Control Plan: `Web Page`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Page to show on the website


### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_title` | Content | Tab Break | None |  |  |  | None | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `dynamic_route` | Dynamic Route | Check | None |  |  |  | 0 | Map route parameters into form variables. Example <code>/project/&lt;name&gt;</code> |
| `cb1` | None | Column Break | None |  |  |  | None | None |
| `published` | Published | Check | None |  |  |  | 1 | None |
| `module` | Module (for export) | Link | Module Def |  |  |  | None | None |
| `sb1` | Content | Section Break | None |  |  |  | None | None |
| `content_type` | Content Type | Select | Rich Text
Markdown
HTML
Page Builder
Slideshow |  |  |  | Page Builder | None |
| `slideshow` | Slideshow | Link | Website Slideshow |  |  |  | None | None |
| `dynamic_template` | Dynamic Template | Check | None |  |  |  | 0 | None |
| `main_section` | Main Section | Text Editor | None |  |  |  | None | None |
| `main_section_md` | Main Section (Markdown) | Markdown Editor | None |  |  |  | None | None |
| `main_section_html` | Main Section (HTML) | HTML Editor | None |  |  |  | None | None |
| `page_blocks` | Page Building Blocks | Table | Web Page Block |  |  |  | None | None |
| `scripting_tab` | Scripting | Tab Break | None |  |  |  | None | None |
| `context_section` | Context | Section Break | None |  |  |  | None | None |
| `context_script` | Context Script | Code | Python |  |  |  | None | <p>Set context before rendering a template. Example:</p><p>
</p><div><pre><code>
context.project = frappe.get_doc("Project", frappe.form_dict.name)
</code></pre></div> |
| `custom_javascript` | Script | Section Break | None |  |  |  | None | None |
| `javascript` | Javascript | Code | Javascript |  |  |  | None | None |
| `custom_css` | Style | Tab Break | None |  |  |  | None | None |
| `insert_style` | Insert Style | Check | None |  |  |  | 0 | None |
| `text_align` | Text Align | Select | Left
Center
Right |  |  |  | None | None |
| `css` | CSS | Code | CSS |  |  |  | None | None |
| `full_width` | Full Width | Check | None |  |  |  | 1 | None |
| `show_title` | Show Title | Check | None |  |  |  | 0 | None |
| `settings` | Settings | Tab Break | None |  |  |  | None | None |
| `publishing_dates_section` | Publishing Dates | Section Break | None |  |  |  | None | None |
| `start_date` | Start Date | Datetime | None |  |  |  | None | None |
| `column_break_30` | None | Column Break | None |  |  |  | None | None |
| `end_date` | End Date | Datetime | None |  |  |  | None | None |
| `metatags_section` | Meta Tags | Section Break | None |  |  |  | None | None |
| `meta_title` | Title | Data | None |  |  |  | None | None |
| `meta_description` | Description | Small Text | None |  |  |  | None | None |
| `meta_image` | Image | Attach Image | None |  |  |  | None | None |
| `set_meta_tags` | Add Custom Tags | Button | None |  |  |  | None | None |
| `section_break_17` | Sidebar and Comments | Section Break | None |  |  |  | None | None |
| `show_sidebar` | Show Sidebar | Check | None |  |  |  | 0 | None |
| `idx` | Priority | Int | None |  |  |  | None | 0 is highest |
| `website_sidebar` | Website Sidebar | Link | Website Sidebar |  |  |  | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `enable_comments` | Enable Comments | Check | None |  |  |  | 0 | None |
| `sb2` | Header and Breadcrumbs | Section Break | None |  |  |  | None | None |
| `header` | Header | HTML Editor | None |  |  |  | None | HTML for header section. Optional |
| `breadcrumbs` | Breadcrumbs | Code | JSON |  |  |  | None | List as [{"label": _("Jobs"), "route":"jobs"}] |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_page/web_page.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

frappe.ui.form.on("Web Page", {
	layout: function (frm) {
		if (frm.is_new()) {
			if (frm.doc.insert_code) {
				if (!frm.doc.javascript) {
					frm.set_value("javascript", `frappe.ready(() => {\n\t\n});`);
				}
			}
		}
	},
	insert_code: function (frm) {
		frm.events.layout(frm);
	},
	onload: function (frm) {
		frm.set_query("web_template", "page_blocks", function () {
			return {
				filters: {
					type: ["in", ["Section", "Component"]],
				},
			};
		});
	},
	validate: function (frm) {
		if (frm.doc.title && !frm.doc.route) {
			frm.set_value("route", frappe.scrub(frm.doc.title, "-"));
		}
	},
	refresh: function (frm) {
		if (frm.doc.template_path) {
			frm.set_read_only();
		} else {
			frm.events.layout(frm);
		}
	},
	published: function (frm) {
		// If current date is before end date,
		// and web page is manually unpublished,
		// set end date to current date.
		if (!frm.doc.published && frm.doc.end_date) {
			var end_date = frappe.datetime.str_to_obj(frappe.datetime.now_datetime());

			// Set date a few seconds in the future to avoid throwing
			// start and end date validation error
			end_date.setSeconds(end_date.getSeconds() + 5);

			frm.set_value("end_date", end_date);
		}
	},
	set_meta_tags(frm) {
		frappe.utils.set_meta_tag(frm.doc.route);
	},
});

frappe.ui.form.on("Web Page Block", {
	edit_values(frm, cdt, cdn) {
		let row = frm.selected_doc;
		let values = JSON.parse(row.web_template_values || "{}");
		open_web_template_values_editor(row.web_template, values).then((new_values) => {
			frappe.model.set_value(cdt, cdn, "web_template_values", JSON.stringify(new_values));
		});
	},
});

frappe.tour["Web Page"] = [
	{
		fieldname: "title",
		title: __("Title of the page"),
		description: __(
			"This title will be used as the title of the webpage as well as in meta tags"
		),
	},
	{
		fieldname: "published",
		title: __("Makes the page public"),
		description: __(
			"Checking this will publish the page on your website and it'll be visible to everyone."
		),
	},
	{
		fieldname: "route",
		title: __("URL of the page"),
		description: __(
			"This will be automatically generated when you publish the page, you can also enter a route yourself if you wish"
		),
	},
	{
		fieldname: "content_type",
		title: __("Content type for building the page"),
		description: `${__("You can select one from the following,")} <br>
					<ul>
						<li><b>${__("Rich Text")}</b>: ${__("Standard rich text editor with controls")}</li>
						<li><b>${__("Markdown")}</b>: ${__("Github flavoured markdown syntax")}</li>
						<li><b>${__("HTML")}</b>: ${__("HTML with jinja support")}</li>
						<li><b>${__("Page Builder")}</b>: ${__("Frappe page builder using components")}</li>
					</ul>
					`,
	},
	{
		fieldname: "insert_code",
		title: __("Client Script"),
		description: __(
			"Checking this will show a text area where you can write custom javascript that will run on this page."
		),
	},
	{
		fieldname: "meta_title",
		title: __("Meta title for SEO"),
		description: __(
			"By default the title is used as meta title, adding a value here will override it."
		),
	},
	{
		fieldname: "meta_title",
		title: __("Meta Title"),
		description: __(
			"By default the title is used as meta title, adding a value here will override it."
		),
	},
	{
		fieldname: "meta_description",
		title: __("Meta Description"),
		description: __(
			"The meta description is an HTML attribute that provides a brief summary of a web page. Search engines such as Google often display the meta description in search results, which can influence click-through rates."
		),
	},
	{
		fieldname: "meta_image",
		title: __("Meta Image"),
		description: __(
			"The meta image is unique image representing the content of the page. Images for this Card should be at least 280px in width, and at least 150px in height."
		),
	},
];

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
