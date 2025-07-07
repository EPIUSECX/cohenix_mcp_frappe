# Master Control Plan: `Blog Post`

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
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Blogger | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `blog_category` | Blog Category | Link | Blog Category | ✅ |  |  | None | None |
| `blogger` | Blogger | Link | Blogger | ✅ |  |  | None | None |
| `route` | Route | Data | None |  |  |  | None | None |
| `read_time` | Read Time | Int | None |  | ✅ | ✅ | None | in minutes |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `published_on` | Published On | Date | None |  |  |  | None | None |
| `published` | Published | Check | None |  | ✅ |  | 0 | None |
| `featured` | Featured | Check | None |  |  |  | 0 | None |
| `hide_cta` | Hide CTA | Check | None |  | ✅ |  | 0 | None |
| `enable_email_notification` | Enable Email Notification | Check | None |  |  |  | 1 | Enable email notification for any comment or likes received on your Blog Post. |
| `disable_comments` | Disable Comments | Check | None |  |  |  | 0 | None |
| `disable_likes` | Disable Likes | Check | None |  |  |  | 0 | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `blog_intro` | Blog Intro | Small Text | None |  |  |  | None | Description for listing page, in plain text, only a couple of lines. (max 200 characters) |
| `content_type` | Content Type | Select | Markdown
Rich Text
HTML | ✅ |  |  | Markdown | None |
| `content` | Content | Text Editor | None |  |  |  | None | None |
| `content_md` | Content (Markdown) | Markdown Editor | None |  |  |  | None | None |
| `content_html` | Content (HTML) | HTML Editor | None |  |  |  | None | None |
| `email_sent` | Email Sent | Check | None |  | ✅ |  | 0 | None |
| `meta_tags` | Meta Tags | Section Break | None |  |  |  | None | None |
| `meta_title` | Meta Title | Data | None |  |  |  | None | None |
| `meta_description` | Meta Description | Small Text | None |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `meta_image` | Meta Image | Attach Image | None |  |  |  | None | None |
| `section_break_20` | None | Section Break | None |  |  |  | None | None |
| `google_preview` | Google Snippet Preview | HTML | None |  |  | ✅ | None | This is an example Google SERP Preview. |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/blog_post/blog_post.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Blog Post", {
	refresh: function (frm) {
		frappe.db.get_single_value("Blog Settings", "show_cta_in_blog").then((value) => {
			frm.set_df_property("hide_cta", "hidden", !value);
		});

		frm.trigger("add_publish_button");

		generate_google_search_preview(frm);
	},
	title: function (frm) {
		generate_google_search_preview(frm);
		frm.trigger("set_route");
	},
	meta_description: function (frm) {
		generate_google_search_preview(frm);
	},
	blog_intro: function (frm) {
		generate_google_search_preview(frm);
	},
	blog_category(frm) {
		frm.trigger("set_route");
	},
	set_route(frm) {
		if (frm.doc.route) return;
		if (frm.doc.title && frm.doc.blog_category) {
			frm.call("make_route").then((r) => {
				frm.set_value("route", r.message);
			});
		}
	},
	add_publish_button(frm) {
		frm.add_custom_button(frm.doc.published ? __("Unpublish") : __("Publish"), () => {
			frm.set_value("published", !frm.doc.published);
			frm.save();
		});
	},
});

function generate_google_search_preview(frm) {
	if (!(frm.doc.meta_title || frm.doc.title)) return;
	let google_preview = frm.get_field("google_preview");
	let seo_title = (frm.doc.meta_title || frm.doc.title).slice(0, 60);
	let seo_description = (frm.doc.meta_description || frm.doc.blog_intro || "").slice(0, 160);
	let date = frm.doc.published_on ? moment(frm.doc.published_on).format("ll") + "-" : "";
	let route_array = frm.doc.route ? frm.doc.route.split("/") : [];
	route_array.pop();

	google_preview.html(`
		<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400&display=swap" rel="stylesheet">
			<div style="font-family: Open Sans; padding: 15px; border: 1px solid #d1d8dd !important; border-radius: 6px;">
				<cite style="font-size: 14px; padding-top: 1px; line-height: 1.3; color: #202124; font-style: normal;">
					${frappe.boot.sitename}
					<span style="color: #5f6368;"> › ${route_array.join(" › ")}</span>
				</cite>
				<div style="font-size: 20px; line-height: 1.3; color: #1a0dab; padding-top: 4px; margin-bottom: 3px;">
						${seo_title}
				</div>
				<p style="color: #545454; max-width: 48em; line-height: 1.58; font-size:14px;">
					<span style="color: #70757a;">${date}</span> ${seo_description}
				</p>
			</div>
	`);
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
