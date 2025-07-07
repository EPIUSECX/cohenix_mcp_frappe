# Master Control Plan: `Web Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `type` | Type | Select | Component
Section
Navbar
Footer |  |  |  | Section | None |
| `standard` | Standard | Check | None |  |  |  | 0 | None |
| `module` | Module | Link | Module Def |  |  |  | None | None |
| `template` | Template | Code | Jinja |  |  |  | None | None |
| `fields` | Fields | Table | Web Template Field |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_template/web_template.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Web Template", {
	refresh: function (frm) {
		if (!frappe.boot.developer_mode && frm.doc.standard) {
			frm.disable_form();
		}

		frm.toggle_display("standard", frappe.boot.developer_mode);
		// necessary to show template field again, after it was hidden when
		// unchecking 'standard'.
		frm.toggle_display("template", !frm.doc.standard);
	},
	standard: function (frm) {
		if (!frm.doc.standard && !frm.is_new()) {
			// If standard changes from true to false, hide template until
			// the next save. Changes will get overwritten from the backend
			// on save and should not be possible in the UI.
			frm.toggle_display("template", false);
			frm.dashboard.clear_headline();
			frm.dashboard.set_headline(__("Please save to edit the template."));
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
