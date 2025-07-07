# Master Control Plan: `Role Replication`

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
| `existing_role` | Existing Role | Link | Role |  |  |  | None | None |
| `column_break_ydyj` | None | Column Break | None |  |  |  | None | None |
| `new_role` | New Role | Data | None |  |  |  | None | Input existing role name if you would like to extend it with access of another role. |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/role_replication/role_replication.js`
```javascript
// Copyright (c) 2024, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Role Replication", {
	refresh(frm) {
		frm.disable_save();
		frm.page.set_primary_action(__("Replicate"), ($btn) => {
			$btn.text(__("Replicating..."));
			frappe.run_serially([
				() => frappe.dom.freeze("Replicating..."),
				() => frm.call("replicate_role"),
				() => frappe.dom.unfreeze(),
				() => frappe.msgprint(__("Replication completed.")),
				() => $btn.text(__("Replicate")),
			]);
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
