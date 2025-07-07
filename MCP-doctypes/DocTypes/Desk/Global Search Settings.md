# Master Control Plan: `Global Search Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
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
| `allowed_in_global_search` | Search Priorities | Table | Global Search DocType |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/global_search_settings/global_search_settings.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Global Search Settings", {
	refresh: function (frm) {
		frappe.realtime.on("global_search_settings", (data) => {
			if (data.progress) {
				frm.dashboard.show_progress(
					"Setting up Global Search",
					(data.progress / data.total) * 100,
					data.msg
				);
				if (data.progress === data.total) {
					frm.dashboard.hide_progress("Setting up Global Search");
				}
			}
		});

		frm.add_custom_button(__("Reset"), function () {
			frappe.call({
				method: "frappe.desk.doctype.global_search_settings.global_search_settings.reset_global_search_settings_doctypes",
				callback: function () {
					frappe.show_alert({
						message: __("Global Search Document Types Reset."),
						indicator: "green",
					});
					frm.refresh();
				},
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
