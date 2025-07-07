# Master Control Plan: `Employee Boarding Activity`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `HR`
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
| `activity_name` | Activity Name | Data | None | ✅ |  |  | None | None |
| `user` | User | Link | User |  |  |  | None | None |
| `role` | Role | Link | Role |  |  |  | None | None |
| `begin_on` | Begin On (Days) | Int | None |  |  |  | None | None |
| `duration` | Duration (Days) | Int | None |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `task` | Task | Link | Task |  |  | ✅ | None | None |
| `task_weight` | Task Weight | Float | None |  |  |  | None | None |
| `required_for_employee_creation` | Required for Employee Creation | Check | None |  |  |  | 0 | Applicable in the case of Employee Onboarding |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |


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
