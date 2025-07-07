# Master Control Plan: `Website Settings`

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
| Website Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `home_tab` | Home | Tab Break | None |  |  |  | None | None |
| `sb0` | Landing Page | Section Break | None |  |  |  | None | None |
| `home_page` | Home Page | Data | None |  |  |  | None | Link that is the website home page. Standard Links (home, login, products, blog, about, contact) |
| `cb4` | None | Column Break | None |  |  |  | None | None |
| `title_prefix` | Title Prefix | Data | None |  |  |  | None | Show title in browser window as "Prefix - title" |
| `misc_section` | Login Page | Section Break | None |  |  |  | None | None |
| `app_name` | App Name | Data | None |  |  |  | Frappe | None |
| `disable_signup` | Disable signups | Check | None |  |  |  | 1 | New users will have to be manually registered by system managers. |
| `show_footer_on_login` | Show footer on login | Check | None |  |  |  | 0 | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `app_logo` | App Logo | Attach Image | None |  |  |  | None | None |
| `section_break_6` | Theme | Section Break | None |  |  |  | None | None |
| `website_theme` | Website Theme | Link | Website Theme |  |  |  | Standard | None |
| `website_theme_image` | Website Theme Image | Image | website_theme_image_link |  | ✅ |  | None | None |
| `website_theme_image_link` | Website Theme image link | Code | None |  | ✅ |  | None | None |
| `navbar_tab` | Navbar | Tab Break | None |  |  |  | None | None |
| `brand` | Brand | Section Break | None |  |  |  | None | None |
| `banner_image` | Brand Image | Attach Image | None |  |  |  | None | Select an image of approx width 150px with a transparent background for best results. |
| `splash_image` | Splash Image | Attach Image | None |  |  |  | None | None |
| `brand_html` | Brand HTML | Code | HTML |  |  |  | None | Brand is what appears on the top-left of the toolbar. If it is an image, make sure it
has a transparent background and use the &lt;img /&gt; tag. Keep size as 200px x 30px |
| `set_banner_from_image` | Set Banner from Image | Button | None |  |  |  | None | None |
| `favicon` | FavIcon | Attach | None |  |  |  | None | An icon file with .ico extension. Should be 16 x 16 px. Generated using a favicon generator. [favicon-generator.org] |
| `top_bar` | Navbar | Section Break | None |  |  |  | None | None |
| `top_bar_items` | Top Bar Items | Table | Top Bar Item |  |  |  | None | None |
| `hide_login` | Hide Login | Check | None |  |  |  | 0 | None |
| `navbar_search` | Include Search in Top Bar | Check | None |  |  |  | 0 | None |
| `show_language_picker` | Show Language Picker | Check | None |  |  |  | 0 | None |
| `navbar_template_section` | Navbar Template | Section Break | None |  |  |  | None | None |
| `navbar_template` | Navbar Template | Link | Web Template |  |  |  | None | None |
| `navbar_template_values` | Navbar Template Values | Code | JSON |  | ✅ |  | None | None |
| `edit_navbar_template_values` | Edit Values | Button | None |  |  |  | None | None |
| `call_to_action` | Call To Action | Data | None |  |  |  | None | None |
| `call_to_action_url` | Call To Action URL | Data | None |  |  |  | None | None |
| `banner` | Banner | Section Break | None |  |  |  | None | None |
| `banner_html` | Banner HTML | Code | HTML |  |  |  | None | Banner is above the Top Menu Bar. |
| `footer_tab` | Footer | Tab Break | None |  |  |  | None | None |
| `footer` | Footer Items | Section Break | None |  |  |  | None | None |
| `footer_items` | Footer Items | Table | Top Bar Item |  |  |  | None | None |
| `footer_details_section` | Footer Details | Section Break | None |  |  |  | None | None |
| `copyright` | Copyright | Data | None |  |  |  | None | None |
| `footer_logo` | Footer Logo | Attach Image | None |  |  |  | None | None |
| `hide_footer_signup` | Hide footer signup | Check | None |  |  |  | 0 | None |
| `column_break_37` | None | Column Break | None |  |  |  | None | None |
| `address` | Address | Small Text | None |  |  |  | None | Address and other legal information you may want to put in the footer. |
| `footer_powered` | Footer "Powered By" | Small Text | None |  |  |  | None | None |
| `custom_footer_section` | Custom Footer | Section Break | None |  |  |  | None | None |
| `footer_template` | Footer Template | Link | Web Template |  |  |  | None | None |
| `footer_template_values` | Footer Template Values | Code | JSON |  | ✅ |  | None | None |
| `edit_footer_template_values` | Edit Values | Button | None |  |  |  | None | None |
| `integrations` | Integrations | Tab Break | None |  |  |  | None | None |
| `analytics_section` | Analytics | Section Break | None |  |  |  | None | None |
| `enable_view_tracking` | Enable in-app website tracking | Check | None |  |  |  | 0 | None |
| `enable_google_indexing` | Enable Google indexing | Check | None |  |  |  | 0 | To use Google Indexing, enable <a href="/app/google-settings">Google Settings</a>. |
| `authorize_api_indexing_access` | Authorize API Indexing  Access | Button | None |  |  |  | None | None |
| `indexing_refresh_token` | Indexing refresh token | Data | None |  | ✅ | ✅ | None | None |
| `indexing_authorization_code` | Indexing authorization code | Data | None |  | ✅ | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `google_analytics_id` | Google Analytics ID | Data | None |  |  |  | None | None |
| `google_analytics_anonymize_ip` | Google Analytics anonymise IP | Check | None |  |  |  | 1 | None |
| `account_deletion_settings_section` | Account Deletion Settings | Section Break | None |  |  |  | None | None |
| `auto_account_deletion` | Automatically delete account within (hours) | Int | None |  |  |  | 72 | None |
| `show_account_deletion_link` | Show account deletion link in My Account page | Check | None |  |  |  | 0 | None |
| `section_break_38` | Header, Robots | Tab Break | None |  |  |  | None | None |
| `subdomain` | Subdomain | Small Text | None |  |  | ✅ | None | Sub-domain provided by erpnext.com |
| `head_html` | &lt;head&gt; HTML | Code | HTML |  |  |  | None | Added HTML in the &lt;head&gt; section of the web page, primarily used for website verification and SEO |
| `robots_txt` | Robots.txt | Code | None |  |  |  | None | None |
| `redirects_tab` | Redirects | Tab Break | None |  |  |  | None | None |
| `route_redirects` | Route Redirects | Table | Website Route Redirect |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/website_settings/website_settings.js`
```javascript
frappe.ui.form.on("Website Settings", {
	setup(frm) {
		frm.set_query("navbar_template", () => ({
			filters: {
				type: "Navbar",
			},
		}));
		frm.set_query("footer_template", () => ({
			filters: {
				type: "Footer",
			},
		}));
	},

	refresh: function (frm) {
		frm.add_custom_button(__("View Website"), () => {
			window.open("/", "_blank");
		});
	},

	set_banner_from_image: function (frm) {
		if (!frm.doc.banner_image) {
			frappe.msgprint(__("Select a Brand Image first."));
		}
		frm.set_value("brand_html", "<img src='" + frm.doc.banner_image + "'>");
	},

	onload_post_render: function (frm) {
		frm.trigger("set_parent_label_options");
	},

	set_parent_label_options: function (frm) {
		frm.fields_dict.top_bar_items.grid.update_docfield_property(
			"parent_label",
			"options",
			frm.events.get_parent_options(frm, "top_bar_items")
		);
	},

	set_parent_label_options_footer: function (frm) {
		frm.fields_dict.footer_items.grid.update_docfield_property(
			"parent_label",
			"options",
			frm.events.get_parent_options(frm, "footer_items")
		);
	},

	authorize_api_indexing_access: function (frm) {
		frappe.call({
			method: "frappe.website.doctype.website_settings.google_indexing.authorize_access",
			args: {
				reauthorize: frm.doc.indexing_authorization_code ? 1 : 0,
			},
			callback: function (r) {
				if (!r.exc) {
					frm.save();
					window.open(r.message.url);
				}
			},
		});
	},

	enable_view_tracking: function (frm) {
		frappe.boot.website_tracking_enabled = frm.doc.enable_view_tracking;
	},

	set_parent_options: function (frm, doctype, name) {
		var item = frappe.get_doc(doctype, name);
		if (item.parentfield === "top_bar_items") {
			frm.trigger("set_parent_label_options");
		} else if (item.parentfield === "footer_items") {
			frm.trigger("set_parent_label_options_footer");
		}
	},

	get_parent_options: function (frm, table_field) {
		var items = frm.doc[table_field] || [];
		var main_items = [""];
		for (var i in items) {
			var d = items[i];
			if (!d.url && d.label) {
				main_items.push(d.label);
			}
		}
		return main_items.join("\n");
	},

	edit_navbar_template_values(frm) {
		frm.events.edit_template_values(frm, "navbar_template");
	},

	edit_footer_template_values(frm) {
		frm.events.edit_template_values(frm, "footer_template");
	},

	edit_template_values(frm, template_field) {
		let values_field = template_field + "_values";
		let template = frm.doc[template_field];
		if (!template) {
			frappe.show_alert(__("Please select {0}", [frm.get_docfield(template_field).label]));
			return;
		}
		let values = JSON.parse(frm.doc[values_field] || "{}");
		open_web_template_values_editor(template, values).then((new_values) => {
			frm.set_value(values_field, JSON.stringify(new_values));
		});
	},
});

frappe.ui.form.on("Top Bar Item", {
	top_bar_items_delete(frm) {
		frm.events.set_parent_label_options(frm);
	},

	footer_items_add(frm, cdt, cdn) {
		frappe.model.set_value(cdt, cdn, "right", 0);
	},

	footer_items_delete(frm) {
		frm.events.set_parent_label_options_footer(frm);
	},

	parent_label: function (frm, doctype, name) {
		frm.events.set_parent_options(frm, doctype, name);
	},

	url: function (frm, doctype, name) {
		frm.events.set_parent_options(frm, doctype, name);
	},

	label: function (frm, doctype, name) {
		frm.events.set_parent_options(frm, doctype, name);
	},
});

frappe.tour["Website Settings"] = [
	{
		fieldname: "enable_view_tracking",
		title: __("Enable Tracking Page Views"),
		description: __(
			"Checking this will enable tracking page views for blogs, web pages, etc."
		),
	},
	{
		fieldname: "disable_signup",
		title: __("Disable Signup for your site"),
		description: __(
			"Check this if you don't want users to sign up for an account on your site. Users won't get desk access unless you explicitly provide it."
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
