# Master Control Plan: `Website Theme`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:theme`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `bootstrap_theme_section` | Theme Configuration | Tab Break | None |  |  |  | None | None |
| `theme` | Theme | Data | None | ✅ |  |  | None | None |
| `module` | Module | Link | Module Def | ✅ |  |  | Website | None |
| `custom` | Custom? | Check | None |  |  |  | 1 | None |
| `google_font` | Google Font | Data | None |  |  |  | None | None |
| `font_size` | Font Size | Data | None |  |  |  | None | None |
| `font_properties` | Font Properties | Data | None |  |  |  | wght@300;400;500;600;700;800 | None |
| `button_rounded_corners` | Button Rounded Corners | Check | None |  |  |  | 1 | None |
| `button_shadows` | Button Shadows | Check | None |  |  |  | 0 | None |
| `button_gradients` | Button Gradients | Check | None |  |  |  | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `primary_color` | Primary Color | Link | Color |  |  |  | None | None |
| `text_color` | Text Color | Link | Color |  |  |  | None | None |
| `light_color` | Light Color | Link | Color |  |  |  | None | None |
| `dark_color` | Dark Color | Link | Color |  |  |  | None | None |
| `background_color` | Background Color | Link | Color |  |  |  | None | None |
| `stylesheet_section` | Stylesheet | Tab Break | None |  |  |  | None | None |
| `custom_overrides` | Custom Overrides | Code | SCSS |  |  |  | None | None |
| `custom_scss` | Custom SCSS | Code | SCSS |  |  |  | None | None |
| `ignored_apps` | Ignored Apps | Table | Website Theme Ignore App |  |  |  | None | None |
| `theme_scss` | Theme | Code | SCSS |  |  | ✅ | None | None |
| `theme_url` | Theme URL | Data | None |  | ✅ | ✅ | None | None |
| `custom_js_section` | Script | Tab Break | None |  |  |  | None | None |
| `js` | JavaScript | Code | JS |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/website_theme/website_theme.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

frappe.ui.form.on("Website Theme", {
	onload_post_render(frm) {
		frm.events.make_app_theme_selector(frm);
	},

	refresh(frm) {
		frm.clear_custom_buttons();
		frm.toggle_display(["module", "custom"], frappe.boot.developer_mode);

		frm.trigger("set_default_theme_button_and_indicator");
		frm.trigger("make_app_theme_selector");

		if (!frm.doc.custom && !frappe.boot.developer_mode) {
			frm.set_read_only();
			frm.disable_save();
		} else {
			frm.enable_save();
		}
		frm.set_df_property("custom_scss", "max_lines", 45);
	},

	set_default_theme_button_and_indicator(frm) {
		frappe.db.get_single_value("Website Settings", "website_theme").then((value) => {
			if (value === frm.doc.name) {
				frm.page.set_indicator(__("Default Theme"), "green");
			} else {
				frm.page.clear_indicator();
				// show set as default button
				if (!frm.is_new() && !frm.is_dirty()) {
					frm.add_custom_button(__("Set as Default Theme"), () => {
						frm.call("set_as_default").then(() => frm.trigger("refresh"));
					});
				}
			}
		});
	},

	make_app_theme_selector(frm) {
		if (frm.app_theme_selector) {
			frm.events.get_installed_apps(frm).then((apps) => {
				let ignored_apps = (frm.doc.ignored_apps || []).map((d) => d.app);
				frm.app_theme_selector
					.get_field("apps")
					.select_options(
						apps.map((d) => d.name).filter((app) => !ignored_apps.includes(app))
					);
			});
			return;
		}
		let $wrapper = frm.get_field("ignored_apps").$wrapper.hide();
		let $body = $("<div>").insertAfter($wrapper);
		let ignored_apps = (frm.doc.ignored_apps || []).map((d) => d.app);
		frm.events.get_installed_apps(frm).then((apps) => {
			if (frm.app_theme_selector) return;
			let form = new frappe.ui.FieldGroup({
				fields: [
					{
						label: __("Include Theme from Apps"),
						fieldname: "apps",
						fieldtype: "MultiCheck",
						columns: 4,
						on_change: () => {
							let value = form
								.get_field("apps")
								.get_unchecked_options()
								.map((app) => ({ app: app }));
							frm.set_value("ignored_apps", value.length ? value : null);
						},
						options: apps.map((app) => ({
							label: app.title,
							value: app.name,
							checked: !ignored_apps.includes(app.name),
						})),
					},
				],
				body: $body,
			});
			form.make();
			frm.app_theme_selector = form;
			$(form.wrapper).find(".form-section").css({
				padding: 0,
				marginLeft: "-15px",
				marginRight: "-15px",
			});
		});
	},

	get_installed_apps(frm) {
		return new Promise((resolve) => {
			if (frm.installed_apps) {
				resolve(frm.installed_apps);
				return;
			}
			return frm.call("get_apps").then((r) => {
				frm.installed_apps = r.message;
				resolve(r.message);
			});
		});
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
