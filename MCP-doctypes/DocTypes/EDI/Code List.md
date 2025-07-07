# Master Control Plan: `Code List`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `EDI`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  |  |  | None | None |
| `canonical_uri` | Canonical URI | Data | None |  |  |  | None | None |
| `url` | URL | Data | URL |  |  |  | None | None |
| `default_common_code` | Default Common Code | Link | Common Code |  |  |  | None | This value shall be used when no matching Common Code for a record is found. |
| `column_break_nkls` | None | Column Break | None |  |  |  | None | None |
| `version` | Version | Data | None |  |  |  | None | None |
| `publisher` | Publisher | Data | None |  |  |  | None | None |
| `publisher_id` | Publisher ID | Data | None |  |  |  | None | None |
| `section_break_npxp` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/edi/doctype/code_list/code_list.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Code List", {
	refresh: (frm) => {
		if (!frm.doc.__islocal) {
			frm.add_custom_button(__("Import Genericode File"), function () {
				erpnext.edi.import_genericode(frm);
			});
		}
	},
	setup: (frm) => {
		frm.savetrash = () => {
			frm.validate_form_action("Delete");
			frappe.confirm(
				__(
					"Are you sure you want to delete {0}?<p>This action will also delete all associated Common Code documents.</p>",
					[frm.docname.bold()]
				),
				function () {
					return frappe.call({
						method: "frappe.client.delete",
						args: {
							doctype: frm.doctype,
							name: frm.docname,
						},
						freeze: true,
						freeze_message: __("Deleting {0} and all associated Common Code documents...", [
							frm.docname,
						]),
						callback: function (r) {
							if (!r.exc) {
								frappe.utils.play_sound("delete");
								frappe.model.clear_doc(frm.doctype, frm.docname);
								window.history.back();
							}
						},
					});
				}
			);
		};

		frm.set_query("default_common_code", function (doc) {
			return {
				filters: {
					code_list: doc.name,
				},
			};
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
