# Master Control Plan: `Material Request Plan Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `from_warehouse` | From Warehouse | Link | Warehouse |  |  |  | None | None |
| `warehouse` | For Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `material_request_type` | Type | Select | 
Purchase
Material Transfer
Material Issue
Manufacture
Subcontracting
Customer Provided |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  | ✅ | None | None |
| `section_break_azee` | None | Section Break | None |  |  |  | None | None |
| `required_bom_qty` | Reqd Qty (BOM) | Float | None |  |  | ✅ | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `column_break_wack` | None | Column Break | None |  |  |  | None | None |
| `quantity` | Required Qty | Float | None | ✅ |  |  | None | None |
| `stock_reserved_qty` | Stock Reserved Qty | Float | None |  |  | ✅ | None | None |
| `item_details` | Item Description | Section Break | None |  |  |  | None | None |
| `schedule_date` | Required By | Date | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `min_order_qty` | Minimum Order Quantity | Float | None |  |  | ✅ | None | None |
| `section_break_8` | Reference | Section Break | None |  |  |  | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `bin_qty_section` | BIN Qty | Section Break | None |  |  |  | None | None |
| `actual_qty` | Qty In Stock | Float | None |  |  | ✅ | 0 | None |
| `requested_qty` | Requested Qty | Float | None |  |  | ✅ | 0 | None |
| `reserved_qty_for_production` | Reserved Qty for Production | Float | None |  |  | ✅ | None | None |
| `column_break_yhelv` | None | Column Break | None |  |  |  | None | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | None | None |
| `safety_stock` | Safety Stock | Float | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/material_request_plan_item/material_request_plan_item.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Material Request Plan Item", {
	refresh: function () {},
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
