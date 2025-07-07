# Master Control Plan: `Maintenance Schedule Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Maintenance`
- **Custom:** `0`
- **Is Table:** `1`
- **Is Submittable:** `0`
- **Autoname:** `hash`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `description` | Description | Text Editor | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None | ✅ |  |  | None | None |
| `end_date` | End Date | Date | None | ✅ |  |  | None | None |
| `periodicity` | Periodicity | Select | 
Weekly
Monthly
Quarterly
Half Yearly
Yearly
Random |  |  |  | None | None |
| `schedule_details` | None | Section Break | None |  |  |  | None | None |
| `no_of_visits` | No of Visits | Int | None | ✅ |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `sales_person` | Sales Person | Link | Sales Person |  |  |  | None | None |
| `reference` | Reference | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Small Text | None |  |  | ✅ | None | None |
| `sales_order` | Sales Order | Link | Sales Order |  |  | ✅ | None | None |
| `column_break_ugqr` | None | Column Break | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |


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
