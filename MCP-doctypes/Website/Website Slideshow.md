# Master Control Plan: `Website Slideshow`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:slideshow_name`
- **Description:** Slideshow like display for the website

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `slideshow_name` | Slideshow Name | Data | None | ✅ |  |  | None | None |
| `sb0` | None | Section Break | None |  |  |  | None | Note: For best results,  images must be of the same size and width must be greater than height. |
| `slideshow_items` | Slideshow Items | Table | Website Slideshow Item |  |  |  | None | None |
| `header` | Header | HTML Editor | None |  |  |  | None | This goes above the slideshow. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/website_slideshow/website_slideshow.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

frappe.ui.form.on("Website Slideshow", {
	refresh: (frm) => {
		let intro = frm.doc.__islocal
			? __("First set the name and save the record.")
			: __("Attach files / urls and add in table.");
		frm.set_intro(intro);

		if (frm.is_new()) return;

		frm.add_custom_button(__("Fetch attached images from document"), () => {
			const d = new frappe.ui.Dialog({
				title: __("Fetch Images"),
				fields: [
					{
						label: __("DocType"),
						fieldtype: "Link",
						fieldname: "reference_doctype",
						options: "DocType",
						reqd: 1,
					},
					{
						label: __("Name"),
						fieldtype: "Dynamic Link",
						fieldname: "reference_name",
						options: "reference_doctype",
						reqd: 1,
					},
				],
				primary_action_label: __("Add to table"),
				primary_action: ({ reference_doctype, reference_name }) => {
					frappe.db
						.get_list("File", {
							fields: ["file_url"],
							filters: {
								attached_to_doctype: reference_doctype,
								attached_to_name: reference_name,
							},
						})
						.then((images) => {
							frm.doc.slideshow_items = frm.doc.slideshow_items || [];
							images.forEach((image) => {
								frm.doc.slideshow_items.push({
									image: image.file_url,
								});
							});

							frm.refresh_field("slideshow_items");
							d.hide();
						});
				},
			});

			d.show();
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
