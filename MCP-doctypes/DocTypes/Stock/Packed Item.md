# Master Control Plan: `Packed Item`

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
| `parent_item` | Parent Item | Link | Item |  |  | ✅ | None | None |
| `item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `warehouse` | From Warehouse | Link | Warehouse |  |  |  | None | None |
| `target_warehouse` | To Warehouse (Optional) | Link | Warehouse |  |  |  | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None |  |  | ✅ | None | None |
| `rate` | Rate | Currency | currency |  |  | ✅ | None | None |
| `uom` | UOM | Link | UOM |  |  | ✅ | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `pick_serial_and_batch` | Pick Serial / Batch No | Button | None |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `section_break_bgys` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `column_break_qlha` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `actual_batch_qty` | Actual Batch Quantity | Float | None |  |  | ✅ | None | None |
| `section_break_13` | None | Section Break | None |  |  |  | None | None |
| `actual_qty` | Actual Qty | Float | None |  |  | ✅ | None | None |
| `projected_qty` | Projected Qty | Float | None |  |  | ✅ | None | None |
| `ordered_qty` | Ordered Qty | Float | None |  |  | ✅ | None | None |
| `packed_qty` | Packed Qty | Float | None |  |  | ✅ | 0 | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `incoming_rate` | Incoming Rate | Currency | None |  |  | ✅ | None | None |
| `picked_qty` | Picked Qty | Float | None |  |  | ✅ | None | None |
| `page_break` | Page Break | Check | None |  |  | ✅ | 0 | None |
| `prevdoc_doctype` | Prevdoc DocType | Data | None |  | ✅ | ✅ | None | None |
| `parent_detail_docname` | Parent Detail docname | Data | None |  | ✅ | ✅ | None | None |


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
