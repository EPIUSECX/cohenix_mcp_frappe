# Master Control Plan: `Insights Alert`

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
| Insights User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `section_break_cmx9` | None | Section Break | None |  |  |  | None | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `channel` | Channel | Select | Email
Telegram |  |  |  | Email | None |
| `query` | Query | Link | Insights Query v3 | ✅ |  |  | None | None |
| `frequency` | Frequency | Select | Hourly
Daily
Weekly
Monthly
Cron |  |  |  | Hourly | None |
| `cron_format` | Cron Format | Data | None |  |  |  | None | None |
| `last_execution` | Last Execution | Datetime | None |  |  | ✅ | None | None |
| `next_execution` | Next Execution | Datetime | None |  |  |  | None | None |
| `column_break_ktop` | None | Column Break | None |  |  |  | None | None |
| `telegram_chat_id` | Telegram Chat ID | Data | None |  |  |  | None | None |
| `recipients` | Recipients | Small Text | None |  |  |  | None | None |
| `condition` | Condition | Code | None | ✅ |  |  | None | None |
| `custom_condition` | Custom Condition | Check | None |  |  |  | 0 | None |
| `section_break_ikjw` | None | Section Break | None |  |  |  | None | None |
| `message` | Message | Markdown Editor | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_alert/insights_alert.js`
```javascript
// Copyright (c) 2023, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Insights Alert", {
	refresh: function (frm) {
		frm.add_custom_button(__("Send Alert"), function () {
			frappe.dom.freeze(__("Sending Alert..."));
			frm.call("send_alert")
				.then(() => {
					frappe.dom.unfreeze();
					frappe.show_alert({
						message: __("Alert sent"),
						indicator: "green",
					});
				})
				.catch(() => {
					frappe.dom.unfreeze();
				});
		});
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
