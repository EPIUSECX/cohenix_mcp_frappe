# Master Control Plan: `Module Def`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:module_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |
| `details_tab` | Details | Tab Break | None |  |  |  | None | None |
| `section_break_dnma` | None | Section Break | None |  |  |  | None | None |
| `module_name` | Module Name | Data | None | ✅ |  |  | None | None |
| `app_name` | App Name | Select | None | ✅ |  |  | None | None |
| `restrict_to_domain` | Restrict To Domain | Link | Domain |  |  |  | None | None |
| `package` | Package | Link | Package |  |  |  | None | None |
| `column_break_giia` | None | Column Break | None |  |  |  | None | None |
| `custom` | Custom | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/module_def/module_def.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Module Def", {
	refresh: function (frm) {
		frappe.xcall("frappe.core.doctype.module_def.module_def.get_installed_apps").then((r) => {
			frm.set_df_property("app_name", "options", JSON.parse(r));
			if (!frm.doc.app_name) {
				frm.set_value("app_name", "frappe");
			}
		});

		if (!frappe.boot.developer_mode) {
			frm.set_df_property("custom", "read_only", 1);
			if (frm.is_new()) {
				frm.set_value("custom", 1);
			}
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
