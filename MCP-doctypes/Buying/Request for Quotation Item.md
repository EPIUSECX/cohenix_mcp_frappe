# Master Control Plan: `Request for Quotation Item`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
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
| `supplier_part_no` | Supplier Part No | Data | None |  | ✅ | ✅ | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  |  | None | None |
| `schedule_date` | Required Date | Date | None | ✅ |  |  | Today | None |
| `section_break_5` | Description | Section Break | None |  |  |  | None | None |
| `description` | Description | Text Editor | None |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `brand` | Brand | Link | Brand |  |  | ✅ | None | None |
| `image_section` | Image | Section Break | None |  |  |  | None | None |
| `image` | Image | Attach | None |  | ✅ |  | None | None |
| `image_view` | Image View | Image | image |  |  |  | None | None |
| `quantity` | Quantity & Stock | Section Break | None |  |  |  | None | None |
| `qty` | Quantity | Float | None | ✅ |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM | ✅ |  | ✅ | None | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `uom` | UOM | Link | UOM | ✅ |  |  | None | None |
| `conversion_factor` | UOM Conversion Factor | Float | None | ✅ |  | ✅ | None | None |
| `stock_qty` | Qty as per Stock UOM | Float | None |  |  | ✅ | None | None |
| `warehouse_and_reference` | Warehouse and Reference | Section Break | None |  |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `material_request` | Material Request | Link | Material Request |  |  | ✅ | None | None |
| `material_request_item` | Material Request Item | Data | None |  | ✅ |  | None | None |
| `section_break_24` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project_name` | Project | Link | Project |  |  |  | None | None |
| `section_break_23` | None | Section Break | None |  |  |  | None | None |
| `page_break` | Page Break | Check | None |  |  |  | 0 | None |


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
