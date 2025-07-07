# Master Control Plan: `Stock Reconciliation Item`

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
| `barcode` | Barcode | Data | None |  |  |  | None | None |
| `has_item_scanned` | Has Item Scanned | Data | None |  |  | ✅ | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `qty` | Quantity | Float | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  | ✅ | 0 | None |
| `serial_no_and_batch_section` | Serial No and Batch | Section Break | None |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch No | Button | None |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `reconcile_all_serial_batch` | Reconcile All Serial Nos / Batches | Check | None |  |  |  | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial / Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `current_serial_and_batch_bundle` | Current Serial / Batch Bundle | Link | Serial and Batch Bundle |  |  | ✅ | None | None |
| `section_break_lypk` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Long Text | None |  |  |  | None | None |
| `column_break_eefq` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `section_break_3` | Before reconciliation | Section Break | None |  |  |  | None | None |
| `current_qty` | Current Qty | Float | None |  |  | ✅ | 0 | None |
| `current_amount` | Current Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `current_valuation_rate` | Current Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `current_serial_no` | Current Serial No | Long Text | None |  |  | ✅ | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `quantity_difference` | Quantity Difference | Read Only | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `amount_difference` | Amount Difference | Currency | Company:company:default_currency |  |  | ✅ | None | None |


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
