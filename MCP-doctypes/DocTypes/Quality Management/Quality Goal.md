# Master Control Plan: `Quality Goal`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Quality Management`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:goal`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Desk User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `goal` | Goal | Data | None | ✅ |  |  | None | None |
| `frequency` | Monitoring Frequency | Select | None
Daily
Weekly
Monthly
Quarterly |  |  |  | None | None |
| `cb_00` | None | Column Break | None |  |  |  | None | None |
| `procedure` | Procedure | Link | Quality Procedure |  |  |  | None | None |
| `weekday` | Weekday | Select | Monday
Tuesday
Wednesday
Thursday
Friday
Saturday |  |  |  | None | None |
| `date` | Date | Select | 1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30 |  |  |  | None | None |
| `sb_01` | Objectives | Section Break | None |  |  |  | None | None |
| `objectives` | Objectives | Table | Quality Goal Objective |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/quality_management/doctype/quality_goal/quality_goal.js`
```javascript
// Copyright (c) 2018, Frappe and contributors
// For license information, please see license.txt

frappe.ui.form.on("Quality Goal", {
	// refresh: function(frm) {
	// }
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
