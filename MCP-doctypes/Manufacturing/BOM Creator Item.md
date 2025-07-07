# Master Control Plan: `BOM Creator Item`

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
| `item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `column_break_f63f` | None | Column Break | None |  |  |  | None | None |
| `fg_item` | Finished Goods Item | Link | Item | ✅ |  |  | None | None |
| `is_expandable` | Is Expandable | Check | None |  |  | ✅ | 0 | None |
| `sourced_by_supplier` | Sourced by Supplier | Check | None |  |  |  | 0 | None |
| `bom_created` | BOM Created | Check | None |  | ✅ |  | 0 | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  | ✅ | 0 | None |
| `operation_section` | Operation | Section Break | None |  |  |  | None | None |
| `operation` | Operation | Link | Operation |  |  |  | None | None |
| `column_break_cbnk` | None | Column Break | None |  |  |  | None | None |
| `description_section` | Description | Section Break | None |  |  |  | None | None |
| `description` | None | Small Text | None |  |  |  | None | None |
| `quantity_and_rate_section` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None |  |  |  | None | None |
| `rate` | Rate | Currency | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  |  | None | None |
| `column_break_bgnb` | None | Column Break | None |  |  |  | None | None |
| `stock_qty` | Stock Qty | Float | None |  |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `amount_section` | Amount | Section Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | None |  |  | ✅ | None | None |
| `column_break_yuca` | None | Column Break | None |  |  |  | None | None |
| `base_rate` | Base Rate | Currency | None |  | ✅ |  | None | None |
| `base_amount` | Base Amount | Currency | None |  | ✅ |  | None | None |
| `section_break_wtld` | None | Section Break | None |  |  |  | None | None |
| `do_not_explode` | Do Not Explode | Check | None |  | ✅ |  | 1 | None |
| `parent_row_no` | Parent Row No | Data | None |  |  |  | None | None |
| `fg_reference_id` | Finished Goods Reference | Data | None |  |  | ✅ | None | None |
| `column_break_sulm` | None | Column Break | None |  |  |  | None | None |
| `instruction` | Instruction | Small Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
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
