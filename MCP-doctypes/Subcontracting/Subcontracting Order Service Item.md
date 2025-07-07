# Master Control Plan: `Subcontracting Order Service Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Subcontracting`
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
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | currency | ✅ |  | ✅ | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `fg_item` | Finished Good Item | Link | Item | ✅ |  |  | None | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `fg_item_qty` | Finished Good Item Quantity | Float | None | ✅ |  |  | 1 | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  | ✅ | ✅ | None | None |
| `section_break_kphn` | Reference | Section Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `column_break_piqi` | None | Column Break | None |  |  |  | None | None |
| `material_request_item` | Material Request Item | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
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
