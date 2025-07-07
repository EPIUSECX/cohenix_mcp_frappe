# Master Control Plan: `Maintenance Schedule Detail`

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
| `item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `scheduled_date` | Scheduled Date | Date | None | ✅ |  |  | None | None |
| `actual_date` | Actual Date | Date | None |  |  | ✅ | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `sales_person` | Sales Person | Link | Sales Person |  |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `completion_status` | Completion Status | Select | Pending
Partially Completed
Fully Completed |  |  |  | Pending | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Small Text | None |  |  | ✅ | None | None |
| `item_reference` | Item Reference | Link | Maintenance Schedule Item |  | ✅ | ✅ | None | None |


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
