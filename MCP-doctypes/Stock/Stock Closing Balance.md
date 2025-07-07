# Master Control Plan: `Stock Closing Balance`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `item_code` | Item Code | Link | Item |  |  | ✅ | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  | ✅ | None | None |
| `batch_no` | Batch No | Link | Batch |  |  | ✅ | None | None |
| `column_break_rvdz` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Posting Date | Date | None |  |  | ✅ | None | None |
| `posting_time` | Posting Time | Time | None |  |  | ✅ | None | None |
| `posting_datetime` | Posting Datetime | Datetime | None |  |  | ✅ | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `actual_qty` | Qty Change | Float | None |  |  | ✅ | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `stock_value` | Balance Stock Value | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `stock_value_difference` | Change in Stock Value | Currency | None |  |  | ✅ | None | None |
| `section_break_21` | None | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `column_break_usgq` | None | Column Break | None |  |  |  | None | None |
| `stock_closing_entry` | Stock Closing Entry | Link | Stock Closing Entry |  |  | ✅ | None | None |
| `section_break_fxjm` | None | Section Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `item_group` | Item Group | Link | Item Group |  |  | ✅ | None | None |
| `column_break_ljle` | None | Column Break | None |  |  |  | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `inventory_dimension_key` | Inventory Dimension key | Small Text | None |  |  | ✅ | None | None |
| `stock_ageing_section` | Stock Ageing | Section Break | None |  |  |  | None | None |
| `fifo_queue` | FIFO Queue | Long Text | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_closing_balance/stock_closing_balance.js`
```javascript
// Copyright (c) 2024, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

// frappe.ui.form.on("Stock Closing Balance", {
// 	refresh(frm) {

// 	},
// });

```




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
