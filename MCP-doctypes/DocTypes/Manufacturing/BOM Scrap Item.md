# Master Control Plan: `BOM Scrap Item`

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
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `quantity_and_rate` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `stock_qty` | Qty | Float | None | ✅ |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | None | None |
| `amount` | Amount | Currency | currency |  |  | ✅ | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `base_rate` | Basic Rate (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_amount` | Basic Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
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
