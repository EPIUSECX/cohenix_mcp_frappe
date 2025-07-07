# Master Control Plan: `Success Action`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:ref_doctype`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `ref_doctype` | Reference Document Type | Link | DocType | ✅ |  |  | None | None |
| `first_success_message` | First Success Message | Data | None | ✅ |  |  | Congratulations on first creations | None |
| `message` | Message | Data | None | ✅ |  |  | Successfully created | None |
| `next_actions_html` | Next Actions HTML | HTML | None |  |  |  | None | None |
| `next_actions` | None | Data | None |  | ✅ |  | None | None |
| `action_timeout` | Action Timeout (Seconds) | Int | None |  |  |  | 7 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/success_action/success_action.js`
```javascript
// Copyright (c) 2018, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Success Action", {
	on_load: (frm) => {
		if (!frm.action_multicheck) {
			frm.trigger("set_next_action_multicheck");
		}
	},
	refresh: (frm) => {
		if (!frm.action_multicheck) {
			frm.trigger("set_next_action_multicheck");
		}
	},
	validate: (frm) => {
		const checked_actions = frm.action_multicheck.get_checked_options();
		if (checked_actions.length < 2) {
			frappe.msgprint(__("Select atleast 2 actions"));
		} else {
			return true;
		}
	},
	before_save: (frm) => {
		const checked_actions = frm.action_multicheck.get_checked_options();
		frm.doc.next_actions = checked_actions.join("\n");
	},
	after_save: (frm) => {
		frappe.boot.success_action.push(frm.doc);
		//TODO: update success action cache on record update and delete
	},
	set_next_action_multicheck: (frm) => {
		const next_actions_wrapper = frm.fields_dict.next_actions_html.$wrapper;
		const checked_actions = frm.doc.next_actions ? frm.doc.next_actions.split("\n") : [];
		const action_multicheck_options = get_default_next_actions().map((action) => {
			return {
				label: action.label,
				value: action.value,
				checked: checked_actions.length ? checked_actions.includes(action.value) : 1,
			};
		});
		frm.action_multicheck = frappe.ui.form.make_control({
			parent: next_actions_wrapper,
			df: {
				label: "Next Actions",
				fieldname: "next_actions_multicheck",
				fieldtype: "MultiCheck",
				options: action_multicheck_options,
				select_all: true,
			},
			render_input: true,
		});
	},
});

const get_default_next_actions = () => {
	return [
		{ label: __("New"), value: "new" },
		{ label: __("Print"), value: "print" },
		{ label: __("Email"), value: "email" },
		{ label: __("View All"), value: "list" },
	];
};

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
