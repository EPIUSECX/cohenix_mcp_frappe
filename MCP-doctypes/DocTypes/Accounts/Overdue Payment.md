# Master Control Plan: `Overdue Payment`

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
| `sales_invoice` | Sales Invoice | Link | Sales Invoice | ✅ |  | ✅ | None | None |
| `payment_schedule` | Payment Schedule | Data | None |  |  | ✅ | None | None |
| `dunning_level` | Dunning Level | Int | None |  |  | ✅ | 1 | None |
| `payment_term` | Payment Term | Link | Payment Term |  |  | ✅ | None | None |
| `section_break_15` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  | ✅ | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `due_date` | Due Date | Date | None |  |  | ✅ | None | None |
| `overdue_days` | Overdue Days | Data | None |  |  | ✅ | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `invoice_portion` | Invoice Portion | Percent | None |  |  | ✅ | None | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `payment_amount` | Payment Amount | Currency | currency |  |  | ✅ | None | None |
| `outstanding` | Outstanding | Currency | currency |  |  | ✅ | None | None |
| `paid_amount` | Paid Amount | Currency | currency |  |  |  | None | None |
| `discounted_amount` | Discounted Amount | Currency | None |  |  | ✅ | 0 | None |
| `interest` | Interest | Currency | currency |  |  | ✅ | None | None |


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
