# Master Control Plan: `Document Naming Rule`

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
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `priority` | Priority | Int | None |  |  |  | None | Rules with higher priority number will be applied first. |
| `section_break_3` | Rule Conditions | Section Break | None |  |  |  | None | None |
| `conditions` | Conditions | Table | Document Naming Rule Condition |  |  |  | None | None |
| `naming_section` | Naming | Section Break | None |  |  |  | None | None |
| `prefix` | Prefix | Data | None | ✅ |  |  | None | None |
| `counter` | Counter | Int | None |  |  |  | 0 | Warning: Updating counter may lead to document name conflicts if not done properly |
| `column_break_xfqa` | None | Column Break | None |  |  |  | None | None |
| `prefix_digits` | Digits | Int | None | ✅ |  |  | 5 | Example: 00001 |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/document_naming_rule/document_naming_rule.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Document Naming Rule", {
	refresh: function (frm) {
		frm.trigger("document_type");
		frm.last_counter_value = frm.doc.counter;
		frm.skip_before_save = false;
	},
	before_save: function (frm) {
		if (frm.is_new() || frm.skip_before_save || frm.last_counter_value === frm.doc.counter)
			return;

		frappe.validated = false;
		frappe.warn(
			__("Are you sure?"),
			__("Updating counter may lead to document name conflicts if not done properly"),
			() => {
				frm.skip_before_save = true;
				frm.save();
			},
			__("Proceed"),
			false
		);
	},
	document_type: (frm) => {
		// update the select field options with fieldnames
		if (frm.doc.document_type) {
			frappe.model.with_doctype(frm.doc.document_type, () => {
				let fieldnames = frappe
					.get_meta(frm.doc.document_type)
					.fields.filter((d) => {
						return frappe.model.no_value_type.indexOf(d.fieldtype) === -1;
					})
					.map((d) => {
						return { label: `${d.label} (${d.fieldname})`, value: d.fieldname };
					});
				frm.fields_dict.conditions.grid.update_docfield_property(
					"field",
					"options",
					fieldnames
				);
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
