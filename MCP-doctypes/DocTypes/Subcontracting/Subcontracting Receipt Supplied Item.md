# Master Control Plan: `Subcontracting Receipt Supplied Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Subcontracting`
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
| `main_item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `rm_item_code` | Raw Material Item Code | Link | Item |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `bom_detail_no` | BOM Detail No | Data | None |  | ✅ | ✅ | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  | ✅ | ✅ | 1 | None |
| `reference_name` | Reference Name | Data | None |  | ✅ | ✅ | None | None |
| `secbreak_1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `secbreak_2` | None | Section Break | None |  |  |  | None | None |
| `available_qty_for_consumption` | Available Qty For Consumption | Float | None |  |  | ✅ | 0 | None |
| `required_qty` | Required Qty | Float | None |  |  | ✅ | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `consumed_qty` | Consumed Qty | Float | None | ✅ |  | ✅ | None | None |
| `current_stock` | Current Stock | Float | None |  |  | ✅ | None | None |
| `secbreak_3` | None | Section Break | None |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch Bundle | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial / Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `subcontracting_order` | Subcontracting Order | Link | Subcontracting Order |  | ✅ | ✅ | None | None |
| `section_break_zwnh` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `column_break_qibi` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |


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
