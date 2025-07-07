# Master Control Plan: `Stock Reposting Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `scheduling_section` | Scheduling | Section Break | None |  |  |  | None | None |
| `limit_reposting_timeslot` | Limit timeslot for Stock Reposting | Check | None |  |  |  | 0 | None |
| `start_time` | Start Time | Time | None |  |  |  | None | None |
| `end_time` | End Time | Time | None |  |  |  | None | None |
| `limits_dont_apply_on` | Limits don't apply on | Select | 
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday |  |  |  | None | None |
| `item_based_reposting` | Use Item based reposting | Check | None |  |  |  | 1 | None |
| `do_reposting_for_each_stock_transaction` | Do reposting for each Stock Transaction | Check | None |  |  |  | 0 | None |
| `errors_notification_section` | Errors Notification | Section Break | None |  |  |  | None | None |
| `notify_reposting_error_to_role` | Notify Reposting Error to Role | Link | Role |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reposting_settings/stock_reposting_settings.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Stock Reposting Settings", {
	refresh: function (frm) {
		frm.trigger("convert_to_item_based_reposting");
	},

	convert_to_item_based_reposting: function (frm) {
		frm.add_custom_button(__("Convert to Item Based Reposting"), function () {
			frm.call({
				method: "convert_to_item_wh_reposting",
				frezz: true,
				doc: frm.doc,
				callback: function (r) {
					if (!r.exc) {
						frm.reload_doc();
					}
				},
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
