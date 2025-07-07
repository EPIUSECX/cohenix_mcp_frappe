# Master Control Plan: `Manufacturing Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `bom_and_work_order_tab` | BOM and Production | Tab Break | None |  |  |  | None | None |
| `raw_materials_consumption_section` | Raw Materials Consumption | Section Break | None |  |  |  | None | None |
| `material_consumption` | Allow Continuous Material Consumption | Check | None |  |  |  | 0 | Allow material consumptions without immediately manufacturing finished goods against a Work Order |
| `get_rm_cost_from_consumption_entry` | Get Raw Materials Cost from Consumption Entry | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `backflush_raw_materials_based_on` | Backflush Raw Materials Based On | Select | BOM
Material Transferred for Manufacture |  |  |  | BOM | None |
| `validate_components_quantities_per_bom` | Validate Components and Quantities Per BOM | Check | None |  |  |  | 0 | None |
| `bom_section` | BOM | Section Break | None |  |  |  | None | None |
| `update_bom_costs_automatically` | Update BOM Cost Automatically | Check | None |  |  |  | 0 | Update BOM cost automatically via scheduler, based on the latest Valuation Rate/Price List Rate/Last Purchase Rate of raw materials |
| `column_break_lhyt` | None | Column Break | None |  |  |  | None | None |
| `section_break_6` | Default Warehouses for Production | Section Break | None |  |  |  | None | None |
| `default_wip_warehouse` | Default Work In Progress Warehouse | Link | Warehouse |  |  |  | None | None |
| `default_fg_warehouse` | Default Finished Goods Warehouse | Link | Warehouse |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `default_scrap_warehouse` | Default Scrap Warehouse | Link | Warehouse |  |  |  | None | None |
| `over_production_for_sales_and_work_order_section` | Overproduction for Sales and Work Order | Section Break | None |  |  |  | None | None |
| `overproduction_percentage_for_sales_order` | Overproduction Percentage For Sales Order | Percent | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `overproduction_percentage_for_work_order` | Overproduction Percentage For Work Order | Percent | None |  |  |  | None | None |
| `job_card_section` | Job Card and Capacity Planning | Tab Break | None |  |  |  | None | None |
| `add_corrective_operation_cost_in_finished_good_valuation` | Add Corrective Operation Cost in Finished Good Valuation | Check | None |  |  |  | 0 | None |
| `enforce_time_logs` | Enforce Time Logs | Check | None |  |  |  | 0 | Enabling this checkbox will force each Job Card Time Log to have From Time and To Time |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `job_card_excess_transfer` | Allow Excess Material Transfer | Check | None |  |  |  | 0 | Allow transferring raw materials even after the Required Quantity is fulfilled |
| `capacity_planning` | Capacity Planning | Section Break | None |  |  |  | None | None |
| `disable_capacity_planning` | Disable Capacity Planning | Check | None |  |  |  | 0 | None |
| `allow_overtime` | Allow Overtime | Check | None |  |  |  | 0 | Plan time logs outside Workstation working hours |
| `allow_production_on_holidays` | Allow Production on Holidays | Check | None |  |  |  | 0 | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `capacity_planning_for_days` | Capacity Planning For (Days) | Int | None |  |  |  | 30 | Plan operations X days in advance |
| `mins_between_operations` | Time Between Operations (Mins) | Int | None |  |  |  | None | Default: 10 mins |
| `other_settings_section` | Other Settings | Section Break | None |  |  |  | None | None |
| `set_op_cost_and_scrap_from_sub_assemblies` | Set Operating Cost / Scrap Items From Sub-assemblies | Check | None |  |  |  | 0 | To include sub-assembly costs and scrap items in Finished Goods on a work order without using a job card, when the 'Use Multi-Level BOM' option is enabled. |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `make_serial_no_batch_from_work_order` | Make Serial No / Batch from Work Order | Check | None |  |  |  | 0 | System will automatically create the serial numbers / batch for the Finished Good on submission of work order |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/manufacturing_settings/manufacturing_settings.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Manufacturing Settings", {});

frappe.tour["Manufacturing Settings"] = [
	{
		fieldname: "material_consumption",
		title: __("Allow Multiple Material Consumption"),
		description: __(
			"If ticked, multiple materials can be used for a single Work Order. This is useful if one or more time consuming products are being manufactured."
		),
	},
	{
		fieldname: "backflush_raw_materials_based_on",
		title: __("Backflush Raw Materials"),
		description: __(
			"The Stock Entry of type 'Manufacture' is known as backflush. Raw materials being consumed to manufacture finished goods is known as backflushing. <br><br> When creating Manufacture Entry, raw-material items are backflushed based on BOM of production item. If you want raw-material items to be backflushed based on Material Transfer entry made against that Work Order instead, then you can set it under this field."
		),
	},
	{
		fieldname: "default_wip_warehouse",
		title: __("Work In Progress Warehouse"),
		description: __(
			"This Warehouse will be auto-updated in the Work In Progress Warehouse field of Work Orders."
		),
	},
	{
		fieldname: "default_fg_warehouse",
		title: __("Finished Goods Warehouse"),
		description: __("This Warehouse will be auto-updated in the Target Warehouse field of Work Order."),
	},
	{
		fieldname: "update_bom_costs_automatically",
		title: __("Update BOM Cost Automatically"),
		description: __(
			"If ticked, the BOM cost will be automatically updated based on Valuation Rate / Price List Rate / last purchase rate of raw materials."
		),
	},
];

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
