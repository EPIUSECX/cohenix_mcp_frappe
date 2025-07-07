# Master Control Plan: `Promotional Scheme`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_1` | None | Section Break | None |  |  |  | None | None |
| `apply_on` | Apply On | Select | 
Item Code
Item Group
Brand
Transaction | ✅ |  |  | Item Code | None |
| `disable` | Disable | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `items` | Pricing Rule Item Code | Table | Pricing Rule Item Code |  |  |  | None | None |
| `item_groups` | Pricing Rule Item Group | Table | Pricing Rule Item Group |  |  |  | None | None |
| `brands` | Pricing Rule Brand | Table | Pricing Rule Brand |  |  |  | None | None |
| `mixed_conditions` | Mixed Conditions | Check | None |  |  |  | 0 | None |
| `is_cumulative` | Is Cumulative | Check | None |  |  |  | 0 | None |
| `section_break_10` | Discount on Other Item | Section Break | None |  |  |  | None | None |
| `apply_rule_on_other` | Apply Rule On Other | Select | 
Item Code
Item Group
Brand |  |  |  | None | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `other_item_code` | Item Code | Link | Item |  |  |  | None | None |
| `other_item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `other_brand` | Brand | Link | Brand |  |  |  | None | None |
| `section_break_8` | Party Information | Section Break | None |  |  |  | None | None |
| `selling` | Selling | Check | None |  |  |  | 0 | None |
| `buying` | Buying | Check | None |  |  |  | 0 | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `applicable_for` | Applicable For | Select | 
Customer
Customer Group
Territory
Sales Partner
Campaign
Supplier
Supplier Group |  |  |  | None | None |
| `customer` | Customer | Table MultiSelect | Customer Item |  |  |  | None | None |
| `customer_group` | Customer Group | Table MultiSelect | Customer Group Item |  |  |  | None | None |
| `territory` | Territory | Table MultiSelect | Territory Item |  |  |  | None | None |
| `sales_partner` | Sales Partner | Table MultiSelect | Sales Partner Item |  |  |  | None | None |
| `campaign` | Campaign | Table MultiSelect | Campaign Item |  |  |  | None | None |
| `supplier` | Supplier | Table MultiSelect | Supplier Item |  |  |  | None | None |
| `supplier_group` | Supplier Group | Table MultiSelect | Supplier Group Item |  |  |  | None | None |
| `period_settings_section` | Period Settings | Section Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None |  |  |  | Today | None |
| `valid_upto` | Valid Up To | Date | None |  |  |  | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `section_break_14` | Price Discount Slabs | Section Break | None |  |  |  | None | None |
| `price_discount_slabs` | Promotional Scheme Price Discount | Table | Promotional Scheme Price Discount |  |  |  | None | None |
| `section_break_15` | Product Discount Slabs | Section Break | None |  |  |  | None | None |
| `product_discount_slabs` | Promotional Scheme Product Discount | Table | Promotional Scheme Product Discount |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 5
- **Dynamic Link Fields:** 0
- **Table Fields:** 12

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/promotional_scheme/promotional_scheme.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Promotional Scheme", {
	setup: function (frm) {
		frm.set_query("for_price_list", "price_discount_slabs", (doc) => {
			return {
				filters: {
					selling: doc.selling,
					buying: doc.buying,
					currency: doc.currency,
				},
			};
		});
	},

	refresh: function (frm) {
		frm.trigger("set_options_for_applicable_for");
		frm.trigger("toggle_reqd_apply_on");
	},

	selling: function (frm) {
		frm.trigger("set_options_for_applicable_for");
	},

	buying: function (frm) {
		frm.trigger("set_options_for_applicable_for");
	},

	set_options_for_applicable_for: function (frm) {
		var options = [""];
		var applicable_for = frm.doc.applicable_for;

		if (frm.doc.selling) {
			options = $.merge(options, [
				"Customer",
				"Customer Group",
				"Territory",
				"Sales Partner",
				"Campaign",
			]);
		}
		if (frm.doc.buying) {
			$.merge(options, ["Supplier", "Supplier Group"]);
		}

		set_field_options("applicable_for", options.join("\n"));

		if (!in_list(options, applicable_for)) applicable_for = null;
		frm.set_value("applicable_for", applicable_for);
	},

	apply_on: function (frm) {
		frm.trigger("toggle_reqd_apply_on");
	},

	toggle_reqd_apply_on: function (frm) {
		const fields = {
			"Item Code": "items",
			"Item Group": "item_groups",
			Brand: "brands",
		};

		for (var key in fields) {
			frm.toggle_reqd(fields[key], frm.doc.apply_on === key ? 1 : 0);
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
