# Master Control Plan: `User Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_standard` | Is Standard | Check | None |  |  |  | 0 | None |
| `section_break_2` | Document Types and Permissions | Section Break | None |  |  |  | None | None |
| `role` | Role | Link | Role |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `apply_user_permission_on` | Apply User Permission On | Link | DocType |  |  |  | None | Can only list down the document types which has been linked to the User document type. |
| `user_id_field` | User Id Field | Select | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `user_doctypes` | Document Types | Table | User Document Type |  |  |  | None | None |
| `custom_select_doctypes` | Custom Document Types (Select Permission) | Table | User Select Document Type |  |  |  | None | None |
| `select_doctypes` | Document Types (Select Permissions Only) | Table | User Select Document Type |  | ✅ | ✅ | None | None |
| `allowed_modules_section` | Allowed Modules | Section Break | None |  |  |  | None | None |
| `user_type_modules` | User Type Module | Table | User Type Module |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/user_type/user_type.js`
```javascript
// Copyright (c) 2021, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("User Type", {
	refresh: function (frm) {
		if (frm.is_new() && !frappe.boot.developer_mode) frm.set_value("is_standard", 1);

		frm.set_query("document_type", "user_doctypes", function () {
			return {
				filters: {
					istable: 0,
				},
			};
		});

		frm.set_query("document_type", "select_doctypes", function () {
			return {
				filters: {
					istable: 0,
				},
			};
		});

		frm.set_query("document_type", "custom_select_doctypes", function () {
			return {
				filters: {
					istable: 0,
				},
			};
		});

		frm.set_query("role", function () {
			return {
				filters: {
					is_custom: 1,
					disabled: 0,
					desk_access: 1,
				},
			};
		});

		frm.set_query("apply_user_permission_on", function () {
			return {
				query: "frappe.core.doctype.user_type.user_type.get_user_linked_doctypes",
			};
		});
	},

	onload: function (frm) {
		frm.trigger("get_user_id_fields");
	},

	apply_user_permission_on: function (frm) {
		frm.set_value("user_id_field", "");
		frm.trigger("get_user_id_fields");
	},

	get_user_id_fields: function (frm) {
		if (frm.doc.apply_user_permission_on) {
			frappe.call({
				method: "frappe.core.doctype.user_type.user_type.get_user_id",
				args: {
					parent: frm.doc.apply_user_permission_on,
				},
				callback: function (r) {
					set_field_options("user_id_field", [""].concat(r.message));
				},
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
