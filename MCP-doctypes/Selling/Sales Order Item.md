# Master Control Plan: `Sales Order Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
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
| `customer_item_code` | Customer's Item Code | Data | None |  | ✅ | ✅ | None | None |
| `ensure_delivery_based_on_produced_serial_no` | Ensure Delivery Based on Produced Serial No | Check | None |  |  |  | 0 | None |
| `is_stock_item` | Is Stock Item | Check | None |  | ✅ |  | 0 | None |
| `reserve_stock` | Reserve Stock | Check | None |  |  |  | 1 | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `delivery_date` | Delivery Date | Date | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ | ✅ | None | None |
| `brand` | Brand Name | Link | Brand |  | ✅ | ✅ | None | None |
| `image_section` | Image | Section Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  | ✅ | None | None |
| `stock_qty` | Qty as per Stock UOM | Float | None |  |  | ✅ | None | None |
| `stock_reserved_qty` | Stock Reserved Qty (in Stock UOM) | Float | None |  |  | ✅ | 0 | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
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
| `section_break_simple1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Basic Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `grant_commission` | Grant Commission | Check | None |  |  | ✅ | 0 | None |
| `section_break_24` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `billed_amt` | Billed Amt | Currency | currency |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `gross_profit` | Gross Profit | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `drop_ship_section` | Drop Ship | Section Break | None |  |  |  | None | None |
| `delivered_by_supplier` | Supplier delivers to Customer | Check | None |  |  |  | 0 | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  |  | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  |  | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Delivery Warehouse | Link | Warehouse |  |  |  | None | None |
| `target_warehouse` | Customer Warehouse (Optional) | Link | Warehouse |  | ✅ |  | None | None |
| `prevdoc_docname` | Quotation | Link | Quotation |  |  | ✅ | None | None |
| `quotation_item` | quotation_item | Data | None |  | ✅ | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `against_blanket_order` | Against Blanket Order | Check | None |  |  |  | 0 | None |
| `blanket_order` | Blanket Order | Link | Blanket Order |  |  |  | None | None |
| `blanket_order_rate` | Blanket Order Rate | Currency | None |  |  | ✅ | None | None |
| `available_quantity_section` | Available Quantity | Section Break | None |  |  |  | None | None |
| `actual_qty` | Qty (Warehouse) | Float | None |  |  | ✅ | None | None |
| `column_break_jpky` | None | Column Break | None |  |  |  | None | None |
| `company_total_stock` | Qty (Company) | Float | None |  |  | ✅ | None | None |
| `manufacturing_section_section` | Manufacturing Section | Section Break | None |  |  |  | None | None |
| `bom_no` | BOM No | Link | BOM |  |  |  | None | None |
| `planning_section` | Planning | Section Break | None |  |  |  | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | None | None |
| `planned_qty` | Planned Quantity | Float | None |  | ✅ | ✅ | None | For Production |
| `production_plan_qty` | Production Plan Qty | Float | None |  |  | ✅ | None | None |
| `column_break_69` | None | Column Break | None |  |  |  | None | None |
| `work_order_qty` | Work Order Qty | Float | None |  |  | ✅ | None | None |
| `delivered_qty` | Delivered Qty | Float | None |  |  | ✅ | None | None |
| `produced_qty` | Produced Quantity | Float | None |  | ✅ | ✅ | None | For Production |
| `returned_qty` | Returned Qty | Float | None |  |  | ✅ | None | None |
| `picked_qty` | Picked Qty (in Stock UOM) | Float | None |  |  | ✅ | None | None |
| `shopping_cart_section` | Shopping Cart | Section Break | None |  |  |  | None | None |
| `additional_notes` | Additional Notes | Text | None |  |  |  | None | None |
| `section_break_63` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | None |
| `transaction_date` | Sales Order Date | Date | None |  | ✅ | ✅ | None | Used for Production Plan |
| `inter_transfer_reference_section` | Inter Transfer Reference | Section Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  |  | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  |  | ✅ | None | None |
| `column_break_89` | None | Column Break | None |  |  |  | None | None |
| `material_request_item` | Material Request Item | Data | None |  |  |  | None | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `column_break_ihdh` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 17
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
