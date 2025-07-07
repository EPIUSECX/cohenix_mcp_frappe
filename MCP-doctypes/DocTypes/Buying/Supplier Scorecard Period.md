# Master Control Plan: `Supplier Scorecard Period`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `naming_series` | Naming Series | Select | PU-SSP-.YYYY.- | ✅ |  |  | None | None |
| `total_score` | Period Score | Percent | None |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None | ✅ |  |  | None | None |
| `section_break_11` | Calculations | Section Break | None |  |  |  | None | None |
| `criteria` | Criteria | Table | Supplier Scorecard Scoring Criteria | ✅ |  |  | None | None |
| `variables` | Variables | Table | Supplier Scorecard Scoring Variable |  |  |  | None | None |
| `sec_ref` | Reference | Section Break | None |  |  |  | None | None |
| `scorecard` | Supplier Scorecard Setup | Link | Supplier Scorecard | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Supplier Scorecard Period |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier_scorecard_period/supplier_scorecard_period.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Supplier Scorecard Period", {
	onload: function (frm) {
		let criteria_grid = frm.get_field("criteria").grid;
		criteria_grid.toggle_enable("criteria_name", false);
		criteria_grid.toggle_enable("weight", false);
		criteria_grid.toggle_display("max_score", true);
		criteria_grid.toggle_display("formula", true);
		criteria_grid.toggle_display("score", true);
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
