# Master Control Plan: `Payment Term`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:payment_term_name`
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
| `payment_term_name` | Payment Term Name | Data | None |  |  |  | None | None |
| `invoice_portion` | Invoice Portion (%) | Float | None |  |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `due_date_based_on` | Due Date Based On | Select | Day(s) after invoice date
Day(s) after the end of the invoice month
Month(s) after the end of the invoice month |  |  |  | None | None |
| `credit_days` | Credit Days | Int | None |  |  |  | None | None |
| `credit_months` | Credit Months | Int | None |  |  |  | None | None |
| `section_break_8` | Discount Settings | Section Break | None |  |  |  | None | None |
| `discount_type` | Discount Type | Select | Percentage
Amount |  |  |  | Percentage | None |
| `discount` | Discount | Float | None |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `discount_validity_based_on` | Discount Validity Based On | Select | Day(s) after invoice date
Day(s) after the end of the invoice month
Month(s) after the end of the invoice month |  |  |  | Day(s) after invoice date | None |
| `discount_validity` | Discount Validity | Int | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_term/payment_term.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt
frappe.ui.form.on("Payment Term", {
	onload(frm) {
		frm.trigger("set_dynamic_description");
	},
	discount(frm) {
		frm.trigger("set_dynamic_description");
	},
	discount_type(frm) {
		frm.trigger("set_dynamic_description");
	},
	set_dynamic_description(frm) {
		if (frm.doc.discount) {
			let description = __("{0}% of total invoice value will be given as discount.", [
				frm.doc.discount,
			]);
			if (frm.doc.discount_type == "Amount") {
				description = __("{0} will be given as discount.", [frm.doc.discount]);
			}
			frm.set_df_property("discount", "description", description);
		}
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
