# Master Control Plan: `Web Template Field`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Website`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `label` | Label | Data | None | ✅ |  |  | None | None |
| `fieldname` | Fieldname | Data | None |  |  |  | None | None |
| `fieldtype` | Fieldtype | Select | Attach Image
Check
Data
Int
Link
Select
Small Text
Text
Markdown Editor
Section Break
Column Break
Table Break | ✅ |  |  | Data | None |
| `reqd` | Mandatory | Check | None |  |  |  | 0 | None |
| `options` | Options | Small Text | None |  |  |  | None | None |
| `default` | Default | Small Text | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/web_template_field/web_template_field.js`
```javascript
// Copyright (c) 2020, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Web Template Field", {
	// refresh: function(frm) {
	// }
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
