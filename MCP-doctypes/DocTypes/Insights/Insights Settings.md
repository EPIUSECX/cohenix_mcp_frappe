# Master Control Plan: `Insights Settings`

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
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Insights Admin | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Insights User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `onboarding_section` | None | Section Break | None |  |  |  | None | None |
| `enable_permissions` | Enable Permissions | Check | None |  |  |  | 0 | None |
| `enable_data_store` | Enable Data Store | Check | None |  |  |  | 0 | None |
| `apply_user_permissions` | Apply User Permissions | Check | None |  |  |  | 0 | None |
| `allowed_origins` | Allowed Origins | Data | None |  |  |  | None | Comma seperated URLs to whitelist for embedding charts & dashboards |
| `max_records_to_sync` | Max Records To Sync | Int | None |  |  |  | None | None |
| `max_memory_usage` | Max Memory Usage | Int | None |  |  |  | None | None |
| `max_execution_time` | Max Execution Time (Seconds) | Int | None |  |  |  | None | None |
| `integrations_section` | Integrations | Section Break | None |  |  |  | None | None |
| `telegram_api_token` | Telegram API Token | Password | None |  |  |  | None | None |
| `query_section` | Query | Section Break | None |  |  |  | None | None |
| `fiscal_year_start` | Fiscal Year Start | Date | None |  |  |  | None | None |
| `week_starts_on` | Week Starts On | Select | Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday |  |  |  | Monday | None |
| `tab_break_tvwi` | Legacy | Tab Break | None |  |  |  | None | None |
| `setup_complete` | Setup Complete | Check | None |  |  |  | 0 | None |
| `onboarding_complete` | Onboarding Complete | Check | None |  |  |  | 0 | None |
| `allow_subquery` | Allow Subquery | Check | None |  |  |  | 0 | None |
| `auto_execute_query` | Auto Execute Query | Check | None |  |  |  | 0 | None |
| `query_result_expiry` | Cache Query Results For (Minutes) | Int | None |  |  |  | 10 | None |
| `query_result_limit` | Query Result Limit | Int | None |  |  |  | 1000 | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_settings/insights_settings.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on('Insights Settings', {
	// refresh: function(frm) {
	// }
})

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
