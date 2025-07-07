# Master Control Plan: `Property Setter`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Custom`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Property Setter overrides a standard DocType or Field property

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_system_generated` | Is System Generated | Check | None |  |  | ✅ | 0 | None |
| `help` | Help | HTML | <div class="alert">Please don't update it as it can mess up your form. Use the Customize Form View and Custom Fields to set properties!</div> |  |  |  | None | None |
| `sb0` | None | Section Break | None |  |  |  | None | None |
| `doctype_or_field` | Applied On | Select | 
DocField
DocType
DocType Link
DocType Action
DocType State | ✅ |  |  | None | None |
| `doc_type` | DocType | Link | DocType | ✅ |  |  | None | None |
| `field_name` | Field Name | Data | None |  |  |  | None | ID (name) of the entity whose property is to be set |
| `row_name` | Row Name | Data | None |  |  |  | None | For DocType Link / DocType Action |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `module` | Module (for export) | Link | Module Def |  |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `property` | Property | Data | None | ✅ |  |  | None | None |
| `property_type` | Property Type | Data | None |  |  |  | None | None |
| `value` | Set Value | Small Text | None |  |  |  | None | New value to be set |
| `default_value` | Default Value | Data | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/property_setter/property_setter.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// MIT License. See license.txt

frappe.ui.form.on("Property Setter", {
	validate: function (frm) {
		if (frm.doc.property_type == "Check" && !["0", "1"].includes(frm.doc.value)) {
			frappe.throw(__("Value for a check field can be either 0 or 1"));
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Audit System Hooks` | Script Report | Custom |



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
