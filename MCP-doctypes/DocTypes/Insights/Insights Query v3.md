# Master Control Plan: `Insights Query v3`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Insights`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Insights User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights Admin | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  |  |  | None | None |
| `workbook` | Workbook | Link | Insights Workbook | ✅ |  |  | None | None |
| `column_break_gamr` | None | Column Break | None |  |  |  | None | None |
| `use_live_connection` | Use Live Connection | Check | None |  |  |  | 0 | None |
| `is_script_query` | Is Script Query | Check | None |  |  |  | 0 | None |
| `is_builder_query` | Is Builder Query | Check | None |  |  |  | 0 | None |
| `is_native_query` | Is Native Query | Check | None |  |  |  | 0 | None |
| `section_break_cuka` | None | Section Break | None |  |  |  | None | None |
| `operations` | Operations | JSON | None |  |  |  | None | None |
| `section_break_oujt` | None | Section Break | None |  |  |  | None | None |
| `linked_queries` | Linked Queries | JSON | None |  |  | ✅ | None | None |
| `old_name` | Old Name | Data | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_query_v3/insights_query_v3.js`
```javascript
// Copyright (c) 2025, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Insights Query v3", {
// 	refresh(frm) {

// 	},
// });

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
