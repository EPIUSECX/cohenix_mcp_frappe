# Master Control Plan: `Asset Maintenance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:asset_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Manufacturing User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `asset_name` | Asset Name | Link | Asset | ✅ |  |  | None | None |
| `asset_category` | Asset Category | Read Only | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item_code` | Item Code | Read Only | None |  |  |  | None | None |
| `item_name` | Item Name | Read Only | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `maintenance_team` | Maintenance Team | Link | Asset Maintenance Team | ✅ |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `maintenance_manager` | Maintenance Manager | Data | None |  | ✅ | ✅ | None | None |
| `maintenance_manager_name` | Maintenance Manager Name | Read Only | None |  |  |  | None | None |
| `section_break_8` | Tasks | Section Break | None |  |  |  | None | None |
| `asset_maintenance_tasks` | Maintenance Tasks | Table | Asset Maintenance Task | ✅ |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_maintenance/asset_maintenance.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Asset Maintenance", {
	setup: (frm) => {
		frm.set_query("asset_name", function () {
			return {
				filters: {
					company: frm.doc.company,
					docstatus: 1,
				},
			};
		});

		frm.set_query("assign_to", "asset_maintenance_tasks", function (doc) {
			return {
				query: "erpnext.assets.doctype.asset_maintenance.asset_maintenance.get_team_members",
				filters: {
					maintenance_team: doc.maintenance_team,
				},
			};
		});

		frm.set_indicator_formatter("maintenance_status", function (doc) {
			let indicator = "blue";
			if (doc.maintenance_status == "Overdue") {
				indicator = "orange";
			}
			if (doc.maintenance_status == "Cancelled") {
				indicator = "red";
			}
			return indicator;
		});
	},

	refresh: (frm) => {
		if (!frm.is_new()) {
			frm.trigger("make_dashboard");
		}
	},
	make_dashboard: (frm) => {
		if (!frm.is_new()) {
			frappe.call({
				method: "erpnext.assets.doctype.asset_maintenance.asset_maintenance.get_maintenance_log",
				args: { asset_name: frm.doc.asset_name },
				callback: (r) => {
					if (!r.message) {
						return;
					}
					const section = frm.dashboard.add_section("", __("Maintenance Log"));
					var rows = $("<div></div>").appendTo(section);
					// show
					(r.message || []).forEach(function (d) {
						$(`<div class='row' style='margin-bottom: 10px;'>
							<div class='col-sm-3 small'>
								<a onclick="frappe.set_route('List', 'Asset Maintenance Log',
									{'asset_name': '${d.asset_name}','maintenance_status': '${d.maintenance_status}' });">
									${__(d.maintenance_status)} <span class="badge">${d.count}</span>
								</a>
							</div>
						</div>`).appendTo(rows);
					});
					frm.dashboard.show();
				},
			});
		}
	},
});

frappe.ui.form.on("Asset Maintenance Task", {
	start_date: (frm, cdt, cdn) => {
		get_next_due_date(frm, cdt, cdn);
	},
	periodicity: (frm, cdt, cdn) => {
		get_next_due_date(frm, cdt, cdn);
	},
	last_completion_date: (frm, cdt, cdn) => {
		get_next_due_date(frm, cdt, cdn);
	},
	end_date: (frm, cdt, cdn) => {
		get_next_due_date(frm, cdt, cdn);
	},
});

var get_next_due_date = function (frm, cdt, cdn) {
	var d = locals[cdt][cdn];
	if (d.start_date && d.periodicity) {
		return frappe.call({
			method: "erpnext.assets.doctype.asset_maintenance.asset_maintenance.calculate_next_due_date",
			args: {
				start_date: d.start_date,
				periodicity: d.periodicity,
				end_date: d.end_date,
				last_completion_date: d.last_completion_date,
				next_due_date: d.next_due_date,
			},
			callback: function (r) {
				if (r.message) {
					frappe.model.set_value(cdt, cdn, "next_due_date", r.message);
				} else {
					frappe.model.set_value(cdt, cdn, "next_due_date", "");
				}
			},
		});
	}
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Asset Maintenance` | Report Builder | Assets |



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
