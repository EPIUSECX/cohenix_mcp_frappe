# Master Control Plan: `Delivery Note Item`

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
| `barcode` | Barcode | Data | None |  |  |  | None | None |
| `has_item_scanned` | Has Item Scanned | Check | None |  |  | ✅ | 0 | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `customer_item_code` | Customer's Item Code | Data | None |  | ✅ | ✅ | None | None |
| `section_break_6` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `brand` | Brand Name | Link | Brand |  | ✅ | ✅ | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ | ✅ | None | None |
| `image_section` | Image | Section Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  | ✅ | None | None |
| `stock_qty_sec_break` | None | Section Break | None |  |  |  | None | None |
| `stock_qty` | Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `stock_qty_col_break` | None | Column Break | None |  |  |  | None | None |
| `returned_qty` | Returned Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `section_break_17` | None | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  | ✅ | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `discount_and_margin` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount (%) on Price List Rate with Margin | Float | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `grant_commission` | Grant Commission | Check | None |  |  | ✅ | 0 | None |
| `section_break_25` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `billed_amt` | Billed Amt | Currency | currency |  |  | ✅ | None | None |
| `incoming_rate` | Incoming Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  |  | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  |  | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `target_warehouse` | Target Warehouse | Link | Warehouse |  | ✅ |  | None | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  |  | 0 | None |
| `against_sales_order` | Against Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `so_detail` | Against Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `against_sales_invoice` | Against Sales Invoice | Link | Sales Invoice |  |  | ✅ | None | None |
| `si_detail` | Against Sales Invoice Item | Data | None |  | ✅ | ✅ | None | None |
| `dn_detail` | Against Delivery Note Item | Data | None |  | ✅ | ✅ | None | None |
| `against_pick_list` | Against Pick List | Link | Pick List |  |  | ✅ | None | None |
| `pick_list_item` | Pick List Item | Data | None |  | ✅ | ✅ | None | None |
| `section_break_40` | Serial and Batch No | Section Break | None |  |  |  | None | None |
| `pick_serial_and_batch` | Pick Serial / Batch No | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `column_break_eaoe` | None | Column Break | None |  |  |  | None | None |
| `section_break_qyjv` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `column_break_rxvc` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `available_qty_section` | Available Qty | Section Break | None |  |  |  | None | None |
| `actual_qty` | Qty (Warehouse) | Float | None |  |  | ✅ | None | None |
| `actual_batch_qty` | Available Batch Qty at From Warehouse | Float | None |  |  | ✅ | None | None |
| `column_break_atna` | None | Column Break | None |  |  |  | None | None |
| `company_total_stock` | Qty (Company) | Float | None |  |  | ✅ | None | None |
| `section_break_kejd` | None | Section Break | None |  |  |  | None | None |
| `installed_qty` | Installed Qty | Float | None |  |  | ✅ | None | None |
| `packed_qty` | Packed Qty | Float | None |  |  | ✅ | 0 | None |
| `column_break_fguf` | None | Column Break | None |  |  |  | None | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `column_break_71` | None | Column Break | None |  |  |  | None | None |
| `item_tax_rate` | Item Tax Rate | Small Text | None |  | ✅ | ✅ | None | None |
| `internal_transfer_section` | Internal Transfer | Section Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  |  | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  |  | ✅ | None | None |
| `column_break_82` | None | Column Break | None |  |  |  | None | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  |  | ✅ | None | None |
| `material_request_item` | Material Request Item | Data | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `section_break_72` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 20
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
