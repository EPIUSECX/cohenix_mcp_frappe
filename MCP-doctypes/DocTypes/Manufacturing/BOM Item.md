# Master Control Plan: `BOM Item`

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
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `operation` | Item operation | Link | Operation |  |  |  | None | None |
| `operation_row_id` | Operation ID | Int | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `do_not_explode` | Do Not Explode | Check | None |  |  |  | 0 | None |
| `bom_no` | BOM No | Link | BOM |  |  |  | None | None |
| `source_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `allow_alternative_item` | Allow Alternative Item | Check | None |  |  |  | 0 | None |
| `is_stock_item` | Is Stock Item | Check | None |  |  | ✅ | 0 | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Item Description | Text Editor | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None | ✅ |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `stock_qty` | Stock Qty | Float | None |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  |  | None | None |
| `rate_amount_section` | Rate & Amount | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `base_rate` | Basic Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `base_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_18` | None | Section Break | None |  |  |  | None | None |
| `qty_consumed_per_unit` | Qty Consumed Per Unit | Float | None |  | ✅ | ✅ | None | None |
| `section_break_27` | None | Section Break | None |  |  |  | None | None |
| `has_variants` | Has Variants | Check | None |  |  | ✅ | 0 | None |
| `include_item_in_manufacturing` | Include Item In Manufacturing | Check | None |  |  |  | 0 | None |
| `original_item` | Original Item | Link | Item |  | ✅ | ✅ | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `sourced_by_supplier` | Sourced by Supplier | Check | None |  |  |  | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
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
