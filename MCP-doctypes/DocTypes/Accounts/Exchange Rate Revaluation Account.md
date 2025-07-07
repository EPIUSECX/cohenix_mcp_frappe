# Master Control Plan: `Exchange Rate Revaluation Account`

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
| `account` | Account | Link | Account | ✅ |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `account_currency` | Account Currency | Link | Currency |  |  | ✅ | None | None |
| `account_balances` | None | Section Break | None |  |  |  | None | None |
| `balance_in_account_currency` | Balance In Account Currency | Currency | account_currency |  |  | ✅ | None | None |
| `column_break_46yz` | None | Column Break | None |  |  |  | None | None |
| `new_balance_in_account_currency` | New Balance In Account Currency | Currency | account_currency |  |  | ✅ | None | None |
| `balances` | None | Section Break | None |  |  |  | None | None |
| `current_exchange_rate` | Current Exchange Rate | Float | None |  |  | ✅ | None | None |
| `column_break_xown` | None | Column Break | None |  |  |  | None | None |
| `new_exchange_rate` | New Exchange Rate | Float | None | ✅ |  |  | None | None |
| `column_break_9` | None | Section Break | None |  |  |  | None | None |
| `balance_in_base_currency` | Balance In Base Currency | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_ukce` | None | Column Break | None |  |  |  | None | None |
| `new_balance_in_base_currency` | New Balance In Base Currency | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_ngrs` | None | Section Break | None |  |  |  | None | None |
| `gain_loss` | Gain/Loss | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `zero_balance` | Zero Balance | Check | None |  |  |  | 0 | This Account has '0' balance in either Base Currency or Account Currency |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
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
