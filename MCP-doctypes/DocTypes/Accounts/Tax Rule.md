# Master Control Plan: `Tax Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `ACC-TAX-RULE-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `tax_type` | Tax Type | Select | Sales
Purchase |  |  |  | Sales | None |
| `use_for_shopping_cart` | Use for Shopping Cart | Check | None |  |  |  | 1 | None |
| `column_break_1` | None | Column Break | None |  |  |  | None | None |
| `sales_tax_template` | Sales Tax Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `purchase_tax_template` | Purchase Tax Template | Link | Purchase Taxes and Charges Template |  |  |  | None | None |
| `filters` | Filters | Section Break | None |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `item` | Item | Link | Item |  |  |  | None | None |
| `billing_city` | Billing City | Data | None |  |  |  | None | None |
| `billing_county` | Billing County | Data | None |  |  |  | None | None |
| `billing_state` | Billing State | Data | None |  |  |  | None | None |
| `billing_zipcode` | Billing Zipcode | Data | None |  |  |  | None | None |
| `billing_country` | Billing Country | Link | Country |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `column_break_2` | None | Column Break | None |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `supplier_group` | Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `shipping_city` | Shipping City | Data | None |  |  |  | None | None |
| `shipping_county` | Shipping County | Data | None |  |  |  | None | None |
| `shipping_state` | Shipping State | Data | None |  |  |  | None | None |
| `shipping_zipcode` | Shipping Zipcode | Data | None |  |  |  | None | None |
| `shipping_country` | Shipping Country | Link | Country |  |  |  | None | None |
| `section_break_4` | Validity | Section Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `priority` | Priority | Int | None |  |  |  | 1 | None |
| `column_break_20` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 12
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/tax_rule/tax_rule.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Tax Rule", "customer", function (frm) {
	if (frm.doc.customer) {
		frappe.call({
			method: "erpnext.accounts.doctype.tax_rule.tax_rule.get_party_details",
			args: {
				party: frm.doc.customer,
				party_type: "customer",
			},
			callback: function (r) {
				if (!r.exc) {
					$.each(r.message, function (k, v) {
						frm.set_value(k, v);
					});
				}
			},
		});
	}
});

frappe.ui.form.on("Tax Rule", "supplier", function (frm) {
	if (frm.doc.supplier) {
		frappe.call({
			method: "erpnext.accounts.doctype.tax_rule.tax_rule.get_party_details",
			args: {
				party: frm.doc.supplier,
				party_type: "supplier",
			},
			callback: function (r) {
				if (!r.exc) {
					$.each(r.message, function (k, v) {
						frm.set_value(k, v);
					});
				}
			},
		});
	}
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
