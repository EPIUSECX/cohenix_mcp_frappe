# Master Control Plan: `Opening Invoice Creation Tool Item`

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
| `invoice_number` | Invoice Number | Data | None |  |  |  | None | Reference number of the invoice from the previous system |
| `party_type` | Party Type | Link | DocType |  | ✅ | ✅ | None | None |
| `party` | Party | Dynamic Link | party_type | ✅ |  |  | None | None |
| `temporary_opening_account` | Temporary Opening Account | Link | Account |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  |  | Today | None |
| `due_date` | Due Date | Date | None |  |  |  | Today | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | Opening Invoice Item | None |
| `outstanding_amount` | Outstanding Amount | Currency | None | ✅ |  |  | 0 | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `qty` | Quantity | Data | None |  |  |  | 1 | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |


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
