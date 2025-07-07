# Master Control Plan: `BOM Explosion Item`

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
| `item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `cb` | None | Column Break | None |  |  |  | None | None |
| `source_warehouse` | Source Warehouse | Link | Warehouse |  |  | ✅ | None | None |
| `operation` | Operation | Link | Operation |  |  | ✅ | None | None |
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `stock_qty` | Stock Qty | Float | None |  |  | ✅ | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `qty_consumed_per_unit` | Qty Consumed Per Unit | Float | None |  |  | ✅ | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `include_item_in_manufacturing` | Include Item In Manufacturing | Check | None |  |  | ✅ | 0 | None |
| `sourced_by_supplier` | Sourced by Supplier | Check | None |  |  | ✅ | 0 | None |


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
