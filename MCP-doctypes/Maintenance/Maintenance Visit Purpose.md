# Master Control Plan: `Maintenance Visit Purpose`

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
| `item_code` | Item Code | Link | Item |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `service_person` | Sales Person | Link | Sales Person | ✅ |  |  | None | None |
| `serial_no` | Serial No | Link | Serial No |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `work_details` | None | Section Break | None |  |  |  | None | None |
| `work_done` | Work Done | Small Text | None | ✅ |  |  | None | None |
| `prevdoc_doctype` | Document Type | Link | DocType |  | ✅ |  | None | None |
| `prevdoc_docname` | Against Document No | Dynamic Link | prevdoc_doctype |  | ✅ |  | None | None |
| `maintenance_schedule_detail` | Maintenance Schedule Detail | Data | Maintenance Schedule Detail |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 1
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
