# Master Control Plan: `Asset Repair Consumed Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
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
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `valuation_rate` | Valuation Rate | Currency | None |  |  |  | None | None |
| `consumed_quantity` | Consumed Quantity | Data | None |  |  |  | None | None |
| `total_value` | Total Value | Currency | None |  |  | ✅ | None | None |
| `serial_no` | Serial No | Small Text | None |  | ✅ |  | None | None |
| `column_break_xzfr` | None | Column Break | None |  |  |  | None | None |
| `pick_serial_and_batch` | Pick Serial / Batch | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |


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
