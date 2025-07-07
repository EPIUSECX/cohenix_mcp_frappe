# Master Control Plan: `Subscription Plan`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:plan_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `plan_name` | Plan Name | Data | None | ✅ |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `item` | Item | Link | Item | ✅ |  |  | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `price_determination` | Subscription Price Based On | Select | 
Fixed Rate
Based On Price List
Monthly Rate | ✅ |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `cost` | Cost | Currency | currency |  |  |  | None | None |
| `price_list` | Price List | Link | Price List |  |  |  | None | None |
| `section_break_11` | None | Section Break | None |  |  |  | None | None |
| `billing_interval` | Billing Interval | Select | Day
Week
Month
Year | ✅ |  |  | Day | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `billing_interval_count` | Billing Interval Count | Int | None | ✅ |  |  | 1 | Number of intervals for the interval field e.g if Interval is 'Days' and Billing Interval Count is 3, invoices will be generated every 3 days |
| `payment_plan_section` | Payment Plan | Section Break | None |  |  |  | None | None |
| `product_price_id` | Product Price ID | Data | None |  |  |  | None | None |
| `column_break_16` | None | Column Break | None |  |  |  | None | None |
| `payment_gateway` | Payment Gateway | Link | Payment Gateway Account |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/subscription_plan/subscription_plan.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Subscription Plan", {
	price_determination: function (frm) {
		frm.toggle_reqd("cost", frm.doc.price_determination === "Fixed rate");
		frm.toggle_reqd("price_list", frm.doc.price_determination === "Based on price list");
	},

	subscription_plan: function (frm) {
		erpnext.utils.check_payments_app();
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
