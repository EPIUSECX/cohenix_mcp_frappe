# Master Control Plan: `Share Balance`

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
| `share_type` | Share Type | Link | Share Type | ✅ |  | ✅ | None | None |
| `from_no` | From No | Int | None | ✅ |  | ✅ | None | None |
| `rate` | Rate | Int | None | ✅ |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `no_of_shares` | No of Shares | Int | None | ✅ |  | ✅ | None | None |
| `to_no` | To No | Int | None | ✅ |  | ✅ | None | None |
| `amount` | Amount | Int | None | ✅ |  | ✅ | None | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `is_company` | Is Company | Check | None |  | ✅ | ✅ | 0 | None |
| `current_state` | Current State | Select | 
Issued
Purchased |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
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
