# Master Control Plan: `Purchase Receipt Item`

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
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `product_bundle` | Product Bundle | Link | Product Bundle |  |  | ✅ | None | None |
| `supplier_part_no` | Supplier Part Number | Data | None |  | ✅ | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `section_break_4` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `brand` | Brand | Link | Brand |  | ✅ | ✅ | None | None |
| `image_column` | None | Column Break | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `received_and_accepted` | Received and Accepted | Section Break | None |  |  |  | None | None |
| `received_qty` | Received Quantity | Float | None | ✅ |  | ✅ | 0 | None |
| `qty` | Accepted Quantity | Float | None |  |  |  | None | None |
| `rejected_qty` | Rejected Quantity | Float | None |  |  |  | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None | ✅ |  |  | None | None |
| `retain_sample` | Retain Sample | Check | None |  |  | ✅ | 0 | None |
| `sample_quantity` | Sample Quantity | Int | None |  |  |  | None | None |
| `tracking_section` | Qty as Per Stock UOM | Section Break | None |  |  |  | None | None |
| `received_stock_qty` | Received Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `col_break_tracking_section` | None | Column Break | None |  |  |  | None | None |
| `stock_qty` | Accepted Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `returned_qty` | Returned Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `rate_and_amount` | Rate and Amount | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `discount_and_margin_section` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `column_break_37` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount on Price List Rate (%) | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  |  | None | None |
| `sec_break1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `apply_tds` | Apply TDS | Check | None |  | ✅ | ✅ | 1 | None |
| `section_break_29` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `sales_incoming_rate` | Sales Incoming Rate | Currency | Company:company:default_currency |  | ✅ |  | None | Valuation rate for the item as per Sales Invoice (Only for Internal Transfers) |
| `item_tax_amount` | Item Tax Amount Included in Value | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `rm_supp_cost` | Raw Materials Supplied Cost | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `landed_cost_voucher_amount` | Landed Cost Voucher Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `amount_difference_with_purchase_invoice` | Amount Difference with Purchase Invoice | Currency | None |  |  | ✅ | None | None |
| `billed_amt` | Billed Amt | Currency | currency |  |  | ✅ | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Accepted Warehouse | Link | Warehouse |  |  |  | None | None |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | None |
| `from_warehouse` | From Warehouse | Link | Warehouse |  | ✅ |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  |  | ✅ | None | None |
| `purchase_invoice` | Purchase Invoice | Link | Purchase Invoice |  |  | ✅ | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  |  | 0 | None |
| `return_qty_from_rejected_warehouse` | Return Qty from Rejected Warehouse | Check | None |  |  | ✅ | 0 | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  | ✅ | ✅ | 0 | None |
| `asset_location` | Asset Location | Link | Location |  |  |  | None | None |
| `asset_category` | Asset Category | Link | Asset Category |  |  | ✅ | None | None |
| `schedule_date` | Required By | Date | None |  |  | ✅ | None | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `material_request_item` | Material Request Item | Data | None |  | ✅ | ✅ | None | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  | ✅ | ✅ | None | None |
| `purchase_invoice_item` | Purchase Invoice Item | Data | None |  | ✅ | ✅ | None | None |
| `purchase_receipt_item` | Purchase Receipt Item | Data | None |  | ✅ | ✅ | None | None |
| `delivery_note_item` | Delivery Note Item | Data | None |  |  | ✅ | None | None |
| `putaway_rule` | Putaway Rule | Link | Putaway Rule |  |  | ✅ | None | None |
| `section_break_45` | Serial and Batch No | Section Break | None |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch No | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_break5` | None | Column Break | None |  |  |  | None | None |
| `add_serial_batch_for_rejected_qty` | Add Serial / Batch No (Rejected Qty) | Button | None |  |  |  | None | None |
| `rejected_serial_and_batch_bundle` | Rejected Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `section_break_3vxt` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `rejected_serial_no` | Rejected Serial No | Text | None |  |  |  | None | None |
| `column_break_tolu` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `subcontract_bom_section` | Subcontract BOM | Section Break | None |  |  |  | None | None |
| `include_exploded_items` | Include Exploded Items | Check | None |  |  | ✅ | 0 | None |
| `bom` | BOM | Link | BOM |  |  | ✅ | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  |  | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_41` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  |  | None | None |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | Tax detail table fetched from item master as a string and stored in this field.
Used for Taxes and Charges |
| `wip_composite_asset` | WIP Composite Asset | Link | Asset |  |  |  | None | None |
| `column_break_102` | None | Column Break | None |  |  |  | None | None |
| `provisional_expense_account` | Provisional Expense Account | Link | Account |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `section_break_80` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `sales_order_item` | Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `subcontracting_receipt_item` | Subcontracting Receipt Item | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 29
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
