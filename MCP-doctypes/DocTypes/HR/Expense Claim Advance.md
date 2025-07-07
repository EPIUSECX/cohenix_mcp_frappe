# Master Control Plan: `Expense Claim Advance`

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
| `employee_advance` | Employee Advance | Link | Employee Advance | ✅ |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  | ✅ | None | None |
| `advance_paid` | Advance Paid | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `unclaimed_amount` | Unclaimed Amount | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `return_amount` | Returned Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `allocated_amount` | Allocated Amount | Currency | Company:company:default_currency |  |  |  | None | None |
| `advance_account` | Advance Account | Link | Account |  | ✅ |  | None | None |


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
