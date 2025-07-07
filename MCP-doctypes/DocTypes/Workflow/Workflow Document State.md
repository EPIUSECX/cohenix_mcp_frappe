# Master Control Plan: `Workflow Document State`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Workflow`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Represents the states allowed in one document and role assigned to change the state.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `state` | State | Link | Workflow State | ✅ |  |  | None | None |
| `doc_status` | Doc Status | Select | 0
1
2 |  |  |  | 0 | 0 - Draft; 1 - Submitted; 2 - Cancelled |
| `update_field` | Update Field | Select | None |  |  |  | None | None |
| `update_value` | Update Value | Data | None |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `is_optional_state` | Is Optional State | Check | None |  |  |  | 0 | Workflow Action is not created for optional states |
| `avoid_status_override` | Don't Override Status | Check | None |  |  |  | 0 | If Checked workflow status will not override status in list view |
| `next_action_email_template` | Next Action Email Template | Link | Email Template |  |  |  | None | None |
| `allow_edit` | Only Allow Edit For | Link | Role | ✅ |  |  | None | None |
| `send_email` | Send Email On State | Check | None |  |  |  | 1 | Send email when document transitions to the state. |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `message` | Message | Text | None |  |  |  | None | None |
| `workflow_builder_id` | Workflow Builder ID | Data | None |  | ✅ |  | None | None |


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
