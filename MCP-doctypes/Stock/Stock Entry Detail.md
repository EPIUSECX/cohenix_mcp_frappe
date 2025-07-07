# Master Control Plan: `Stock Entry Detail`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
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
| `barcode` | Barcode | Data | None |  |  |  | None | None |
| `has_item_scanned` | Has Item Scanned | Check | None |  |  | ✅ | 0 | None |
| `section_break_2` | None | Section Break | None |  |  |  | None | None |
| `s_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `t_warehouse` | Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `sec_break1` | None | Section Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `is_finished_item` | Is Finished Item | Check | None |  |  |  | 0 | None |
| `is_scrap_item` | Is Scrap Item | Check | None |  |  |  | 0 | None |
| `quality_inspection` | Quality Inspection | Link | Quality Inspection |  |  |  | None | None |
| `subcontracted_item` | Subcontracted Item | Link | Item |  |  |  | None | None |
| `section_break_8` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `item_group` | Item Group | Data | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_section` | Quantity | Section Break | None |  |  |  | None | None |
| `qty` | Qty | Float | None | ✅ |  |  | None | None |
| `transfer_qty` | Qty as per Stock UOM | Float | None | ✅ |  | ✅ | None | None |
| `retain_sample` | Retain Sample | Check | None |  |  | ✅ | 0 | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None | ✅ |  |  | None | None |
| `sample_quantity` | Sample Quantity | Int | None |  |  |  | None | None |
| `rates_section` | Rates | Section Break | None |  |  |  | None | None |
| `basic_rate` | Basic Rate (as per Stock UOM) | Currency | Company:company:default_currency |  |  |  | None | None |
| `additional_cost` | Additional Cost | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `landed_cost_voucher_amount` | Landed Cost Voucher Amount | Currency | None |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `allow_zero_valuation_rate` | Allow Zero Valuation Rate | Check | None |  |  |  | 0 | None |
| `col_break3` | None | Column Break | None |  |  |  | None | None |
| `set_basic_rate_manually` | Set Basic Rate Manually | Check | None |  |  |  | 0 | None |
| `basic_amount` | Basic Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `amount` | Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `serial_no_batch` | Serial No / Batch | Section Break | None |  |  |  | None | None |
| `add_serial_batch_bundle` | Add Serial / Batch No | Button | None |  |  |  | None | None |
| `use_serial_batch_fields` | Use Serial No / Batch Fields | Check | None |  |  |  | 0 | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `section_break_rdtg` | None | Section Break | None |  |  |  | None | None |
| `serial_no` | Serial No | Text | None |  |  |  | None | None |
| `column_break_prps` | None | Column Break | None |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `accounting` | Accounting | Section Break | None |  |  |  | None | None |
| `expense_account` | Difference Account | Link | Account |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | :Company | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `more_info` | More Information | Section Break | None |  |  |  | None | None |
| `actual_qty` | Actual Qty (at source/target) | Float | None |  |  | ✅ | None | None |
| `transferred_qty` | Transferred Qty | Float | None |  |  | ✅ | None | None |
| `bom_no` | BOM No | Link | BOM |  | ✅ |  | None | BOM No. for a Finished Good Item |
| `allow_alternative_item` | Allow Alternative Item | Check | None |  |  | ✅ | 0 | None |
| `col_break6` | None | Column Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  | ✅ | ✅ | None | Material Request used to make this Stock Entry |
| `material_request_item` | Material Request Item | Link | Material Request Item |  | ✅ | ✅ | None | None |
| `original_item` | Original Item | Link | Item |  | ✅ | ✅ | None | None |
| `reference_section` | Reference | Section Break | None |  |  |  | None | None |
| `against_stock_entry` | Against Stock Entry | Link | Stock Entry |  |  | ✅ | None | None |
| `ste_detail` | Stock Entry Child | Data | None |  |  | ✅ | None | None |
| `po_detail` | PO Supplied Item | Data | None |  | ✅ | ✅ | None | None |
| `sco_rm_detail` | SCO Supplied Item | Data | None |  | ✅ | ✅ | None | None |
| `putaway_rule` | Putaway Rule | Link | Putaway Rule |  |  | ✅ | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `reference_purchase_receipt` | Reference Purchase Receipt | Link | Purchase Receipt |  |  | ✅ | None | None |
| `job_card_item` | Job Card Item | Data | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 19
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
