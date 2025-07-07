# Master Control Plan: `User Permission`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `user` | User | Link | User | ✅ |  |  | None | None |
| `allow` | Allow | Link | DocType | ✅ |  |  | None | None |
| `for_value` | For Value | Dynamic Link | allow | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `is_default` | Is Default | Check | None |  |  |  | 0 | None |
| `advanced_control_section` | Advanced Control | Section Break | None |  |  |  | None | None |
| `apply_to_all_doctypes` | Apply To All Document Types | Check | None |  |  |  | 1 | None |
| `applicable_for` | Applicable For | Link | DocType |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `hide_descendants` | Hide Descendants | Check | None |  | ✅ |  | 0 | Hide descendant records of <b>For Value</b>. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user_permission/user_permission.js`
```javascript
// Copyright (c) 2017, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("User Permission", {
	setup: (frm) => {
		frm.set_query("allow", () => {
			return {
				filters: {
					issingle: 0,
					istable: 0,
				},
			};
		});

		frm.set_query("applicable_for", () => {
			return {
				query: "frappe.core.doctype.user_permission.user_permission.get_applicable_for_doctype_list",
				doctype: frm.doc.allow,
			};
		});
	},

	refresh: (frm) => {
		frm.add_custom_button(__("View Permitted Documents"), () =>
			frappe.set_route("query-report", "Permitted Documents For User", {
				user: frm.doc.user,
			})
		);
		frm.trigger("set_applicable_for_constraint");
		frm.trigger("toggle_hide_descendants");
	},

	allow: (frm) => {
		if (frm.doc.allow) {
			if (frm.doc.for_value) {
				frm.set_value("for_value", null);
			}
			frm.trigger("toggle_hide_descendants");
		}
	},

	apply_to_all_doctypes: (frm) => {
		frm.trigger("set_applicable_for_constraint");
	},

	set_applicable_for_constraint: (frm) => {
		frm.toggle_reqd("applicable_for", !frm.doc.apply_to_all_doctypes);

		if (frm.doc.apply_to_all_doctypes && frm.doc.applicable_for) {
			frm.set_value("applicable_for", null, null, true);
		}
	},

	toggle_hide_descendants: (frm) => {
		let show = frappe.boot.nested_set_doctypes.includes(frm.doc.allow);
		frm.toggle_display("hide_descendants", show);
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
