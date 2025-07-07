# Master Control Plan: `Notification Recipient`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Email`
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
| `receiver_by_document_field` | Receiver By Document Field | Select | None |  |  |  | None | None |
| `receiver_by_role` | Receiver By Role | Link | Role |  |  |  | None | None |
| `cc` | CC | Code | None |  |  |  | None | Optional: Always send to these ids. Each Email Address on a new row |
| `bcc` | BCC | Code | None |  |  |  | None | None |
| `condition` | Condition | Data | None |  |  |  | None | Expression, Optional |


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
