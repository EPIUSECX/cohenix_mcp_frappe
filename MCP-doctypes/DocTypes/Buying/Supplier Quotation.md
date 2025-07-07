# Master Control Plan: `Supplier Quotation`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Manufacturing Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Purchase Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `title` | Title | Data | None |  | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | PUR-SQTN-.YYYY.- | ✅ |  |  | None | None |
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Supplier Name | Data | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Submitted
Stopped
Cancelled
Expired | ✅ |  | ✅ | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `valid_till` | Valid Till | Date | None |  |  |  | None | None |
| `quotation_number` | Quotation Number | Data | None |  |  |  | None | None |
| `has_unit_price_items` | Has Unit Price Items | Check | None |  | ✅ |  | 0 | None |
| `amended_from` | Amended From | Link | Supplier Quotation |  | ✅ | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | None |
| `cb_price_list` | None | Column Break | None |  |  |  | None | None |
| `buying_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency |  |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None |  |  |  | None | None |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Supplier Quotation Item | ✅ |  |  | None | None |
| `section_break_22` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_24` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Purchase Taxes and Charges Template | Link | Purchase Taxes and Charges Template |  |  |  | None | None |
| `column_break_34` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_36` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_38` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Purchase Taxes and Charges | Table | Purchase Taxes and Charges |  |  |  | None | None |
| `totals` | None | Section Break | fa fa-money |  |  |  | None | None |
| `base_taxes_and_charges_added` | Taxes and Charges Added (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_taxes_and_charges_deducted` | Taxes and Charges Deducted (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_37` | None | Column Break | None |  |  |  | None | None |
| `taxes_and_charges_added` | Taxes and Charges Added | Currency | currency |  |  | ✅ | None | None |
| `taxes_and_charges_deducted` | Taxes and Charges Deducted | Currency | currency |  |  | ✅ | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `section_break_41` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_43` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `section_break_46` | Totals | Section Break | None |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `supplier_address_section` | Supplier Address | Section Break | None |  |  |  | None | None |
| `supplier_address` | Supplier Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_72` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  |  | ✅ | None | None |
| `shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `shipping_address` | Shipping Address | Link | Address |  |  |  | None | None |
| `column_break_zjaq` | None | Column Break | None |  |  |  | None | None |
| `shipping_address_display` | Shipping Address Details | Text Editor | None |  |  | ✅ | None | None |
| `company_billing_address_section` | Company Billing Address | Section Break | None |  |  |  | None | None |
| `billing_address` | Company Billing Address | Link | Address |  |  |  | None | None |
| `column_break_gcth` | None | Column Break | None |  |  |  | None | None |
| `billing_address_display` | Billing Address Details | Text Editor | None |  |  | ✅ | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `tc_name` | Terms Template | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `printing_settings` | Printing Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_85` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Data | None |  |  | ✅ | None | None |
| `subscription_section` | Auto Repeat | Section Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `more_info` | Additional Info | Section Break | fa fa-file-text |  |  |  | None | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  |  | 0 | None |
| `column_break_57` | None | Column Break | None |  |  |  | None | None |
| `opportunity` | Opportunity | Link | Opportunity |  |  | ✅ | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 21
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/supplier_quotation/supplier_quotation.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

erpnext.buying.setup_buying_controller();
erpnext.buying.SupplierQuotationController = class SupplierQuotationController extends (
	erpnext.buying.BuyingController
) {
	setup() {
		this.frm.custom_make_buttons = {
			"Purchase Order": "Purchase Order",
			Quotation: "Quotation",
		};

		const me = this;
		this.frm.set_indicator_formatter("item_code", function (doc) {
			return !doc.qty && me.frm.doc.has_unit_price_items ? "yellow" : "";
		});

		super.setup();
	}

	refresh() {
		var me = this;
		super.refresh();

		if (this.frm.doc.__islocal && !this.frm.doc.valid_till) {
			this.frm.set_value("valid_till", frappe.datetime.add_months(this.frm.doc.transaction_date, 1));
		}
		if (this.frm.doc.docstatus === 1) {
			this.frm.add_custom_button(
				__("Purchase Order"),
				this.make_purchase_order.bind(this),
				__("Create")
			);
			this.frm.page.set_inner_btn_group_as_primary(__("Create"));
			this.frm.add_custom_button(__("Quotation"), this.make_quotation.bind(this), __("Create"));
		} else if (this.frm.doc.docstatus === 0) {
			erpnext.set_unit_price_items_note(this.frm);

			this.frm.add_custom_button(
				__("Material Request"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.stock.doctype.material_request.material_request.make_supplier_quotation",
						source_doctype: "Material Request",
						target: me.frm,
						setters: {
							schedule_date: undefined,
							status: undefined,
						},
						get_query_filters: {
							material_request_type: "Purchase",
							docstatus: 1,
							status: ["!=", "Stopped"],
							per_ordered: ["<", 100],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);

			// Link Material Requests
			this.frm.add_custom_button(
				__("Link to Material Requests"),
				function () {
					erpnext.buying.link_to_mrs(me.frm);
				},
				__("Tools")
			);

			this.frm.add_custom_button(
				__("Request for Quotation"),
				function () {
					if (!me.frm.doc.supplier) {
						frappe.throw({ message: __("Please select a Supplier"), title: __("Mandatory") });
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.buying.doctype.request_for_quotation.request_for_quotation.make_supplier_quotation_from_rfq",
						source_doctype: "Request for Quotation",
						target: me.frm,
						setters: {
							transaction_date: null,
						},
						get_query_filters: {
							supplier: me.frm.doc.supplier,
							company: me.frm.doc.company,
						},
						get_query_method:
							"erpnext.buying.doctype.request_for_quotation.request_for_quotation.get_rfq_containing_supplier",
					});
				},
				__("Get Items From")
			);
		}
	}

	make_purchase_order() {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.supplier_quotation.supplier_quotation.make_purchase_order",
			frm: this.frm,
		});
	}
	make_quotation() {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.supplier_quotation.supplier_quotation.make_quotation",
			frm: this.frm,
		});
	}
};

// for backward compatibility: combine new and previous states
extend_cscript(cur_frm.cscript, new erpnext.buying.SupplierQuotationController({ frm: cur_frm }));

cur_frm.fields_dict["items"].grid.get_field("project").get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Project", "status", "not in", "Completed, Cancelled"]],
	};
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Supplier Quotation Comparison` | Script Report | Buying |



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
