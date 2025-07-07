# Master Control Plan: `Purchase Invoice Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
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
| `item_code` | Item | Link | Item |  |  |  | None | None |
| `product_bundle` | Product Bundle | Link | Product Bundle |  |  | ✅ | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `description_section` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `is_zero_rated` | Is Zero Rated | Check | None |  |  |  | None | None |
| `brand` | Brand | Link | Brand |  | ✅ |  | None | None |
| `col_break7` | None | Column Break | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `qty` | Accepted Qty | Float | None | ✅ |  |  | None | None |
| `rejected_qty` | Rejected Qty | Float | None |  |  |  | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  | ✅ | 1 | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `stock_qty` | Accepted Qty in Stock UOM | Float | None | ✅ |  | ✅ | None | None |
| `sec_break1` | None | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_26` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `column_break_30` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount on Price List Rate (%) | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `sec_break2` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `amount` | Amount | Currency | currency | ✅ |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `apply_tds` | Apply TDS | Check | None |  |  |  | 1 | None |
| `section_break_22` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `sales_incoming_rate` | Sales Incoming Rate | Currency | Company:company:default_currency |  | ✅ |  | None | Valuation rate for the item as per Sales Invoice (Only for Internal Transfers) |
| `item_tax_amount` | Item Tax Amount Included in Value | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `landed_cost_voucher_amount` | Landed Cost Voucher Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `rm_supp_cost` | Raw Materials Supplied Cost | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `warehouse_section` | Warehouse | Section Break | None |  |  |  | None | None |
| `warehouse` | Accepted Warehouse | Link | Warehouse |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch No | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_br_wh` | None | Column Break | None |  |  |  | None | None |
| `from_warehouse` | From Warehouse | Link | Warehouse |  | ✅ |  | None | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | None |
| `rejected_serial_and_batch_bundle` | Rejected Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `section_break_rqbe` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `rejected_serial_no` | Rejected Serial No | Text | None |  |  |  | None | None |
| `column_break_vbbb` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `accounting` | Accounting | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Head | Link | Account |  |  |  | None | None |
| `wip_composite_asset` | WIP Composite Asset | Link | Asset |  |  |  | None | None |
| `col_break5` | None | Column Break | None |  |  |  | None | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  | ✅ | ✅ | 0 | None |
| `asset_location` | Asset Location | Link | Location |  |  |  | None | None |
| `asset_category` | Asset Category | Link | Asset Category |  |  | ✅ | None | None |
| `deferred_expense_section` | Deferred Expense | Section Break | None |  |  |  | None | None |
| `deferred_expense_account` | Deferred Expense Account | Link | Account |  |  |  | None | None |
| `service_stop_date` | Service Stop Date | Date | None |  |  |  | None | None |
| `enable_deferred_expense` | Enable Deferred Expense | Check | None |  |  |  | 0 | None |
| `column_break_58` | None | Column Break | None |  |  |  | None | None |
| `service_start_date` | Service Start Date | Date | None |  |  |  | None | None |
| `service_end_date` | Service End Date | Date | None |  |  |  | None | None |
| `reference` | Reference | Section Break | None |  |  |  | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  |  | 0 | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | Tax detail table fetched from item master as a string and stored in this field.
Used for Taxes and Charges |
| `bom` | BOM | Link | BOM |  |  | ✅ | None | None |
| `include_exploded_items` | Include Exploded Items | Check | None |  |  | ✅ | 0 | None |
| `purchase_invoice_item` | Purchase Invoice Item | Data | None |  |  | ✅ | None | None |
| `col_break6` | None | Column Break | None |  |  |  | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  |  | ✅ | None | None |
| `po_detail` | Purchase Order Item | Data | None |  | ✅ | ✅ | None | None |
| `purchase_receipt` | Purchase Receipt | Link | Purchase Receipt |  |  | ✅ | None | None |
| `pr_detail` | Purchase Receipt Detail | Data | None |  | ✅ | ✅ | None | None |
| `sales_invoice_item` | Sales Invoice Item | Data | None |  |  | ✅ | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `material_request_item` | Material Request Item | Data | None |  | ✅ | ✅ | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  |  | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `section_break_82` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


### Custom Fields
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `is_zero_rated` | Is Zero Rated | Check | None |  |  |  | None | None |



### Links & Relationships
- **Link Fields:** 27
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
