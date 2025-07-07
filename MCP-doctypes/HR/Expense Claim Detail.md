# Master Control Plan: `Expense Claim Detail`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
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
| `expense_date` | Expense Date | Date | None |  |  |  | Today | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `expense_type` | Expense Claim Type | Link | Expense Claim Type | ✅ |  |  | None | None |
| `default_account` | Default Account | Link | Account |  | ✅ | ✅ | None | None |
| `description_sb` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `amounts_sb` | None | Section Break | None |  |  |  | None | None |
| `amount` | Amount | Currency | Company:company:default_currency | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `sanctioned_amount` | Sanctioned Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |


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
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Claims by Type` | Claims by Type | Group By | HR |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
