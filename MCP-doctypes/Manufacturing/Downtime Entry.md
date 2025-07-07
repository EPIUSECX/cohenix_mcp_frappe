# Master Control Plan: `Downtime Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Naming Series | Select | DT- | ✅ |  |  | None | None |
| `workstation` | Workstation / Machine | Link | Workstation | ✅ |  |  | None | None |
| `operator` | Operator | Link | Employee | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `from_time` | From Time | Datetime | None | ✅ |  |  | None | None |
| `to_time` | To Time | Datetime | None | ✅ |  |  | None | None |
| `downtime` | Downtime | Float | None |  |  | ✅ | None | In Mins |
| `downtime_reason_section` | Downtime Reason | Section Break | None |  |  |  | None | None |
| `stop_reason` | Stop Reason | Select | 
Excessive machine set up time
Unplanned machine maintenance
On-machine press checks
Machine operator errors
Machine malfunction
Electricity down
Other | ✅ |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `remarks` | Remarks | Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/downtime_entry/downtime_entry.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Downtime Entry", {
	// refresh: function(frm) {
	// }
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Downtime Analysis` | Script Report | Manufacturing |



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
