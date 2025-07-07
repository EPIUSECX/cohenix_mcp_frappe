# Master Control Plan: `Insights Table Import`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Insights`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `table_label` | Table Label | Data | None | ✅ |  |  | None | None |
| `table_name` | Table Name | Data | None | ✅ |  |  | None | None |
| `if_exists` | Action if table exists | Select | Fail
Append
Overwrite |  |  |  | Fail | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `data_source` | Data Source | Link | Insights Data Source | ✅ |  |  | None | None |
| `source` | Source | Attach | None |  |  |  | None | None |
| `status` | Status | Select | Draft
Queued
Started
Partial Success
Success
Failed |  | ✅ | ✅ | Draft | None |
| `rows` | Rows | Int | None |  |  | ✅ | 0 | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `columns` | Columns | Table | Insights Table Column |  |  |  | None | None |
| `error` | Error | Text | None |  |  | ✅ | None | None |
| `amended_from` | Amended From | Link | Insights Table Import |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_table_import/insights_table_import.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Table Import", {
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
