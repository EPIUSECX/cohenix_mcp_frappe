# Master Control Plan: `Production Plan Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
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
| `include_exploded_items` | Include Exploded Items | Check | None |  |  |  | 1 | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `bom_no` | BOM No | Link | BOM | ✅ |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `planned_qty` | Planned Qty | Float | None | ✅ |  |  | None | None |
| `stock_uom` | UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `warehouse` | Finished Goods Warehouse | Link | Warehouse |  |  |  | None | None |
| `planned_start_date` | Planned Start Date | Datetime | None | ✅ |  |  | Today | None |
| `section_break_9` | Quantity and Description | Section Break | None |  |  |  | None | None |
| `pending_qty` | Pending Qty | Float | None |  |  | ✅ | 0 | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | 0 | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  | ✅ | None | None |
| `produced_qty` | Produced Qty | Float | None |  |  | ✅ | 0 | None |
| `reference_section` | Reference | Section Break | None |  |  |  | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `sales_order_item` | Sales Order Item | Data | None |  | ✅ |  | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `material_request_item` | material_request_item | Data | None |  | ✅ |  | None | None |
| `product_bundle_item` | Product Bundle Item | Link | Item |  |  | ✅ | None | None |
| `item_reference` | Item Reference | Data | None |  | ✅ |  | None | None |
| `temporary_name` | temporary name | Data | None |  | ✅ |  | None | None |


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
