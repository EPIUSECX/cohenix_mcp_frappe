# Master Control Plan: `Recorder Query`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
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
| `index` | Index | Int | None |  |  |  | None | None |
| `query` | Query | Data | None |  |  |  | None | None |
| `duration` | Duration | Float | None |  |  |  | None | None |
| `column_break_qmju` | None | Column Break | None |  |  |  | None | None |
| `exact_copies` | Exact Copies | Int | None |  |  |  | None | None |
| `normalized_query` | Normalized Query | Data | None |  |  |  | None | None |
| `normalized_copies` | Normalized Copies | Int | None |  |  |  | None | None |
| `section_break_dygy` | None | Section Break | None |  |  |  | None | None |
| `stack_html` | Stack Trace | HTML | None |  |  |  | None | None |
| `stack` | None | Text | None |  | ✅ |  | None | None |
| `section_break_kvkb` | None | Section Break | None |  |  |  | None | None |
| `sql_explain_html` | SQL Explain | HTML | None |  |  |  | None | None |
| `explain_result` | None | Text | None |  | ✅ |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/recorder_query/recorder_query.js`
```javascript
// Copyright (c) 2023, Frappe Technologies and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Recorder Query", {
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
