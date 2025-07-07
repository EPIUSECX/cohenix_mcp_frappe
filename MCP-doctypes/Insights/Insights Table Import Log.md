# Master Control Plan: `Insights Table Import Log`

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
| System Manager | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights Admin | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `status` | Status | Select | In Progress
Completed
Failed |  |  | ✅ | None | None |
| `data_source` | Data Source | Data | None | ✅ |  | ✅ | None | None |
| `table_name` | Table Name | Data | None | ✅ |  | ✅ | None | None |
| `parquet_file` | Parquet File | Text | None |  |  | ✅ | None | None |
| `started_at` | Started At | Datetime | None |  |  | ✅ | None | None |
| `ended_at` | Ended At | Datetime | None |  |  | ✅ | None | None |
| `time_taken` | Time Taken (Seconds) | Int | None |  |  | ✅ | None | None |
| `column_break_ydhp` | None | Column Break | None |  |  |  | None | None |
| `row_limit` | Row Limit | Int | None |  |  | ✅ | None | None |
| `memory_limit` | Memory Limit (MB) | Int | None |  |  | ✅ | None | None |
| `row_size` | Row Size (KB) | Float | None |  |  | ✅ | None | None |
| `batch_size` | Batch Size | Int | None |  |  | ✅ | None | None |
| `rows_imported` | Rows Imported | Int | None |  |  | ✅ | None | None |
| `section_break_vxpp` | None | Section Break | None |  |  |  | None | None |
| `query` | Query | Code | None | ✅ |  | ✅ | None | None |
| `output` | Output | Long Text | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_table_import_log/insights_table_import_log.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Table Import Log", {
	refresh(frm) {
		if (frm.doc.status == "In Progress") {
			frm.add_custom_button(__("Mark as Failed"), function () {
				frm.call("mark_as_failed").then(() => {
					frm.reload_doc();
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
