# Master Control Plan: `Subcontracting Receipt Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Subcontracting`
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
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `is_scrap_item` | Is Scrap Item | Check | None |  |  |  | 0 | None |
| `section_break_4` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `brand` | Brand | Link | Brand |  | ✅ | ✅ | None | None |
| `image_column` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `received_and_accepted` | Received and Accepted | Section Break | None |  |  |  | None | None |
| `received_qty` | Received Quantity | Float | None | ✅ |  | ✅ | 0 | None |
| `qty` | Accepted Quantity | Float | None |  |  |  | None | None |
| `rejected_qty` | Rejected Quantity | Float | None |  |  |  | None | None |
| `returned_qty` | Returned Qty | Float | None |  |  | ✅ | 0 | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  | ✅ | ✅ | 1 | None |
| `rate_and_amount` | Rate and Amount | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `landed_cost_voucher_amount` | Landed Cost Voucher Amount | Currency | None |  |  | ✅ | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `rm_cost_per_qty` | Raw Material Cost Per Qty | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `service_cost_per_qty` | Service Cost Per Qty | Currency | Company:company:default_currency | ✅ |  | ✅ | 0 | None |
| `additional_cost_per_qty` | Additional Cost Per Qty | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `scrap_cost_per_qty` | Scrap Cost Per Qty | Float | None |  |  | ✅ | 0 | None |
| `rm_supp_cost` | Raw Materials Supplied Cost | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Accepted Warehouse | Link | Warehouse |  |  |  | None | None |
| `subcontracting_order` | Subcontracting Order | Link | Subcontracting Order |  |  | ✅ | None | None |
| `subcontracting_order_item` | Subcontracting Order Item | Data | None |  | ✅ | ✅ | None | None |
| `subcontracting_receipt_item` | Subcontracting Receipt Item | Data | None |  | ✅ | ✅ | None | None |
| `job_card` | Job Card | Link | Job Card |  |  | ✅ | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | None |
| `bom` | BOM | Link | BOM |  |  |  | None | None |
| `include_exploded_items` | Include Exploded Items | Check | None |  |  |  | 0 | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `schedule_date` | Required By | Date | None |  |  | ✅ | None | None |
| `reference_name` | Reference Name | Data | None |  | ✅ | ✅ | None | None |
| `section_break_45` | Serial and Batch Details | Section Break | None |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch Bundle | Button | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_break5` | None | Column Break | None |  |  |  | None | None |
| `add_serial_batch_for_rejected_qty` | Add Serial / Batch No (Rejected Qty) | Button | None |  |  |  | None | None |
| `rejected_serial_and_batch_bundle` | Rejected Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `section_break_jshh` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Small Text | None |  |  |  | None | None |
| `rejected_serial_no` | Rejected Serial No | Small Text | None |  |  |  | None | None |
| `column_break_henr` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `manufacture_details` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `section_break_80` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |
| `purchase_order` | Purchase Order | Link | Purchase Order |  | ✅ | ✅ | None | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 17
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
