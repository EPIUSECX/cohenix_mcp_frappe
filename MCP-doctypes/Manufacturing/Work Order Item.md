# Master Control Plan: `Work Order Item`

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
| `operation` | Operation | Link | Operation |  |  |  | None | None |
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `source_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `operation_row_id` | Operation Row Id | Int | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `description` | Description | Text | None |  |  | ✅ | None | None |
| `allow_alternative_item` | Allow Alternative Item | Check | None |  |  |  | 0 | None |
| `include_item_in_manufacturing` | Include Item In Manufacturing | Check | None |  |  |  | 0 | None |
| `qty_section` | Qty | Section Break | None |  |  |  | None | None |
| `required_qty` | Required Qty | Float | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  |  | None | None |
| `rate` | Rate | Currency | None |  |  | ✅ | None | None |
| `amount` | Amount | Currency | None |  |  | ✅ | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `transferred_qty` | Transferred Qty | Float | None |  |  | ✅ | None | None |
| `consumed_qty` | Consumed Qty | Float | None |  |  | ✅ | None | None |
| `returned_qty` | Returned Qty  | Float | None |  |  | ✅ | None | None |
| `section_break_idhr` | None | Section Break | None |  |  |  | None | None |
| `available_qty_at_source_warehouse` | Available Qty at Source Warehouse | Float | None |  |  | ✅ | None | None |
| `available_qty_at_wip_warehouse` | Available Qty at WIP Warehouse | Float | None |  |  | ✅ | None | None |
| `column_break_jash` | None | Column Break | None |  |  |  | None | None |
| `stock_reserved_qty` | Stock Reserved Qty | Float | None |  |  | ✅ | None | None |
| `is_additional_item` | Is Additional Item | Check | None |  |  | ✅ | 0 | None |
| `voucher_detail_reference` | Voucher Detail Reference | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
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
