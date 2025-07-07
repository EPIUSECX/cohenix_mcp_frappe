# Master Control Plan: `Timesheet Detail`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Projects`
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
| `activity_type` | Activity Type | Link | Activity Type |  |  |  | None | None |
| `from_time` | From Time | Datetime | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `section_break_3` | None | Column Break | None |  |  |  | None | None |
| `expected_hours` | Expected Hrs | Float | None |  |  |  | None | None |
| `to_time` | To Time | Datetime | None |  |  |  | None | None |
| `hours` | Hrs | Float | None |  |  |  | None | None |
| `completed` | Completed | Check | None |  |  |  | 0 | None |
| `project_details` | None | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `project_name` | Project Name | Data | None |  |  | ✅ | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `task` | Task | Link | Task |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `is_billable` | Is Billable | Check | None |  |  |  | 0 | None |
| `sales_invoice` | Sales Invoice | Link | Sales Invoice |  |  | ✅ | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `billing_hours` | Billing Hours | Float | None |  |  |  | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `base_billing_rate` | Billing Rate | Currency | None |  |  | ✅ | None | None |
| `base_billing_amount` | Billing Amount | Currency | None |  |  | ✅ | None | None |
| `base_costing_rate` | Costing Rate | Currency | None |  |  | ✅ | None | None |
| `base_costing_amount` | Costing Amount | Currency | None |  |  | ✅ | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `billing_rate` | Billing Rate | Currency | currency |  |  |  | None | None |
| `billing_amount` | Billing Amount | Currency | currency |  |  | ✅ | 0 | None |
| `costing_rate` | Costing Rate | Currency | currency |  |  |  | None | None |
| `costing_amount` | Costing Amount | Currency | currency |  |  | ✅ | 0 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
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
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Timesheet Activity Breakup` | Timesheet Activity Breakup | Group By | HR |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
