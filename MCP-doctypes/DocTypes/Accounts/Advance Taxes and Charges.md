# Master Control Plan: `Advance Taxes and Charges`

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
| `add_deduct_tax` | Add Or Deduct | Select | Add
Deduct | ✅ |  |  | None | None |
| `charge_type` | Type | Select | 
Actual
On Paid Amount
On Previous Row Amount
On Previous Row Total | ✅ |  |  | None | None |
| `row_id` | Reference Row # | Data | None |  |  |  | None | None |
| `account_head` | Account Head | Link | Account | ✅ |  |  | None | None |
| `col_break_1` | None | Column Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None | ✅ |  |  | None | None |
| `included_in_paid_amount` | Considered In Paid Amount | Check | None |  |  |  | 0 | None |
| `set_by_item_tax_template` | Set by Item Tax Template | Check | None |  | ✅ | ✅ | 0 | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `rate` | Tax Rate | Float | None |  |  |  | None | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `currency` | Account Currency | Link | Currency |  |  | ✅ | None | None |
| `net_amount` | Net Amount | Currency | currency |  |  | ✅ | None | None |
| `tax_amount` | Amount | Currency | currency |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `allocated_amount` | Allocated Amount | Currency | currency |  |  |  | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `base_tax_amount` | Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_amount` | Net Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |


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
