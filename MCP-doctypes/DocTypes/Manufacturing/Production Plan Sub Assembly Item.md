# Master Control Plan: `Production Plan Sub Assembly Item`

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
| `production_item` | Sub Assembly Item Code | Link | Item |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `fg_warehouse` | Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `parent_item_code` | Finished Good | Link | Item |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `bom_no` | Bom No | Link | BOM |  |  |  | None | None |
| `bom_level` | Level (BOM) | Int | None |  |  | ✅ | None | None |
| `type_of_manufacturing` | Manufacturing Type | Select | In House
Subcontract
Material Request |  |  |  | In House | None |
| `section_break_4rxf` | Quantity | Section Break | None |  |  |  | None | None |
| `required_qty` | Required Qty | Float | None |  |  |  | None | None |
| `column_break_xfhm` | None | Column Break | None |  |  |  | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `qty` | Qty to Order | Float | None |  |  | ✅ | None | None |
| `subcontracting_section` | Subcontracting | Section Break | None |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  |  | ✅ | None | None |
| `work_order_details_section` | Manufacturing | Section Break | None |  |  |  | None | None |
| `production_plan_item` | Production Plan Item | Data | None |  | ✅ | ✅ | None | None |
| `wo_produced_qty` | Produced Qty | Float | None |  |  | ✅ | None | None |
| `stock_reserved_qty` | Stock Reserved Qty | Float | None |  |  | ✅ | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | None | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `indent` | Indent | Int | None |  |  |  | None | None |
| `section_break_19` | Item Details | Section Break | None |  |  |  | None | None |
| `schedule_date` | Schedule Date | Datetime | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `actual_qty` | Actual Qty | Float | None |  |  | ✅ | None | None |
| `column_break_22` | None | Column Break | None |  |  |  | None | None |
| `description` | description | Small Text | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
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
