# Master Control Plan: `Payment Entry Reference`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
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
| `reference_doctype` | Type | Link | DocType | ✅ |  |  | None | None |
| `reference_name` | Name | Dynamic Link | reference_doctype | ✅ |  |  | None | None |
| `due_date` | Due Date | Date | None |  |  | ✅ | None | None |
| `bill_no` | Supplier Invoice No | Data | None |  |  | ✅ | None | None |
| `payment_term` | Payment Term | Link | Payment Term |  |  |  | None | None |
| `payment_term_outstanding` | Payment Term Outstanding | Float | None |  |  | ✅ | None | None |
| `account_type` | Account Type | Data | None |  |  |  | None | None |
| `payment_type` | Payment Type | Data | None |  |  |  | None | None |
| `reconcile_effect_on` | Reconcile Effect On | Date | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `total_amount` | Grand Total | Float | None |  |  | ✅ | None | None |
| `outstanding_amount` | Outstanding | Float | None |  |  | ✅ | None | None |
| `allocated_amount` | Allocated | Float | None |  |  |  | None | None |
| `exchange_rate` | Exchange Rate | Float | None |  |  | ✅ | None | None |
| `exchange_gain_loss` | Exchange Gain/Loss | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `account` | Account | Link | Account |  |  |  | None | None |
| `payment_request` | Payment Request | Link | Payment Request |  |  |  | None | None |
| `payment_request_outstanding` | Payment Request Outstanding | Float | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 1
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
