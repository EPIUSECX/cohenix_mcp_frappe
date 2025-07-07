# Master Control Plan: `Selling Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Settings for Selling Module

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_defaults_section` | Customer Defaults | Section Break | None |  |  |  | None | None |
| `cust_master_name` | Customer Naming By | Select | Customer Name
Naming Series
Auto Name |  |  |  | Customer Name | None |
| `customer_group` | Default Customer Group | Link | Customer Group |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `territory` | Default Territory | Link | Territory |  |  |  | None | None |
| `item_price_settings_section` | Item Price Settings | Section Break | None |  |  |  | None | None |
| `selling_price_list` | Default Price List | Link | Price List |  |  |  | None | None |
| `maintain_same_rate_action` | Action if Same Rate is Not Maintained Throughout Sales Cycle | Select | Stop
Warn |  |  |  | Stop | None |
| `role_to_override_stop_action` | Role Allowed to Override Stop Action | Link | Role |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `maintain_same_sales_rate` | Maintain Same Rate Throughout Sales Cycle | Check | None |  |  |  | 0 | None |
| `editable_price_list_rate` | Allow User to Edit Price List Rate in Transactions | Check | None |  |  |  | 0 | None |
| `validate_selling_price` | Validate Selling Price for Item Against Purchase Rate or Valuation Rate | Check | None |  |  |  | 0 | None |
| `editable_bundle_item_rates` | Calculate Product Bundle Price based on Child Items' Rates | Check | None |  |  |  | 0 | None |
| `allow_negative_rates_for_items` | Allow Negative rates for Items | Check | None |  |  |  | 0 | None |
| `sales_transactions_settings_section` | Transaction Settings | Section Break | None |  |  |  | None | None |
| `so_required` | Is Sales Order Required for Sales Invoice & Delivery Note Creation? | Select | No
Yes |  |  |  | None | None |
| `dn_required` | Is Delivery Note Required for Sales Invoice Creation? | Select | No
Yes |  |  |  | None | None |
| `sales_update_frequency` | Sales Update Frequency in Company and Project | Select | Monthly
Each Transaction
Daily | ✅ |  |  | Each Transaction | How often should Project and Company be updated based on Sales Transactions? |
| `blanket_order_allowance` | Blanket Order Allowance (%) | Float | None |  |  |  | None | Percentage you are allowed to sell beyond the Blanket Order quantity. |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `allow_multiple_items` | Allow Item to be Added Multiple Times in a Transaction | Check | None |  |  |  | 0 | None |
| `allow_against_multiple_purchase_orders` | Allow Multiple Sales Orders Against a Customer's Purchase Order | Check | None |  |  |  | 0 | None |
| `allow_sales_order_creation_for_expired_quotation` | Allow Sales Order Creation For Expired Quotation | Check | None |  |  |  | 0 | None |
| `dont_reserve_sales_order_qty_on_sales_return` | Don't Reserve Sales Order Qty on Sales Return | Check | None |  |  |  | 0 | None |
| `hide_tax_id` | Hide Customer's Tax ID from Sales Transactions | Check | None |  |  |  | 0 | None |
| `enable_discount_accounting` | Enable Discount Accounting for Selling | Check | None |  |  |  | 0 | If enabled, additional ledger entries will be made for discounts in a separate Discount Account |
| `enable_cutoff_date_on_bulk_delivery_note_creation` | Enable Cut-Off Date on Bulk Delivery Note Creation | Check | None |  |  |  | 0 | None |
| `allow_zero_qty_in_quotation` | Allow Quotation with Zero Quantity | Check | None |  |  |  | 0 | Allows users to submit Quotations with zero quantity. Useful when rates are fixed but the quantities are not. Eg. Rate Contracts. |
| `allow_zero_qty_in_sales_order` | Allow Sales Order with Zero Quantity | Check | None |  |  |  | 0 | Allows users to submit Sales Orders with zero quantity. Useful when rates are fixed but the quantities are not. Eg. Rate Contracts. |
| `experimental_section` | Experimental | Section Break | None |  |  |  | None | None |
| `use_server_side_reactivity` | Use Server Side Reactivity | Check | None |  |  |  | 1 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/selling_settings/selling_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Selling Settings", {
	after_save(frm) {
		frappe.boot.user.defaults.editable_price_list_rate = frm.doc.editable_price_list_rate;
	},
});

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
