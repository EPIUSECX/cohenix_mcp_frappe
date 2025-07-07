# Master Control Plan: `Stock Ledger Entry`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `MAT-SLE-.YYYY.-.#####`
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
| `posting_date` | Posting Date | Date | None |  |  | ✅ | None | None |
| `posting_time` | Posting Time | Time | None |  |  | ✅ | None | None |
| `posting_datetime` | Posting Datetime | Datetime | None |  |  |  | None | None |
| `is_adjustment_entry` | Is Adjustment Entry | Check | None |  |  |  | 0 | None |
| `auto_created_serial_and_batch_bundle` | Auto Created Serial and Batch Bundle | Check | None |  |  |  | 0 | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `voucher_type` | Voucher Type | Link | DocType |  |  | ✅ | None | None |
| `voucher_no` | Voucher No | Dynamic Link | voucher_type |  |  | ✅ | None | None |
| `voucher_detail_no` | Voucher Detail No | Data | None |  |  | ✅ | None | None |
| `serial_and_batch_bundle` | Serial and Batch Bundle | Link | Serial and Batch Bundle |  |  |  | None | None |
| `dependant_sle_voucher_detail_no` | Dependant SLE Voucher Detail No | Data | None |  |  |  | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `recalculate_rate` | Recalculate Incoming/Outgoing Rate | Check | None |  |  | ✅ | 0 | None |
| `actual_qty` | Qty Change | Float | None |  |  | ✅ | None | None |
| `qty_after_transaction` | Qty After Transaction | Float | None |  |  | ✅ | None | None |
| `incoming_rate` | Incoming Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `outgoing_rate` | Outgoing Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `valuation_rate` | Valuation Rate | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `stock_value` | Balance Stock Value | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `stock_value_difference` | Change in Stock Value | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `stock_queue` | FIFO Stock Queue (qty, rate) | Long Text | None |  |  | ✅ | None | None |
| `section_break_21` | None | Section Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  | ✅ | None | None |
| `stock_uom` | Stock UOM | Link | UOM |  |  | ✅ | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `fiscal_year` | Fiscal Year | Data | None |  |  | ✅ | None | None |
| `has_batch_no` | Has Batch No | Check | None |  |  |  | 0 | None |
| `has_serial_no` | Has Serial No | Check | None |  |  |  | 0 | None |
| `is_cancelled` | Is Cancelled | Check | None |  |  |  | 0 | None |
| `to_rename` | To Rename | Check | None |  | ✅ |  | 1 | None |
| `serial_no` | Serial No | Long Text | None |  |  | ✅ | None | None |
| `batch_no` | Batch No | Data | None |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 7
- **Dynamic Link Fields:** 1
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_ledger_entry/stock_ledger_entry.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Stock Ledger Entry", {
	refresh: function (frm) {
		frm.page.btn_secondary.hide();
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Available Serial No` | Script Report | Stock |
| `Available Batch Report` | Script Report | Stock |
| `Stock Ledger Variance` | Script Report | Stock |
| `Warehouse Wise Stock Balance` | Script Report | Stock |
| `FIFO Queue vs Qty After Transaction Comparison` | Script Report | Stock |
| `Stock Ledger Invariant Check` | Script Report | Stock |
| `Incorrect Stock Value Report` | Script Report | Stock |
| `Incorrect Serial No Valuation` | Script Report | Stock |
| `Incorrect Balance Qty After Transaction` | Script Report | Stock |
| `Serial No Ledger` | Script Report | Stock |
| `Stock and Account Value Comparison` | Script Report | Stock |
| `Product Bundle Balance` | Script Report | Stock |
| `Warehouse wise Item Balance Age and Value` | Script Report | Stock |
| `Batch Item Expiry Status` | Script Report | Stock |
| `Stock Balance` | Script Report | Stock |
| `Stock Ledger` | Script Report | Stock |
| `Supplier-Wise Sales Analytics` | Script Report | Stock |
| `Item Prices` | Script Report | Stock |
| `Batch-Wise Balance History` | Script Report | Stock |



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
