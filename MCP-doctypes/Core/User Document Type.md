# Master Control Plan: `User Document Type`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
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
| `document_type` | Document Type | Link | DocType | ✅ |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `is_custom` | Is Custom | Check | None |  |  | ✅ | 0 | None |
| `permissions_section` | Role Permissions | Section Break | None |  |  |  | None | None |
| `read` | Read | Check | None |  |  |  | 1 | None |
| `write` | Write | Check | None |  |  |  | 0 | None |
| `create` | Create | Check | None |  |  |  | 0 | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `submit` | Submit | Check | None |  |  |  | 0 | None |
| `cancel` | Cancel | Check | None |  |  |  | 0 | None |
| `amend` | Amend | Check | None |  |  |  | 0 | None |
| `delete` | Delete | Check | None |  |  |  | 0 | None |
| `additional_permissions_section` | Additional Permissions | Section Break | None |  |  |  | None | None |
| `email` | Email | Check | None |  |  |  | 1 | None |
| `column_break_fjuk` | None | Column Break | None |  |  |  | None | None |
| `share` | Share | Check | None |  |  |  | 1 | None |
| `print` | Print | Check | None |  |  |  | 1 | None |


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
