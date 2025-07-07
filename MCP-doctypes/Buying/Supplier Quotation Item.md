# Master Control Plan: `Supplier Quotation Item`

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
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `supplier_part_no` | Supplier Part Number | Data | None |  | ✅ | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `lead_time_days` | Supplier Lead Time (days) | Int | None |  |  |  | None | None |
| `expected_delivery_date` | Expected Delivery Date | Date | None |  |  |  | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  | ✅ | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  | ✅ | None | None |
| `stock_qty` | Qty as per Stock UOM | Float | None |  |  | ✅ | None | None |
| `sec_break_price_list` | None | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  |  | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `discount_and_margin_section` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `col_break_6` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount on Price List Rate (%) | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_break1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `section_break_24` | None | Section Break | None |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | None |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  | ✅ | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  | ✅ | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `prevdoc_doctype` | Reference Document Type | Data | None |  | ✅ | ✅ | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `request_for_quotation` | Request for Quotation | Link | Request for Quotation |  |  | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `material_request_item` | Material Request Item | Data | None |  | ✅ | ✅ | None | None |
| `request_for_quotation_item` | Request for Quotation Item | Data | None |  | ✅ | ✅ | None | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | Tax detail table fetched from item master as a string and stored in this field.
Used for Taxes and Charges |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `ad_sec_break` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `section_break_44` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 14
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
