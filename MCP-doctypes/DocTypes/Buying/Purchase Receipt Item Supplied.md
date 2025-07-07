# Master Control Plan: `Purchase Receipt Item Supplied`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
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
| `stock_uom` | Stock Uom | Link | UOM |  |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  | ✅ | ✅ | None | None |
| `reference_name` | Reference Name | Data | None |  | ✅ | ✅ | None | None |
| `secbreak_1` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `secbreak_2` | None | Section Break | None |  |  |  | None | None |
| `required_qty` | Available Qty For Consumption | Float | None |  |  | ✅ | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `consumed_qty` | Qty to Be Consumed | Float | None | ✅ |  |  | None | None |
| `current_stock` | Current Stock | Float | None |  |  | ✅ | None | None |
| `secbreak_3` | None | Section Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
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
