# Master Control Plan: `Pick List Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
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
| `item_code` | Item | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Text | None |  |  | ✅ | None | None |
| `item_group` | Item Group | Data | None |  |  | ✅ | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  | ✅ | None | None |
| `quantity_section` | Quantity | Section Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None | ✅ |  |  | 1 | None |
| `stock_qty` | Stock Qty | Float | None |  |  | ✅ | None | None |
| `picked_qty` | Picked Qty (in Stock UOM) | Float | None |  |  |  | None | None |
| `stock_reserved_qty` | Stock Reserved Qty (in Stock UOM) | Float | None |  |  | ✅ | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM |  |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `delivered_qty` | Delivered Qty (in Stock UOM) | Float | None |  |  | ✅ | 0 | None |
| `serial_no_and_batch_section` | Serial No and Batch | Section Break | None |  |  |  | None | None |
| `pick_serial_and_batch` | Pick Serial / Batch No | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `section_break_ecxc` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Small Text | None |  |  |  | None | None |
| `column_break_belw` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `column_break_15` | Reference | Section Break | None |  |  |  | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `sales_order_item` | Sales Order Item | Data | None |  | ✅ | ✅ | None | None |
| `product_bundle_item` | Product Bundle Item | Data | None |  | ✅ | ✅ | None | product bundle item row's name in sales order. Also indicates that picked item is to be used for a product bundle |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `material_request_item` | Material Request Item | Data | None |  |  | ✅ | None | None |


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
