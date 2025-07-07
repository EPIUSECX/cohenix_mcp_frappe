# Master Control Plan: `Accounting Dimension Detail`

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
| `company` | Company | Link | Company |  |  |  | None | None |
| `reference_document` | Reference Document | Link | DocType |  | ✅ | ✅ | None | None |
| `default_dimension` | Default Dimension | Dynamic Link | reference_document |  |  |  | None | None |
| `mandatory_for_bs` | Mandatory For Balance Sheet | Check | None |  |  |  | 0 | None |
| `mandatory_for_pl` | Mandatory For Profit and Loss Account | Check | None |  |  |  | 0 | None |
| `column_break_lqns` | None | Column Break | None |  |  |  | None | None |
| `automatically_post_balancing_accounting_entry` | Automatically post balancing accounting entry | Check | None |  |  |  | 0 | None |
| `offsetting_account` | Offsetting Account | Link | Account |  |  |  | None | None |


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
