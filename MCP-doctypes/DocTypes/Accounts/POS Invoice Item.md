# Master Control Plan: `POS Invoice Item`

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
| `barcode` | Barcode | Data | None |  |  |  | None | None |
| `has_item_scanned` | Has Item Scanned | Check | None |  |  | ✅ | 0 | None |
| `item_code` | Item | Link | Item |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `customer_item_code` | Customer's Item Code | Data | None |  | ✅ | ✅ | None | None |
| `description_section` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None | ✅ |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ | ✅ | None | None |
| `brand` | Brand Name | Data | None |  | ✅ |  | None | None |
| `image_section` | Image | Section Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | None | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  |  | None | None |
| `stock_qty` | Qty as per Stock UOM | Float | None |  |  | ✅ | None | None |
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
| `discount_percentage` | Discount (%) on Price List Rate with Margin | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `amount` | Amount | Currency | currency | ✅ |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `grant_commission` | Grant Commission | Check | None |  |  | ✅ | 0 | None |
| `section_break_21` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `drop_ship` | Drop Ship | Section Break | None |  |  |  | None | None |
| `delivered_by_supplier` | Delivered By Supplier | Check | None |  |  | ✅ | 0 | None |
| `accounting` | Accounting Details | Section Break | None |  |  |  | None | None |
| `income_account` | Income Account | Link | Account | ✅ |  |  | None | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  | ✅ | ✅ | 0 | None |
| `asset` | Asset | Link | Asset |  |  |  | None | None |
| `finance_book` | Finance Book | Link | Finance Book |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `deferred_revenue` | Deferred Revenue | Section Break | None |  |  |  | None | None |
| `deferred_revenue_account` | Deferred Revenue Account | Link | Account |  |  |  | None | None |
| `service_stop_date` | Service Stop Date | Date | None |  |  |  | None | None |
| `enable_deferred_revenue` | Enable Deferred Revenue | Check | None |  |  |  | 0 | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `service_start_date` | Service Start Date | Date | None |  |  |  | None | None |
| `service_end_date` | Service End Date | Date | None |  |  |  | None | None |
| `section_break_18` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  | ✅ | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  | ✅ | None | None |
| `warehouse_and_reference` | Stock Details | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `target_warehouse` | Customer Warehouse (Optional) | Link | Warehouse |  | ✅ |  | None | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_break5` | None | Column Break | None |  |  |  | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  |  | 0 | None |
| `item_tax_rate` | Item Tax Rate | Small Text | None |  | ✅ | ✅ | None | None |
| `actual_batch_qty` | Available Batch Qty at Warehouse | Float | None |  |  | ✅ | None | None |
| `actual_qty` | Available Qty at Warehouse | Float | None |  |  | ✅ | None | None |
| `section_break_tlhi` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `column_break_ciit` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `edit_references` | References | Section Break | None |  |  |  | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `so_detail` | Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `pos_invoice_item` | POS Invoice Item | Data | None |  |  | ✅ | None | None |
| `column_break_74` | None | Column Break | None |  |  |  | None | None |
| `delivery_note` | Delivery Note | Link | Delivery Note |  |  | ✅ | None | None |
| `dn_detail` | Delivery Note Item | Data | None |  | ✅ | ✅ | None | None |
| `delivered_qty` | Delivered Qty | Float | None |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center | ✅ |  |  | :Company | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `section_break_54` | None | Section Break | None |  |  |  | None | None |
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
