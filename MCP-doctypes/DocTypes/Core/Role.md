# Master Control Plan: `Role`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:role_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `role_name` | Role Name | Data | None | ✅ |  |  | None | None |
| `home_page` | Home Page | Data | None |  |  |  | None | Route: Example "/app" |
| `restrict_to_domain` | Restrict To Domain | Link | Domain |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | If disabled, this role will be removed from all users. |
| `is_custom` | Is Custom | Check | None |  |  |  | 0 | None |
| `desk_access` | Desk Access | Check | None |  |  |  | 1 | None |
| `two_factor_auth` | Two Factor Authentication | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/role/role.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See LICENSE

frappe.ui.form.on("Role", {
	refresh: function (frm) {
		if (frm.doc.name === "All") {
			frm.dashboard.add_comment(
				__("Role 'All' will be given to all system + website users."),
				"yellow"
			);
		} else if (frm.doc.name === "Desk User") {
			frm.dashboard.add_comment(
				__("Role 'Desk User' will be given to all system users."),
				"yellow"
			);
		}

		frm.set_df_property("is_custom", "read_only", frappe.session.user !== "Administrator");

		frm.add_custom_button("Role Permissions Manager", function () {
			frappe.route_options = { role: frm.doc.name };
			frappe.set_route("permission-manager");
		});
		frm.add_custom_button("Show Users", function () {
			frappe.route_options = { role: frm.doc.name };
			frappe.set_route("List", "User", "Report");
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
