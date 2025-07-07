# Master Control Plan: `Bin`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item | ✅ |  | ✅ | None | None |
| `column_break_yreo` | None | Column Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  | ✅ | None | None |
| `section_break_stag` | None | Section Break | None |  |  |  | None | None |
| `actual_qty` | Actual Qty | Float | None |  |  | ✅ | 0.00 | None |
| `planned_qty` | Planned Qty | Float | None |  |  | ✅ | None | None |
| `indented_qty` | Requested Qty | Float | None |  |  | ✅ | 0.00 | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | 0.00 | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `column_break_xn5j` | None | Column Break | None |  |  |  | None | None |
| `reserved_qty` | Reserved Qty | Float | None |  |  | ✅ | 0.00 | None |
| `reserved_qty_for_production` | Reserved Qty for Production | Float | None |  |  | ✅ | None | None |
| `reserved_qty_for_sub_contract` | Reserved Qty for Subcontract | Float | None |  |  | ✅ | None | None |
| `reserved_qty_for_production_plan` | Reserved Qty for Production Plan | Float | None |  |  | ✅ | None | None |
| `reserved_stock` | Reserved Stock | Float | None |  |  | ✅ | 0 | None |
| `section_break_pmrs` | None | Section Break | None |  |  |  | None | None |
| `stock_uom` | UOM | Link | UOM |  |  | ✅ | None | None |
| `column_break_0slj` | None | Column Break | None |  |  |  | None | None |
| `valuation_rate` | Valuation Rate | Float | None |  |  | ✅ | None | None |
| `stock_value` | Stock Value | Float | None |  |  | ✅ | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/bin/bin.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Bin", {
	refresh(frm) {
		frm.trigger("recalculate_bin_quantity");
	},

	recalculate_bin_quantity(frm) {
		frm.add_custom_button(__("Recalculate Bin Qty"), () => {
			frappe.call({
				method: "recalculate_qty",
				freeze: true,
				doc: frm.doc,
				callback: function (r) {
					frappe.show_alert(__("Bin Qty Recalculated"), 2);
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
| Name | Type | Module |
|---|---|---|
| `Item Balance (Simple)` | Query Report | Stock |
| `Item Shortage Report` | Script Report | Stock |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Stock Value` | Total Stock Value | Sum | Stock |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
