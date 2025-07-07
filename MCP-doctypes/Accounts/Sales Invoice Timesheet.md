# Master Control Plan: `Sales Invoice Timesheet`

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
| `activity_type` | Activity Type | Link | Activity Type |  |  | ✅ | None | None |
| `description` | Description | Small Text | None |  |  | ✅ | None | None |
| `section_break_3` | Time | Section Break | None |  |  |  | None | None |
| `from_time` | From Time | Datetime | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `to_time` | To Time | Datetime | None |  |  |  | None | None |
| `section_break_7` | Totals | Section Break | None |  |  |  | None | None |
| `billing_hours` | Billing Hours | Float | None |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `billing_amount` | Billing Amount | Currency | currency |  |  | ✅ | None | None |
| `section_break_11` | Reference | Section Break | None |  |  |  | None | None |
| `time_sheet` | Time Sheet | Link | Timesheet |  |  | ✅ | None | None |
| `timesheet_detail` | Timesheet Detail | Data | None |  | ✅ | ✅ | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `project_name` | Project Name | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
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
