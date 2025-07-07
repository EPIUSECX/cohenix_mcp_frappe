# Master Control Plan: `Portal Settings`

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
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `default_role` | Default Role at Time of Signup | Link | Role |  |  |  | None | None |
| `default_portal_home` | Default Portal Home | Data | None |  |  |  | None | Example: "/desk" |
| `standard_menu_items` | Standard Sidebar Menu | Section Break | None |  |  |  | None | None |
| `hide_standard_menu` | Hide Standard Menu | Check | None |  |  |  | 0 | None |
| `menu` | Portal Menu | Table | Portal Menu Item |  |  |  | None | None |
| `custom_sidebar_menu` | Custom Sidebar Menu | Section Break | None |  |  |  | None | None |
| `custom_menu` | Custom Menu Items | Table | Portal Menu Item |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/portal_settings/portal_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Portal Settings", {
	setup: function (frm) {
		frm.fields_dict["default_role"].get_query = function (doc) {
			return {
				filters: {
					desk_access: 0,
					disabled: 0,
				},
			};
		};
	},
	onload: function (frm) {
		frm.get_field("menu").grid.only_sortable();
	},
	refresh: function (frm) {
		frm.add_custom_button(__("Reset"), function () {
			frappe.confirm(__("Restore to default settings?"), function () {
				frm.call("reset");
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
