# Master Control Plan: `Supplier Scorecard`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:supplier`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `supplier_score` | Supplier Score | Data | None |  |  | ✅ | None | None |
| `indicator_color` | Indicator Color | Data | None |  | ✅ |  | None | None |
| `status` | Status | Data | None |  | ✅ |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `period` | Evaluation Period | Select | Per Week
Per Month
Per Year | ✅ |  |  | Per Month | None |
| `scoring_setup` | Scoring Setup | Section Break | None |  |  |  | None | None |
| `weighting_function` | Weighting Function | Small Text | None | ✅ |  |  | {total_score} * max( 0, min ( 1 , (12 - {period_number}) / 12) ) | Scorecard variables can be used, as well as:
{total_score} (the total score from that period),
{period_number} (the number of periods to present day)
 |
| `standings` | Scoring Standings | Table | Supplier Scorecard Scoring Standing | ✅ |  |  | None | None |
| `criteria_setup` | Criteria Setup | Section Break | None |  |  |  | None | None |
| `load_criteria` | Load All Criteria | Button | None |  |  |  | None | None |
| `criteria` | Scoring Criteria | Table | Supplier Scorecard Scoring Criteria | ✅ |  |  | None | None |
| `scorecard_actions` | Scorecard Actions | Section Break | None |  |  |  | None | None |
| `warn_rfqs` | Warn for new Request for Quotations | Check | None |  |  | ✅ | 0 | None |
| `warn_pos` | Warn for new Purchase Orders | Check | None |  |  | ✅ | 0 | None |
| `prevent_rfqs` | Prevent RFQs | Check | None |  |  | ✅ | 0 | None |
| `prevent_pos` | Prevent POs | Check | None |  |  | ✅ | 0 | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `notify_supplier` | Notify Supplier | Check | None |  | ✅ | ✅ | 0 | None |
| `notify_employee` | Notify Employee | Check | None |  | ✅ | ✅ | 0 | None |
| `employee` | Employee | Link | Employee |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 2

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier_scorecard/supplier_scorecard.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Supplier Scorecard", {
	setup: function (frm) {
		if (frm.doc.indicator_color !== "") {
			frm.set_indicator_formatter("status", function (doc) {
				return doc.indicator_color.toLowerCase();
			});
		}
	},
	onload: function (frm) {
		if (frm.doc.__unsaved == 1) {
			loadAllStandings(frm);
		}
	},
	load_criteria: function (frm) {
		frappe.call({
			method: "erpnext.buying.doctype.supplier_scorecard_criteria.supplier_scorecard_criteria.get_criteria_list",
			callback: function (r) {
				frm.set_value("criteria", []);
				for (var i = 0; i < r.message.length; i++) {
					var row = frm.add_child("criteria");
					row.criteria_name = r.message[i].name;
					frm.script_manager.trigger("criteria_name", row.doctype, row.name);
				}
				refresh_field("criteria");
			},
		});
	},
});

frappe.ui.form.on("Supplier Scorecard Scoring Standing", {
	standing_name: function (frm, cdt, cdn) {
		var d = frappe.get_doc(cdt, cdn);
		if (d.standing_name) {
			return frm.call({
				method: "erpnext.buying.doctype.supplier_scorecard_standing.supplier_scorecard_standing.get_scoring_standing",
				child: d,
				args: {
					standing_name: d.standing_name,
				},
			});
		}
	},
});

frappe.ui.form.on("Supplier Scorecard Scoring Criteria", {
	criteria_name: function (frm, cdt, cdn) {
		var d = frappe.get_doc(cdt, cdn);
		if (d.criteria_name) {
			return frm.call({
				method: "frappe.client.get",
				args: {
					fieldname: "weight",
					doctype: "Supplier Scorecard Criteria",
					filters: { name: d.criteria_name },
				},
				callback: function (r) {
					if (r.message) {
						d.weight = r.message.weight;
						frm.refresh_field("criteria", "weight");
					}
				},
			});
		}
	},
});

var loadAllStandings = function (frm) {
	frappe.call({
		method: "erpnext.buying.doctype.supplier_scorecard_standing.supplier_scorecard_standing.get_standings_list",
		callback: function (r) {
			for (var j = 0; j < frm.doc.standings.length; j++) {
				if (!Object.prototype.hasOwnProperty.call(frm.doc.standings[j], "standing_name")) {
					frm.get_field("standings").grid.grid_rows[j].remove();
				}
			}
			for (var i = 0; i < r.message.length; i++) {
				var new_row = frm.add_child("standings");
				new_row.standing_name = r.message[i].name;
				frm.script_manager.trigger("standing_name", new_row.doctype, new_row.name);
			}
			refresh_field("standings");
		},
	});
};

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
