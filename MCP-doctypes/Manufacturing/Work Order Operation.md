# Master Control Plan: `Work Order Operation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Manufacturing`
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
| `details` | None | Section Break | None |  |  |  | None | None |
| `operation` | Operation | Link | Operation | ✅ |  |  | None | None |
| `status` | Status | Select | Pending
Work in Progress
Completed |  |  |  | Pending | None |
| `completed_qty` | Completed Qty | Float | None |  |  |  | None | Operation completed for how many finished goods? |
| `process_loss_qty` | Process Loss Qty | Float | None |  |  | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `bom` | BOM | Link | BOM |  |  |  | None | None |
| `workstation_type` | Workstation Type | Link | Workstation Type |  |  |  | None | None |
| `workstation` | Workstation | Link | Workstation |  |  |  | None | None |
| `sequence_id` | Sequence ID | Int | None |  |  |  | None | None |
| `section_break_insy` | None | Section Break | None |  |  |  | None | None |
| `bom_no` | BOM No (For Semi-Finished Goods) | Link | BOM |  |  | ✅ | None | None |
| `finished_good` | Semi Finished Goods / Finished Goods | Link | Item |  |  | ✅ | None | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  | ✅ | 0 | None |
| `skip_material_transfer` | Skip Material Transfer | Check | None |  |  | ✅ | 0 | None |
| `backflush_from_wip_warehouse` | Backflush Materials From WIP Warehouse | Check | None |  |  | ✅ | 0 | None |
| `column_break_vjih` | None | Column Break | None |  |  |  | None | None |
| `source_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `wip_warehouse` | WIP WH | Link | Warehouse |  |  |  | None | None |
| `fg_warehouse` | Finished Goods Warehouse | Link | Warehouse |  |  |  | None | None |
| `section_break_10` | None | Section Break | None |  |  |  | None | None |
| `description` | Operation Description | Text Editor | None |  |  |  | None | None |
| `estimated_time_and_cost` | Estimated Time and Cost | Section Break | None |  |  |  | None | None |
| `planned_start_time` | Planned Start Time | Datetime | None |  |  | ✅ | None | None |
| `hour_rate` | Hour Rate | Float | None |  |  | ✅ | None | None |
| `time_in_mins` | Time | Float | None | ✅ |  |  | None | In Minutes |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `planned_end_time` | Planned End Time | Datetime | None |  |  | ✅ | None | None |
| `batch_size` | Batch Size | Float | None |  |  | ✅ | None | None |
| `planned_operating_cost` | Planned Operating Cost | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `section_break_9` | Actual Time and Cost | Section Break | None |  |  |  | None | None |
| `actual_start_time` | Actual Start Time | Datetime | None |  |  | ✅ | None | Updated via 'Time Log' (In Minutes) |
| `actual_operation_time` | Actual Operation Time | Float | None |  |  | ✅ | None | Updated via 'Time Log' (In Minutes) |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `actual_end_time` | Actual End Time | Datetime | None |  |  | ✅ | None | Updated via 'Time Log' (In Minutes) |
| `actual_operating_cost` | Actual Operating Cost | Currency | Company:company:default_currency |  |  | ✅ | None | (Hour Rate / 60) * Actual Operation Time |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
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
| `Completed Operation` | Completed Operation | Sum | Manufacturing |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
