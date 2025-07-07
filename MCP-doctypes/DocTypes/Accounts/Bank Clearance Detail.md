# Master Control Plan: `Bank Clearance Detail`

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
| `payment_document` | Payment Document | Link | DocType |  |  |  | None | None |
| `payment_entry` | Payment Entry | Dynamic Link | payment_document |  |  |  | None | None |
| `against_account` | Against Account | Data | None |  |  | ✅ | None | None |
| `amount` | Amount | Data | None |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  | ✅ | None | None |
| `cheque_number` | Cheque Number | Data | None |  |  | ✅ | None | None |
| `cheque_date` | Cheque Date | Date | None |  |  | ✅ | None | None |
| `clearance_date` | Clearance Date | Date | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
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
