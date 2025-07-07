# Master Control Plan: `Payment Order Reference`

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
| `reference_doctype` | Type | Link | DocType | ✅ |  | ✅ | None | None |
| `reference_name` | Name | Dynamic Link | reference_doctype | ✅ |  | ✅ | None | None |
| `amount` | Amount | Currency | None | ✅ |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  | ✅ | None | None |
| `payment_request` | Payment Request | Link | Payment Request |  |  | ✅ | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  | ✅ | None | None |
| `bank_account_details` | Bank Account Details | Section Break | None |  |  |  | None | None |
| `bank_account` | Bank Account | Link | Bank Account | ✅ |  | ✅ | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `account` | Account | Link | Account |  |  | ✅ | None | None |
| `payment_reference` | Payment Reference | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 6
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
