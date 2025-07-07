# Master Control Plan: `BOM Operation`

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
| `operation` | Operation | Link | Operation | ✅ |  |  | None | None |
| `sequence_id` | Sequence ID | Int | None |  |  |  | None | None |
| `finished_good` | Finished Goods / Semi Finished Goods Item | Link | Item |  |  |  | None | None |
| `finished_good_qty` | Finished Goods Qty | Float | None |  |  |  | 1 | None |
| `bom_no` | BOM No | Link | BOM |  |  |  | None | None |
| `add_raw_materials` | Add Raw Materials | Button | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `workstation_type` | Workstation Type | Link | Workstation Type |  |  |  | None | None |
| `workstation` | Workstation | Link | Workstation |  |  |  | None | None |
| `time_in_mins` | Operation Time | Float | None | ✅ |  |  | None | In minutes |
| `fixed_time` | Fixed Time | Check | None |  |  |  | 0 | Operation time does not depend on quantity to produce |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  |  | 0 | None |
| `is_final_finished_good` | Is Final Finished Good | Check | None |  |  |  | 0 | None |
| `set_cost_based_on_bom_qty` | Set Operating Cost Based On BOM Quantity | Check | None |  |  |  | 0 | None |
| `warehouse_section` | Warehouse | Section Break | None |  |  |  | None | None |
| `skip_material_transfer` |  Skip Material Transfer | Check | None |  |  |  | 0 | None |
| `backflush_from_wip_warehouse` | Backflush Materials From WIP Warehouse | Check | None |  |  |  | 0 | None |
| `source_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `column_break_lbhy` | None | Column Break | None |  |  |  | None | None |
| `wip_warehouse` | WIP Warehouse | Link | Warehouse |  |  |  | None | None |
| `fg_warehouse` | Finished Goods Warehouse | Link | Warehouse |  |  |  | None | None |
| `costing_section` | Costing | Section Break | None |  |  |  | None | None |
| `hour_rate` | Hour Rate | Currency | currency |  |  |  | None | None |
| `base_hour_rate` | Base Hour Rate(Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `batch_size` | Batch Size | Int | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `cost_per_unit` | Cost Per Unit | Float | None |  |  | ✅ | None | None |
| `base_cost_per_unit` | Base Cost Per Unit | Float | None |  | ✅ | ✅ | None | None |
| `operating_cost` | Operating Cost | Currency | currency |  |  | ✅ | None | None |
| `base_operating_cost` | Operating Cost(Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `more_information_section` | More Information | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 8
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
