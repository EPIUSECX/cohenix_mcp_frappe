# Master Control Plan: `Module Onboarding`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Desk`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `subtitle` | Subtitle | Data | None | ✅ |  |  | None | None |
| `module` | Module | Link | Module Def | ✅ |  |  | None | None |
| `allow_roles` | Allow Roles | Table MultiSelect | Onboarding Permission | ✅ |  |  | None | System managers are allowed by default |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `success_message` | Success Message | Data | None | ✅ |  |  | None | None |
| `documentation_url` | Documentation URL | Data | None | ✅ |  |  | None | None |
| `is_complete` | Is Complete | Check | None |  |  | ✅ | 0 | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `steps` | Steps | Table | Onboarding Step Map | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/module_onboarding/module_onboarding.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Module Onboarding", {
	refresh: function (frm) {
		frappe.boot.developer_mode &&
			frm.set_intro(
				__(
					"Saving this will export this document as well as the steps linked here as json."
				),
				true
			);
		if (!frappe.boot.developer_mode) {
			frm.trigger("disable_form");
		}

		frm.add_custom_button(__("Reset"), () => {
			frm.call("reset_progress");
		});
	},

	disable_form: function (frm) {
		frm.set_read_only();
		frm.fields
			.filter((field) => field.has_input)
			.forEach((field) => {
				frm.set_df_property(field.df.fieldname, "read_only", "1");
			});
		frm.disable_save();
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
