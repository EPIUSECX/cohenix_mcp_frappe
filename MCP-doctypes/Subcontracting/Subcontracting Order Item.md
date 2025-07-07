# Master Control Plan: `Subcontracting Order Item`

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
| `item_code` | Item Code | Link | Item | ✅ |  | ✅ | None | None |
| `item_name` | Item Name | Data | None | ✅ |  |  | None | None |
| `bom` | BOM | Link | BOM | ✅ |  |  | None | None |
| `include_exploded_items` | Include Exploded Items | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `schedule_date` | Required By | Date | None |  |  | ✅ | None | None |
| `expected_delivery_date` | Expected Delivery Date | Date | None |  |  |  | None | None |
| `description_section` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None | ✅ |  |  | None | None |
| `column_break_8` | None | Column Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity_and_rate_section` | Quantity and Rate | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | 1 | None |
| `received_qty` | Received Qty | Float | None |  |  | ✅ | None | None |
| `returned_qty` | Returned Qty | Float | None |  |  | ✅ | None | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `conversion_factor` | Conversion Factor | Float | None |  | ✅ | ✅ | 1 | None |
| `section_break_16` | None | Section Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `amount` | Amount | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `rm_cost_per_qty` | Raw Material Cost Per Qty | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `service_cost_per_qty` | Service Cost Per Qty | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `additional_cost_per_qty` | Additional Cost Per Qty | Currency | Company:company:default_currency |  |  | ✅ | 0 | None |
| `warehouse_section` | Warehouse Details | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse | ✅ |  |  | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `expense_account` | Expense Account | Link | Account |  |  |  | None | None |
| `manufacture_section` | Manufacture | Section Break | None |  |  |  | None | None |
| `manufacturer` | Manufacturer | Link | Manufacturer |  |  |  | None | None |
| `manufacturer_part_no` | Manufacturer Part Number | Data | None |  |  |  | None | None |
| `column_break_impp` | None | Column Break | None |  |  |  | None | None |
| `reference_section` | Reference | Section Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `column_break_fpyl` | None | Column Break | None |  |  |  | None | None |
| `material_request_item` | Material Request Item | Data | None |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `references_section` | References | Section Break | None |  |  |  | None | None |
| `job_card` | Job Card | Link | Job Card |  |  | ✅ | None | None |
| `column_break_nfod` | None | Column Break | None |  |  |  | None | None |
| `section_break_34` | None | Section Break | None |  |  |  | None | None |
| `purchase_order_item` | Purchase Order Item | Data | None |  | ✅ | ✅ | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |
| `subcontracting_conversion_factor` | Subcontracting Conversion Factor | Float | None |  | ✅ | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 10
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
