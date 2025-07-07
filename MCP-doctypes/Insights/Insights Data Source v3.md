# Master Control Plan: `Insights Data Source v3`

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
| Insights Admin | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `status` | Status | Select | Inactive
Active |  |  |  | None | None |
| `database_type` | Database Type | Select | MariaDB
PostgreSQL
SQLite
DuckDB
BigQuery
Supabase |  |  |  | None | None |
| `host` | Host | Data | None |  |  |  | None | None |
| `port` | Port | Int | None |  |  |  | None | None |
| `use_ssl` | Use SSL | Check | None |  |  |  | 0 | None |
| `is_site_db` | Is Site Database | Check | None |  |  | ✅ | 0 | None |
| `is_frappe_db` | Is Frappe Database | Check | None |  |  | ✅ | 0 | None |
| `enable_stored_procedure_execution` | Enable Stored Procedure Execution | Check | None |  |  |  | 0 | None |
| `column_break_pfsa` | None | Column Break | None |  |  |  | None | None |
| `database_name` | Database Name | Data | None |  |  |  | None | None |
| `schema` | Schema | Data | None |  |  |  | None | None |
| `username` | Username | Data | None |  |  |  | None | None |
| `password` | Password | Password | None |  |  |  | None | None |
| `bigquery_project_id` | BigQuery Project ID | Data | None |  |  |  | None | None |
| `bigquery_dataset_id` | BigQuery Dataset ID | Data | None |  |  |  | None | None |
| `bigquery_service_account_key` | BigQuery Service Account Key (JSON) | JSON | None |  |  |  | None | None |
| `section_break_ajvs` | None | Section Break | None |  |  |  | None | None |
| `connection_string` | Connection String | Text | None |  |  |  | None | None |
| `supabase_project_url` | Supabase Project URL | Data | None |  |  |  | None | None |
| `supabase_api_key` | Supabase API Key (service_role) | Password | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source_v3/insights_data_source_v3.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Data Source v3", {
	refresh: function (frm) {},
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
