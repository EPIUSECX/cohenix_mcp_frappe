# Master Control Plan: `Quotation Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
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
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `customer_item_code` | Customer's Item Code | Data | None |  | ✅ | ✅ | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `is_free_item` | Is Free Item | Check | None |  |  | ✅ | 0 | None |
| `is_alternative` | Is Alternative | Check | None |  |  |  | 0 | None |
| `has_alternative_item` | Has Alternative Item | Check | None |  | ✅ | ✅ | 0 | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  | ✅ | ✅ | None | None |
| `brand` | Brand | Link | Brand |  | ✅ | ✅ | None | None |
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
| `available_quantity_section` | Available Quantity | Section Break | None |  |  |  | None | None |
| `actual_qty` | Qty (Warehouse) | Float | None |  |  | ✅ | None | None |
| `column_break_ylrv` | None | Column Break | None |  |  |  | None | None |
| `company_total_stock` | Qty (Company) | Float | None |  |  | ✅ | None | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `price_list_rate` | Price List Rate | Currency | currency |  |  | ✅ | None | None |
| `base_price_list_rate` | Price List Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `discount_and_margin` | Discount and Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | None | None |
| `rate_with_margin` | Rate With Margin | Currency | currency |  |  | ✅ | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `discount_percentage` | Discount (%) on Price List Rate with Margin | Percent | None |  |  |  | None | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | None | None |
| `distributed_discount_amount` | Distributed Discount Amount | Currency | currency |  |  |  | None | None |
| `base_rate_with_margin` | Rate With Margin (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `net_rate` | Net Rate | Currency | currency |  |  | ✅ | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `item_tax_template` | Item Tax Template | Link | Item Tax Template |  |  |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_rate` | Net Rate (Company Currency) | Currency | None |  |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `pricing_rules` | Pricing Rules | Small Text | None |  | ✅ | ✅ | None | None |
| `stock_uom_rate` | Rate of Stock UOM | Currency | currency |  |  | ✅ | None | None |
| `section_break_43` | None | Section Break | None |  |  |  | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `gross_profit` | Gross Profit | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `item_weight_details` | Item Weight Details | Section Break | None |  |  |  | None | None |
| `weight_per_unit` | Weight Per Unit | Float | None |  |  | ✅ | None | None |
| `total_weight` | Total Weight | Float | None |  |  | ✅ | None | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `weight_uom` | Weight UOM | Link | UOM |  |  | ✅ | None | None |
| `reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `against_blanket_order` | Against Blanket Order | Check | None |  |  |  | 0 | None |
| `blanket_order` | Blanket Order | Link | Blanket Order |  |  |  | None | None |
| `blanket_order_rate` | Blanket Order Rate | Currency | None |  |  | ✅ | None | None |
| `column_break_30` | None | Column Break | None |  |  |  | None | None |
| `prevdoc_doctype` | Against Doctype | Link | DocType |  | ✅ | ✅ | None | None |
| `prevdoc_docname` | Against Docname | Dynamic Link | prevdoc_doctype |  |  | ✅ | None | None |
| `item_balance` | Planning | Section Break | None |  |  |  | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `stock_balance` | Stock Balance | Button | None |  |  |  | None | None |
| `item_tax_rate` | Item Tax Rate | Code | None |  | ✅ | ✅ | None | None |
| `shopping_cart_section` | Shopping Cart | Section Break | None |  |  |  | None | None |
| `additional_notes` | Additional Notes | Text | None |  |  |  | None | None |
| `section_break_61` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
- **Dynamic Link Fields:** 1
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
