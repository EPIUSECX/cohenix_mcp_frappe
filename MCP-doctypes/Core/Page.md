# Master Control Plan: `Page`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:page_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `system_page` | System Page | Check | None |  |  |  | 0 | None |
| `page_html` | Page HTML | Section Break | None |  |  |  | None | None |
| `page_name` | Page Name | Data | None | ✅ |  |  | None | None |
| `title` | Title | Data | None |  |  |  | None | None |
| `icon` | icon | Data | None |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `module` | Module | Link | Module Def | ✅ |  |  | None | None |
| `restrict_to_domain` | Restrict To Domain | Link | Domain |  |  |  | None | None |
| `standard` | Standard | Select | Yes
No | ✅ |  |  | None | None |
| `section_break0` | None | Section Break | None |  |  |  | None | None |
| `roles` | Roles | Table | Has Role |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/page/page.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Page", {
	refresh: function (frm) {
		if (!frappe.boot.developer_mode && frappe.session.user != "Administrator") {
			// make the document read-only
			frm.set_read_only();
		}
		if (!frm.is_new() && !frm.doc.istable) {
			frm.add_custom_button(__("Go to {0} Page", [frm.doc.title || frm.doc.name]), () => {
				frappe.set_route(frm.doc.name);
			});
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
