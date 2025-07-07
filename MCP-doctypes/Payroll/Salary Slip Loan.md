# Master Control Plan: `Salary Slip Loan`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Payroll`
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
| `loan` | Loan | Link | Loan | ✅ |  | ✅ | None | None |
| `loan_product` | Loan Product | Link | Loan Product |  |  | ✅ | None | None |
| `loan_account` | Loan Account | Link | Account |  |  | ✅ | None | None |
| `interest_income_account` | Interest Income Account | Link | Account |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `principal_amount` | Principal Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `interest_amount` | Interest Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `total_payment` | Total Payment | Currency | Company:company:default_currency |  |  |  | None | None |
| `loan_repayment_entry` | Loan Repayment Entry | Link | Loan Repayment |  |  | ✅ | None | None |


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
