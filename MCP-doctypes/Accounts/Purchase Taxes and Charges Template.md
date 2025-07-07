# Master Control Plan: `Purchase Taxes and Charges Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Standard tax template that can be applied to all Purchase Transactions. This template can contain a list of tax heads and also other expense heads like "Shipping", "Insurance", "Handling", etc.

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Purchase Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase Master Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `is_default` | Default | Check | None |  |  |  | 0 | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `section_break6` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Purchase Taxes and Charges | Table | Purchase Taxes and Charges |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/purchase_taxes_and_charges_template/purchase_taxes_and_charges_template.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.cscript.tax_table = "Purchase Taxes and Charges";
erpnext.accounts.taxes.setup_tax_validations("Purchase Taxes and Charges Template");
erpnext.accounts.taxes.setup_tax_filters("Purchase Taxes and Charges");

frappe.ui.form.on("Purchase Taxes and Charges", {
	add_deduct_tax(doc, cdt, cdn) {
		let d = locals[cdt][cdn];

		if (!d.category && d.add_deduct_tax) {
			frappe.msgprint(__("Please select Category first"));
			d.add_deduct_tax = "";
		} else if (d.category != "Total" && d.add_deduct_tax == "Deduct") {
			frappe.msgprint(__("Cannot deduct when category is for 'Valuation' or 'Valuation and Total'"));
			d.add_deduct_tax = "";
		}
		refresh_field("add_deduct_tax", d.name, "taxes");
	},

	category(doc, cdt, cdn) {
		let d = locals[cdt][cdn];

		if (d.category != "Total" && d.add_deduct_tax == "Deduct") {
			frappe.msgprint(__("Cannot deduct when category is for 'Valuation' or 'Valuation and Total'"));
			d.add_deduct_tax = "";
		}
		refresh_field("add_deduct_tax", d.name, "taxes");
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
