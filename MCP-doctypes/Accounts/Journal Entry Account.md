# Master Control Plan: `Journal Entry Account`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
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
| `account` | Account | Link | Account | ✅ |  |  | None | None |
| `account_type` | Account Type | Data | None |  | ✅ |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account |  |  |  | None | None |
| `party_type` | Party Type | Link | DocType |  |  |  | None | None |
| `party` | Party | Dynamic Link | party_type |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | If Income or Expense |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_section` | Currency | Section Break | None |  |  |  | None | None |
| `account_currency` | Account Currency | Link | Currency |  |  | ✅ | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `exchange_rate` | Exchange Rate | Float | None |  |  |  | None | None |
| `sec_break1` | Amount | Section Break | None |  |  |  | None | None |
| `debit_in_account_currency` | Debit | Currency | account_currency |  |  |  | None | None |
| `debit` | Debit in Company Currency | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `credit_in_account_currency` | Credit | Currency | account_currency |  |  |  | None | None |
| `credit` | Credit in Company Currency | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `reference` | Reference | Section Break | None |  |  |  | None | None |
| `reference_type` | Reference Type | Select | 
Sales Invoice
Purchase Invoice
Journal Entry
Sales Order
Purchase Order
Expense Claim
Asset
Loan
Payroll Entry
Employee Advance
Exchange Rate Revaluation
Invoice Discounting
Fees
Full and Final Statement
Payment Entry |  |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_type |  |  |  | None | None |
| `reference_due_date` | Reference Due Date | Date | None |  |  |  | None | None |
| `reference_detail_no` | Reference Detail No | Data | None |  | ✅ |  | None | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `is_advance` | Is Advance | Select | No
Yes |  |  |  | None | None |
| `user_remark` | User Remark | Small Text | None |  |  |  | None | None |
| `against_account` | Against Account | Text | None |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
- **Dynamic Link Fields:** 2
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
