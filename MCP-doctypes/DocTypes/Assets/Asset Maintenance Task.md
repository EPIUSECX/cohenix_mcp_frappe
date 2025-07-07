# Master Control Plan: `Asset Maintenance Task`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Assets`
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
| `maintenance_task` | Maintenance Task | Data | None | ✅ |  |  | None | None |
| `maintenance_type` | Maintenance Type | Select | Preventive Maintenance
Calibration |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `maintenance_status` | Maintenance Status | Select | Planned
Overdue
Cancelled | ✅ |  |  | None | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | Today | None |
| `periodicity` | Periodicity | Select | 
Daily
Weekly
Monthly
Quarterly
Half-yearly
Yearly
2 Yearly
3 Yearly | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `certificate_required` | Certificate Required | Check | None |  |  |  | 0 | None |
| `section_break_9` | None | Section Break | None |  |  |  | None | None |
| `assign_to` | Assign To | Link | User |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `assign_to_name` | Assign to Name | Read Only | None |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `next_due_date` | Next Due Date | Date | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `last_completion_date` | Last Completion Date | Date | None |  |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |


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
