# Master Control Plan: `Purchase Invoice Advance`

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
| `reference_type` | Reference Type | Link | DocType |  |  | ✅ | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_type |  |  | ✅ | None | None |
| `remarks` | Remarks | Text | None |  |  | ✅ | None | None |
| `reference_row` | Reference Row | Data | None |  | ✅ | ✅ | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `advance_amount` | Advance Amount | Currency | party_account_currency |  |  | ✅ | None | None |
| `allocated_amount` | Allocated Amount | Currency | party_account_currency |  |  |  | None | None |
| `exchange_gain_loss` | Exchange Gain/Loss | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `ref_exchange_rate` | Reference Exchange Rate | Float | None |  |  | ✅ | None | None |
| `difference_posting_date` | Difference Posting Date | Date | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
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
