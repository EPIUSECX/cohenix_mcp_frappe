# Master Control Plan: `Email Group`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Newsletter Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `total_subscribers` | Total Subscribers | Int | None |  |  | ✅ | 0 | None |
| `sign_up_and_confirmation_section` | Sign Up and Confirmation | Section Break | None |  |  |  | None | None |
| `confirmation_email_template` | Confirmation Email Template | Link | Email Template |  |  |  | None | None |
| `welcome_email_template` | Welcome Email Template | Link | Email Template |  |  |  | None | None |
| `welcome_url` | Welcome URL | Data | URL |  |  |  | None | Redirect to this URL after successful confirmation. |
| `add_query_parameters` | Add Query Parameters | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_group/email_group.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Email Group", {
	refresh: function (frm) {
		if (!frm.is_new()) {
			frm.add_custom_button(
				__("Import Subscribers"),
				function () {
					frappe.prompt(
						{
							fieldtype: "Select",
							options: frm.doc.__onload.import_types,
							label: __("Import Email From"),
							fieldname: "doctype",
							reqd: 1,
						},
						function (data) {
							frappe.call({
								method: "frappe.email.doctype.email_group.email_group.import_from",
								args: {
									name: frm.doc.name,
									doctype: data.doctype,
								},
								callback: function (r) {
									frm.set_value("total_subscribers", r.message);
								},
							});
						},
						__("Import Subscribers"),
						__("Import")
					);
				},
				__("Action")
			);

			frm.add_custom_button(
				__("Add Subscribers"),
				function () {
					frappe.prompt(
						{
							fieldtype: "Text",
							label: __("Email Addresses"),
							fieldname: "email_list",
							reqd: 1,
						},
						function (data) {
							frappe.call({
								method: "frappe.email.doctype.email_group.email_group.add_subscribers",
								args: {
									name: frm.doc.name,
									email_list: data.email_list,
								},
								callback: function (r) {
									frm.set_value("total_subscribers", r.message);
								},
							});
						},
						__("Add Subscribers"),
						__("Add")
					);
				},
				__("Action")
			);

			frm.add_custom_button(
				__("New Newsletter"),
				function () {
					frappe.route_options = { email_group: frm.doc.name };
					frappe.new_doc("Newsletter");
				},
				__("Action")
			);
		}

		frm.trigger("preview_welcome_url");
	},
	welcome_url(frm) {
		frm.trigger("preview_welcome_url");
	},
	add_query_parameters: function (frm) {
		frm.trigger("preview_welcome_url");
	},
	preview_welcome_url: function (frm) {
		if (frm.doc.add_query_parameters && frm.doc.welcome_url) {
			frm.call("preview_welcome_url", { email: "mail@example.org" }).then((r) => {
				frm.set_df_property(
					"add_query_parameters",
					"description",
					`${__("Preview:")} ${r.message}`
				);
			});
		} else {
			frm.set_df_property("add_query_parameters", "description", "");
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
