# Master Control Plan: `Purchase Order Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
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
| `fg_item` | Finished Good | Link | Item |  |  |  | None | None |
| `fg_item_qty` | Finished Good Qty | Float | None |  |  |  | 1 | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `supplier_part_no` | Supplier Part Number | Data | None |  | ✅ | ✅ | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `brand` | Brand | Link | Brand |  | ✅ | ✅ | None | None |
| `product_bundle` | Product Bundle | Link | Product Bundle |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `schedule_date` | Required By | Date | None | ✅ |  |  | None | None |
| `expected_delivery_date` | Expected Delivery Date | Date | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ | ✅ | None | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `subcontracted_quantity` | Subcontracted Quantity | Float | None |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  |  | None | None |
| `stock_qty` | Qty in Stock UOM | Float | None |  |  | ✅ | None | None |
| `sec_break1` | None | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  |  | None | None |
| `last_purchase_rate` | Last Purchase Rate | Currency | currency |  |  | ✅ | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `discount_and_margin_section` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount on Price List Rate (%) | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `sec_break2` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `apply_tds` | Apply TDS | Check | None |  |  |  | 1 | None |
| `section_break_29` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `warehouse_and_reference` | Warehouse Settings | Section Break | None |  |  |  | None | None |
| `from_warehouse` | From Warehouse | Link | Warehouse |  |  |  | None | None |
| `warehouse` | Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `column_break_54` | None | Column Break | None |  |  |  | None | None |
| `actual_qty` | Available Qty at Target Warehouse | Float | None |  |  | ✅ | None | None |
| `company_total_stock` | Available Qty at Company | Float | None |  |  | ✅ | None | None |
| `references_section` | References | Section Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `material_request_item` | Material Request Item | Data | None |  | ✅ | ✅ | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  |  | None | None |
| `sales_order_item` | Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `sales_order_packed_item` | Sales Order Packed Item | Data | None |  |  |  | None | None |
| `supplier_quotation` | Supplier Quotation | Link | Supplier Quotation |  |  | ✅ | None | None |
| `supplier_quotation_item` | Supplier Quotation Item | Link | Supplier Quotation Item |  | ✅ | ✅ | None | None |
| `col_break5` | None | Column Break | None |  |  |  | None | None |
| `delivered_by_supplier` | To be Delivered to Customer | Check | None |  |  | ✅ | 0 | None |
| `against_blanket_order` | Against Blanket Order | Check | None |  |  |  | 0 | None |
| `blanket_order` | Blanket Order | Link | Blanket Order |  |  |  | None | None |
| `blanket_order_rate` | Blanket Order Rate | Currency | None |  |  | ✅ | None | None |
| `section_break_56` | Billed, Received & Returned | Section Break | None |  |  |  | None | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `returned_qty` | Returned Qty | Float | None |  |  | ✅ | None | None |
| `column_break_60` | None | Column Break | None |  |  |  | None | None |
| `billed_amt` | Billed Amount | Currency | currency |  |  | ✅ | None | None |
| `accounting_details` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `column_break_fyqr` | None | Column Break | None |  |  |  | None | None |
| `wip_composite_asset` | WIP Composite Asset | Link | Asset |  |  |  | None | None |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `bom` | BOM | Link | BOM |  |  | ✅ | None | None |
| `include_exploded_items` | Include Exploded Items | Check | None |  |  |  | 0 | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  | ✅ | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions  | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `more_info_section_break` | More Information | Section Break | None |  |  |  | None | None |
| `is_fixed_asset` | Is Fixed Asset | Check | None |  |  | ✅ | 0 | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | Tax detail table fetched from item master as a string and stored in this field.
Used for Taxes and Charges |
| `section_break_72` | None | Section Break | None |  |  |  | None | None |
| `production_plan` | Production Plan | Link | Production Plan |  |  | ✅ | None | None |
| `production_plan_item` | Production Plan Item | Data | None |  | ✅ | ✅ | None | None |
| `production_plan_sub_assembly_item` | Production Plan Sub Assembly Item | Data | None |  | ✅ | ✅ | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |
| `column_break_pjyo` | None | Column Break | None |  |  |  | None | None |
| `job_card` | Job Card | Link | Job Card |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 24
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
