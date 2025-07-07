# Master Control Plan: `Insights Query`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Insights`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `format:QRY-{####}`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `tab_break_1` | Query | Tab Break | None |  |  |  | None | None |
| `status` | Status | Select | Pending Execution
Execution Successful
Execution Failed |  | ✅ | ✅ | Pending Execution | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `is_native_query` | Is Native Query | Check | None |  |  |  | 0 | None |
| `is_assisted_query` | Is Assisted Query | Check | None |  |  |  | 0 | None |
| `is_saved_as_table` | Is Saved as Table | Check | None |  |  |  | 0 | None |
| `is_script_query` | Is Script Query | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `data_source` | Data Source | Link | Insights Data Source |  |  |  | None | None |
| `chart` | Chart | Link | Insights Chart |  |  |  | None | None |
| `is_stored` | Stored | Check | None |  |  |  | 0 | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `tables` | Tables | Table | Insights Query Table |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `columns` | Columns | Table | Insights Query Column |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `filters` | Filters | JSON | None |  |  |  | {
	"type": "LogicalExpression",
	"operator": "&&",
	"level": 1,
	"position": 1,
	"conditions": []
} | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `limit` | Limit | Int | None |  |  |  | 500 | None |
| `section_break_cnma` | None | Section Break | None |  |  |  | None | None |
| `json` | JSON | Code | JSON |  |  |  | {} | None |
| `sql` | SQL | Code | None |  |  | ✅ | None | None |
| `section_break_byvw` | None | Section Break | None |  |  |  | None | None |
| `script` | Script | Code | Python |  |  |  | None | None |
| `script_log` | Script Log | Text | None |  |  | ✅ | None | None |
| `section_break_qcue` | None | Section Break | None |  |  |  | None | None |
| `execution_time` | Execution Time (seconds) | Float | None |  |  | ✅ | None | None |
| `result_name` | Result | Data | None |  |  | ✅ | None | None |
| `results_row_count` | Result Row Count | Int | None |  |  | ✅ | None | None |
| `column_break_dluz` | None | Column Break | None |  |  |  | None | None |
| `last_execution` | Last Executed On | Datetime | None |  |  | ✅ | None | None |
| `transform_tab` | Transform | Tab Break | None |  |  |  | None | None |
| `section_break_18` | None | Section Break | None |  |  |  | None | None |
| `transforms` | Transforms | Table | Insights Query Transform |  |  |  | None | None |
| `variables` | Variables | Table | Insights Query Variable |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_query/insights_query.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Query", {
	refresh(frm) {
		if (frm.doc.status == "Pending Execution") {
			frm.add_custom_button(__("Run"), () => {
				frm.call({
					method: "run",
					doc: frm.doc,
					callback: (r) => {
						frm.reload_doc();
					},
				});
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
