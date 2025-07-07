# Master Control Plan: `Communication Medium`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Communication`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `communication_channel` | Communication Channel | Select | None |  |  |  | None | None |
| `communication_medium_type` | Communication Medium Type | Select | Voice
Email
Chat | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `catch_all` | Catch All | Link | Employee Group |  |  |  | None | If there is no assigned timeslot, then communication will be handled by this group |
| `provider` | Provider | Link | Supplier |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `timeslots_section` | Timeslots | Section Break | None |  |  |  | None | None |
| `timeslots` | Timeslots | Table | Communication Medium Timeslot |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

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
