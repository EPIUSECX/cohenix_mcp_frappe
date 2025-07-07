# Master Control Plan: `Material Request Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `schedule_date` | Required By | Date | None | ✅ |  |  | None | None |
| `section_break_4` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  | ✅ | None | None |
| `image` | Image | Attach Image | None |  |  | ✅ | None | None |
| `quantity_and_warehouse` | Quantity and Warehouse | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `from_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `warehouse` | Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  |  | None | None |
| `stock_qty` | Stock Qty | Float | None |  |  | ✅ | None | None |
| `qty_info_sec_break` | None | Section Break | None |  |  |  | None | None |
| `min_order_qty` | Min Order Qty | Float | None |  |  | ✅ | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `qty_info_col_break` | None | Column Break | None |  |  |  | None | None |
| `actual_qty` | Actual Qty | Float | None |  |  | ✅ | None | None |
| `ordered_qty` | Completed Qty | Float | None |  |  | ✅ | None | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `rate_and_amount_section_break` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  | ✅ | ✅ | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `column_break_glru` | None | Column Break | None |  |  |  | None | None |
| `wip_composite_asset` | WIP Composite Asset | Link | Asset |  |  |  | None | None |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  | ✅ | None | None |
| `col_break_mfg` | None | Column Break | None |  |  |  | None | None |
| `bom_no` | BOM No | Link | BOM |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `more_info` | More Information | Section Break | None |  |  |  | None | None |
| `lead_time_date` | Lead Time Date | Date | None |  |  | ✅ | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `sales_order_item` | Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `production_plan` | Production Plan | Link | Production Plan |  |  | ✅ | None | None |
| `material_request_plan_item` | Material Request Plan Item | Data | None |  |  | ✅ | None | None |
| `job_card_item` | Job Card Item | Data | None |  | ✅ |  | None | None |
| `section_break_46` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 15
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)




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
