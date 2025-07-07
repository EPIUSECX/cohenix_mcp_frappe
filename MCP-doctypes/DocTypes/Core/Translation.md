# Master Control Plan: `Translation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `contributed` | Contributed | Check | None |  | ✅ | ✅ | 0 | None |
| `language` | Language | Link | Language | ✅ |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `source_text` | Source Text | Code | None | ✅ |  |  | None | If your data is in HTML, please copy paste the exact HTML code with the tags. |
| `context` | Context | Data | None |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `translated_text` | Translated Text | Code | None | ✅ |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `contribution_status` | Contribution Status | Select | 
Pending
Verified
Rejected |  |  | ✅ | None | None |
| `contribution_docname` | Contribution Document Name | Data | None |  | ✅ | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/translation/translation.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Translation", {
	refresh: function () {
		//
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
