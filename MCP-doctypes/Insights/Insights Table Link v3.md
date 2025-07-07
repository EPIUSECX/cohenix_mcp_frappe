# Master Control Plan: `Insights Table Link v3`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Insights`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `autoincrement`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Insights Admin | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `data_source` | Data Source | Link | Insights Data Source v3 | ✅ |  |  | None | None |
| `left_table` | Left Table | Data | None | ✅ |  |  | None | None |
| `right_table` | Right Table | Data | None | ✅ |  |  | None | None |
| `column_break_nqax` | None | Column Break | None |  |  |  | None | None |
| `left_column` | Left Column | Data | None | ✅ |  |  | None | None |
| `right_column` | Right Column | Data | None | ✅ |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_table_link_v3/insights_table_link_v3.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Insights Table Link v3", {
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
