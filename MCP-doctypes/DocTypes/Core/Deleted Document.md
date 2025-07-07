# Master Control Plan: `Deleted Document`

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
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `deleted_name` | Deleted Name | Data | None |  |  | ✅ | None | None |
| `deleted_doctype` | Deleted DocType | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `restored` | Restored | Check | None |  |  | ✅ | 0 | None |
| `new_name` | New Name | Read Only | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `data` | Data | Code | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/deleted_document/deleted_document.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Deleted Document", {
	refresh: function (frm) {
		if (frm.doc.restored) {
			frm.add_custom_button(__("Open"), function () {
				frappe.set_route("Form", frm.doc.deleted_doctype, frm.doc.new_name);
			});
		} else {
			frm.add_custom_button(__("Restore"), function () {
				frappe.call({
					method: "frappe.core.doctype.deleted_document.deleted_document.restore",
					args: { name: frm.doc.name },
					callback: function (r) {
						frm.reload_doc();
					},
				});
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
