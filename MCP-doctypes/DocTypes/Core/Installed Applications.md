# Master Control Plan: `Installed Applications`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `installed_applications` | Installed Applications | Table | Installed Application |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/installed_applications/installed_applications.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Installed Applications", {
	refresh: function (frm) {
		frm.add_custom_button(__("Update Hooks Resolution Order"), () => {
			frm.trigger("show_update_order_dialog");
		});
	},

	show_update_order_dialog() {
		const dialog = new frappe.ui.Dialog({
			title: __("Update Hooks Resolution Order"),
			fields: [
				{
					fieldname: "apps",
					fieldtype: "Table",
					label: __("Installed Apps"),
					cannot_add_rows: true,
					cannot_delete_rows: true,
					in_place_edit: true,
					data: [],
					fields: [
						{
							fieldtype: "Data",
							fieldname: "app_name",
							label: __("App Name"),
							in_list_view: 1,
							read_only: 1,
						},
					],
				},
			],
			primary_action: function () {
				const new_order = this.get_values()["apps"].map((row) => row.app_name);
				frappe.call({
					method: "frappe.core.doctype.installed_applications.installed_applications.update_installed_apps_order",
					freeze: true,
					args: {
						new_order: new_order,
					},
				});
				this.hide();
			},
			primary_action_label: __("Update Order"),
		});

		frappe
			.xcall(
				"frappe.core.doctype.installed_applications.installed_applications.get_installed_app_order"
			)
			.then((data) => {
				data.forEach((app) => {
					dialog.fields_dict.apps.df.data.push({
						app_name: app,
					});
				});

				dialog.fields_dict.apps.grid.refresh();
				// hack: change checkboxes to drag handles.
				let grid = $(dialog.fields_dict.apps.grid.parent);
				grid.find(".grid-row-check:first").remove() &&
					grid.find(".grid-row-check").replaceWith(frappe.utils.icon("menu"));
				dialog.show();
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
