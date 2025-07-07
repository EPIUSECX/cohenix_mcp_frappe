# Master Control Plan: `Insights Data Source`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Insights`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:title`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `status` | Status | Select | Inactive
Active |  | ✅ | ✅ | None | None |
| `database_type` | Database Type | Select | MariaDB
PostgreSQL
SQLite |  |  |  | MariaDB | None |
| `is_site_db` | Site Database | Check | None |  |  | ✅ | 0 | None |
| `host` | Host | Data | None |  |  |  | None | None |
| `port` | Port | Data | None |  |  |  | None | None |
| `use_ssl` | Use SSL | Check | None |  |  |  | 0 | None |
| `allow_imports` | Allow Table Import | Check | None |  |  |  | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `database_name` | Database Name | Data | None |  |  |  | None | None |
| `username` | Username | Data | None |  |  |  | None | None |
| `password` | Password | Password | None |  |  |  | None | None |
| `section_break_j5ez` | None | Section Break | None |  |  |  | None | None |
| `connection_string` | Connection String | Small Text | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source/insights_data_source.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Data Source", {
	refresh: function (frm) {
		if (frm.name == "Query Store") {
			frm.set_read_only();
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
