# Master Control Plan: `Payment Schedule`

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
| `payment_term` | Payment Term | Link | Payment Term |  |  |  | None | None |
| `section_break_15` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `due_date` | Due Date | Date | None | ✅ |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `invoice_portion` | Invoice Portion | Percent | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `discount_type` | Discount Type | Select | Percentage
Amount |  |  |  | Percentage | None |
| `discount_date` | Discount Date | Date | None |  |  |  | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `discount` | Discount | Float | None |  |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `payment_amount` | Payment Amount | Currency | currency | ✅ |  |  | None | None |
| `outstanding` | Outstanding | Currency | currency |  |  | ✅ | None | None |
| `paid_amount` | Paid Amount | Currency | currency |  |  |  | None | None |
| `discounted_amount` | Discounted Amount | Currency | None |  |  | ✅ | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `base_payment_amount` | Payment Amount (Company Currency) | Currency | Company:company:default_currency |  |  |  | None | None |
| `base_outstanding` | Outstanding (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_paid_amount` | Paid Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |


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
