# Master Control Plan: `Workspace Settings`

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
| Workspace Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `select_workspaces_section` | Select Workspaces | Section Break | None |  |  |  | None | None |
| `workspace_visibility_json` | Workspace Visibility | JSON | None | ✅ |  |  | None | None |
| `workspace_setup_completed` | Workspace Setup Completed | Check | None |  |  |  | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/workspace_settings/workspace_settings.js`
```javascript
// Copyright (c) 2024, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Workspace Settings", {
	setup(frm) {
		frm.hide_full_form_button = true;
		frm.docfields = [];
		frm.workspace_map = {};
		let workspace_visibilty = JSON.parse(frm.doc.workspace_visibility_json || "{}");

		// build fields from workspaces
		let cnt = 0,
			column_added = false;
		for (let page of frappe.boot.allowed_workspaces) {
			if (page.public) {
				frm.workspace_map[page.name] = page;
				cnt++;
				frm.docfields.push({
					fieldtype: "Check",
					fieldname: page.name,
					hidden: !frappe.boot.app_data_map[frappe.current_app].workspaces.includes(
						page.title
					),
					label: page.title + (page.parent_page ? ` (${page.parent_page})` : ""),
					initial_value: workspace_visibilty[page.name] !== 0, // not set is also visible
				});
			}
		}

		frappe.temp = frm;
	},
	validate(frm) {
		frm.doc.workspace_visibility_json = JSON.stringify(frm.dialog.get_values());
		frm.doc.workspace_setup_completed = 1;
	},
	after_save(frm) {
		// reload page to show latest sidebar
		frappe.app.sidebar.reload();
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
