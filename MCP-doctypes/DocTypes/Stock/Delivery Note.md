# Master Control Plan: `Delivery Note`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Delivery User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Delivery Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | MAT-DN-.YYYY.-
MAT-DN-RET-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `tax_id` | Tax Id | Data | None |  |  | ✅ | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None | ✅ |  |  | None | None |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `amended_from` | Amended From | Link | Delivery Note |  |  | ✅ | None | None |
| `is_return` | Is Return | Check | None |  |  | ✅ | 0 | None |
| `issue_credit_note` | Issue Credit Note | Check | None |  |  |  | 0 | None |
| `return_against` | Return Against Delivery Note | Link | Delivery Note |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which customer's currency is converted to company's base currency |
| `col_break23` | None | Column Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Price list currency is converted to company's base currency |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `items_section` | Items | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `col_break_warehouse` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Set Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `set_target_warehouse` | Set Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `section_break_30` | None | Section Break | None |  |  |  | None | None |
| `items` | Delivery Note Item | Table | Delivery Note Item | ✅ |  |  | None | None |
| `section_break_31` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_35` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Sales Taxes and Charges Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `column_break_43` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_39` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_41` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Sales Taxes and Charges | Table | Sales Taxes and Charges |  |  |  | None | None |
| `section_break_44` | None | Section Break | None |  |  |  | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_47` | None | Column Break | None |  |  |  | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `totals` | Totals | Section Break | fa fa-money |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | In Words will be visible once you save the Delivery Note. |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | In Words (Export) will be visible once you save the Delivery Note. |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `section_break_49` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `packing_list` | Packing List | Section Break | fa fa-suitcase |  |  |  | None | None |
| `packed_items` | Packed Items | Table | Packed Item |  |  |  | None | None |
| `product_bundle_help` | Product Bundle Help | HTML | None |  |  |  | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `contact_info` | Billing Address | Section Break | fa fa-bullhorn |  |  |  | None | None |
| `customer_address` | Billing Address Name | Link | Address |  |  |  | None | None |
| `address_display` | Billing Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break21` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  | ✅ | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `shipping_address_name` | Shipping Address | Link | Address |  |  |  | None | None |
| `shipping_address` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_95` | None | Column Break | None |  |  |  | None | None |
| `dispatch_address_name` | Dispatch Address Name | Link | Address |  |  |  | None | None |
| `dispatch_address` | Dispatch Address | Text Editor | None |  |  | ✅ | None | None |
| `company_address_section` | Company Address | Section Break | None |  |  |  | None | None |
| `company_address` | Company Address Name | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_101` | None | Column Break | None |  |  |  | None | None |
| `company_contact_person` | Company Contact Person | Link | Contact |  |  |  | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions Details | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `section_break_83` | Status | Section Break | None |  |  |  | None | None |
| `per_billed` | % Amount Billed | Percent | None |  |  | ✅ | None | None |
| `status` | Status | Select | 
Draft
To Bill
Completed
Return Issued
Cancelled
Closed | ✅ |  | ✅ | Draft | None |
| `column_break_112` | None | Column Break | None |  |  |  | None | None |
| `per_installed` | % Installed | Percent | None |  |  | ✅ | None | None |
| `installation_status` | Installation Status | Select | None |  | ✅ |  | None | None |
| `column_break_89` | None | Column Break | None |  |  |  | None | None |
| `per_returned` | % Returned | Percent | None |  |  | ✅ | None | None |
| `transporter_info` | Transporter Info | Section Break | fa fa-truck |  |  |  | None | None |
| `transporter` | Transporter | Link | Supplier |  |  |  | None | None |
| `lr_no` | Transport Receipt No | Data | None |  |  |  | None | None |
| `delivery_trip` | Delivery Trip | Link | Delivery Trip |  |  |  | None | None |
| `driver` | Driver | Link | Driver |  |  |  | None | None |
| `col_break34` | None | Column Break | None |  |  |  | None | None |
| `transporter_name` | Transporter Name | Data | None |  |  | ✅ | None | None |
| `lr_date` | Transport Receipt Date | Date | None |  |  |  | Today | None |
| `vehicle_no` | Vehicle No | Data | None |  |  |  | None | None |
| `driver_name` | Driver Name | Data | None |  |  |  | None | None |
| `customer_po_details` | Customer PO Details | Section Break | None |  |  |  | None | None |
| `po_no` | Customer's Purchase Order No | Small Text | None |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `po_date` | Customer's Purchase Order Date | Date | None |  |  |  | None | None |
| `sales_team_section_break` | Commission | Section Break | fa fa-group |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `amount_eligible_for_commission` | Amount Eligible for Commission | Currency | None |  |  | ✅ | None | None |
| `column_break7` | None | Column Break | None |  |  |  | None | None |
| `commission_rate` | Commission Rate (%) | Float | None |  |  |  | None | None |
| `total_commission` | Total Commission | Currency | Company:company:default_currency |  |  |  | None | None |
| `section_break1` | Sales Team | Section Break | None |  |  |  | None | None |
| `sales_team` | Sales Team | Table | Sales Team |  |  |  | None | None |
| `subscription_section` | Subscription Section | Section Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `printing_details` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `print_without_amount` | Print Without Amount | Check | None |  |  |  | 0 | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_88` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  | ✅ | None | None |
| `more_info` | Additional Info | Section Break | fa fa-file-text |  |  |  | None | None |
| `is_internal_customer` | Is Internal Customer | Check | None |  |  | ✅ | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | Company which internal customer represents. |
| `inter_company_reference` | Inter Company Reference | Link | Purchase Receipt |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  | ✅ |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `column_break_pxls` | None | Column Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `column_break5` | None | Column Break | None |  |  |  | None | None |
| `excise_page` | Excise Page Number | Data | None |  | ✅ |  | None | None |
| `instructions` | Instructions | Text | None |  |  |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 37
- **Dynamic Link Fields:** 0
- **Table Fields:** 5

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/delivery_note/delivery_note.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.add_fetch("customer", "tax_id", "tax_id");

cur_frm.cscript.tax_table = "Sales Taxes and Charges";

frappe.provide("erpnext.stock");
frappe.provide("erpnext.stock.delivery_note");
frappe.provide("erpnext.accounts.dimensions");

erpnext.accounts.taxes.setup_tax_filters("Sales Taxes and Charges");
erpnext.accounts.taxes.setup_tax_validations("Delivery Note");
erpnext.sales_common.setup_selling_controller();

frappe.ui.form.on("Delivery Note", {
	setup: function (frm) {
		(frm.custom_make_buttons = {
			"Packing Slip": "Packing Slip",
			"Installation Note": "Installation Note",
			"Sales Invoice": "Sales Invoice",
			"Stock Entry": "Return",
			Shipment: "Shipment",
		}),
			frm.set_indicator_formatter("item_code", function (doc) {
				return doc.docstatus == 1 || doc.qty <= doc.actual_qty ? "green" : "orange";
			});

		erpnext.queries.setup_queries(frm, "Warehouse", function () {
			return erpnext.queries.warehouse(frm.doc);
		});
		erpnext.queries.setup_warehouse_query(frm);

		frm.set_query("transporter", function () {
			return {
				filters: {
					is_transporter: 1,
				},
			};
		});

		frm.set_query("driver", function (doc) {
			return {
				filters: {
					transporter: doc.transporter,
				},
			};
		});

		frm.set_query("expense_account", "items", function (doc, cdt, cdn) {
			if (erpnext.is_perpetual_inventory_enabled(doc.company)) {
				return {
					filters: {
						report_type: "Profit and Loss",
						company: doc.company,
						is_group: 0,
					},
				};
			}
		});

		frm.set_query("cost_center", "items", function (doc, cdt, cdn) {
			if (erpnext.is_perpetual_inventory_enabled(doc.company)) {
				return {
					filters: {
						company: doc.company,
						is_group: 0,
					},
				};
			}
		});

		frm.set_df_property("packed_items", "cannot_add_rows", true);
		frm.set_df_property("packed_items", "cannot_delete_rows", true);
	},

	print_without_amount: function (frm) {
		erpnext.stock.delivery_note.set_print_hide(frm.doc);
	},

	refresh: function (frm) {
		if (
			frm.doc.docstatus === 1 &&
			frm.doc.is_return === 1 &&
			frm.doc.per_billed !== 100 &&
			frappe.model.can_create("Sales Invoice")
		) {
			frm.add_custom_button(
				__("Credit Note"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.stock.doctype.delivery_note.delivery_note.make_sales_invoice",
						frm: cur_frm,
					});
				},
				__("Create")
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (
			frm.doc.docstatus == 1 &&
			!frm.doc.inter_company_reference &&
			frappe.model.can_create("Purchase Receipt")
		) {
			let internal = frm.doc.is_internal_customer;
			if (internal) {
				let button_label =
					frm.doc.company === frm.doc.represents_company
						? "Internal Purchase Receipt"
						: "Inter Company Purchase Receipt";

				frm.add_custom_button(
					__(button_label),
					function () {
						frappe.model.open_mapped_doc({
							method: "erpnext.stock.doctype.delivery_note.delivery_note.make_inter_company_purchase_receipt",
							frm: frm,
						});
					},
					__("Create")
				);
			}
		}
	},
});

frappe.ui.form.on("Delivery Note Item", {
	expense_account: function (frm, dt, dn) {
		var d = locals[dt][dn];
		frm.update_in_all_rows("items", "expense_account", d.expense_account);
	},
	cost_center: function (frm, dt, dn) {
		var d = locals[dt][dn];
		frm.update_in_all_rows("items", "cost_center", d.cost_center);
	},
});

erpnext.stock.DeliveryNoteController = class DeliveryNoteController extends (
	erpnext.selling.SellingController
) {
	setup(doc) {
		this.setup_posting_date_time_check();
		super.setup(doc);
		this.frm.make_methods = {
			"Delivery Trip": this.make_delivery_trip,
		};
	}
	refresh(doc, dt, dn) {
		var me = this;
		super.refresh();
		if (
			!doc.is_return &&
			(doc.status != "Closed" || this.frm.is_new()) &&
			this.frm.has_perm("write") &&
			frappe.model.can_read("Sales Order") &&
			this.frm.doc.docstatus === 0
		) {
			this.frm.add_custom_button(
				__("Sales Order"),
				function () {
					if (!me.frm.doc.customer) {
						frappe.throw({
							title: __("Mandatory"),
							message: __("Please Select a Customer"),
						});
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.selling.doctype.sales_order.sales_order.make_delivery_note",
						args: {
							for_reserved_stock: 1,
						},
						source_doctype: "Sales Order",
						target: me.frm,
						setters: {
							customer: me.frm.doc.customer,
						},
						get_query_filters: {
							docstatus: 1,
							status: ["not in", ["Closed", "On Hold"]],
							per_delivered: ["<", 99.99],
							company: me.frm.doc.company,
							project: me.frm.doc.project || undefined,
						},
					});
				},
				__("Get Items From")
			);
		}

		if (
			!doc.is_return &&
			doc.status != "Closed" &&
			this.frm.has_perm("write") &&
			frappe.model.can_read("Pick List") &&
			this.frm.doc.docstatus === 0
		) {
			this.frm.add_custom_button(
				__("Pick List"),
				function () {
					if (!me.frm.doc.customer) {
						frappe.throw({
							title: __("Mandatory"),
							message: __("Please Select a Customer"),
						});
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.stock.doctype.pick_list.pick_list.create_dn_for_pick_lists",
						source_doctype: "Pick List",
						target: me.frm,
						setters: [
							{
								fieldname: "customer",
								default: me.frm.doc.customer,
								label: __("Customer"),
								fieldtype: "Link",
								options: "Customer",
								reqd: 1,
								read_only: 1,
							},
							{
								fieldname: "sales_order",
								label: __("Sales Order"),
								fieldtype: "Link",
								options: "Sales Order",
								link_filters: `[["Sales Order","customer","=","${me.frm.doc.customer}"],["Sales Order","docstatus","=","1"],["Sales Order","delivery_status","not in",["Closed","Fully Delivered"]]]`,
							},
						],
						get_query_filters: {
							company: me.frm.doc.company,
						},
						get_query_method: "erpnext.stock.doctype.pick_list.pick_list.get_pick_list_query",
						size: "extra-large",
					});
				},
				__("Get Items From")
			);
		}

		if (!doc.is_return && doc.status != "Closed") {
			if (doc.docstatus == 1 && frappe.model.can_create("Shipment")) {
				this.frm.add_custom_button(
					__("Shipment"),
					function () {
						me.make_shipment();
					},
					__("Create")
				);
			}

			if (
				flt(doc.per_installed, 2) < 100 &&
				doc.docstatus == 1 &&
				frappe.model.can_create("Installation Note")
			) {
				this.frm.add_custom_button(
					__("Installation Note"),
					function () {
						me.make_installation_note();
					},
					__("Create")
				);
			}

			if (doc.docstatus == 1 && this.frm.has_perm("create")) {
				this.frm.add_custom_button(
					__("Sales Return"),
					function () {
						me.make_sales_return();
					},
					__("Create")
				);
			}

			if (doc.docstatus == 1 && doc.status != "Completed" && frappe.model.can_create("Delivery Trip")) {
				this.frm.add_custom_button(
					__("Delivery Trip"),
					function () {
						me.make_delivery_trip();
					},
					__("Create")
				);
			}

			if (
				doc.docstatus == 0 &&
				!doc.__islocal &&
				doc.__onload &&
				doc.__onload.has_unpacked_items &&
				frappe.model.can_create("Packing Slip")
			) {
				this.frm.add_custom_button(
					__("Packing Slip"),
					function () {
						frappe.model.open_mapped_doc({
							method: "erpnext.stock.doctype.delivery_note.delivery_note.make_packing_slip",
							frm: me.frm,
						});
					},
					__("Create")
				);
			}

			if (!doc.__islocal && doc.docstatus == 1) {
				this.frm.page.set_inner_btn_group_as_primary(__("Create"));
			}
		}

		erpnext.accounts.ledger_preview.show_accounting_ledger_preview(this.frm);
		erpnext.accounts.ledger_preview.show_stock_ledger_preview(this.frm);

		if (doc.docstatus > 0) {
			this.show_stock_ledger();
			if (erpnext.is_perpetual_inventory_enabled(doc.company)) {
				this.show_general_ledger();
			}
			if (this.frm.has_perm("submit") && doc.status !== "Closed") {
				me.frm.add_custom_button(
					__("Close"),
					function () {
						me.close_delivery_note();
					},
					__("Status")
				);
			}
		}

		if (
			doc.docstatus == 1 &&
			!doc.is_return &&
			doc.status != "Closed" &&
			flt(doc.per_billed) < 100 &&
			frappe.model.can_create("Sales Invoice")
		) {
			// show Make Invoice button only if Delivery Note is not created from Sales Invoice
			var from_sales_invoice = false;
			from_sales_invoice = me.frm.doc.items.some(function (item) {
				return item.against_sales_invoice ? true : false;
			});

			if (!from_sales_invoice) {
				this.frm.add_custom_button(
					__("Sales Invoice"),
					function () {
						me.make_sales_invoice();
					},
					__("Create")
				);
			}
		}

		if (doc.docstatus == 1 && doc.status === "Closed" && this.frm.has_perm("submit")) {
			this.frm.add_custom_button(
				__("Reopen"),
				function () {
					me.reopen_delivery_note();
				},
				__("Status")
			);
		}
		erpnext.stock.delivery_note.set_print_hide(doc, dt, dn);
	}

	make_shipment() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.make_shipment",
			frm: this.frm,
		});
	}

	make_sales_invoice() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.make_sales_invoice",
			frm: this.frm,
		});
	}

	make_installation_note() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.make_installation_note",
			frm: this.frm,
		});
	}

	make_sales_return() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.make_sales_return",
			frm: this.frm,
		});
	}

	make_delivery_trip() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.make_delivery_trip",
			frm: cur_frm,
		});
	}

	tc_name() {
		this.get_terms();
	}

	items_on_form_rendered(doc, grid_row) {
		erpnext.setup_serial_or_batch_no();
	}

	packed_items_on_form_rendered(doc, grid_row) {
		erpnext.setup_serial_or_batch_no();
	}

	close_delivery_note(doc) {
		this.update_status("Closed");
	}

	reopen_delivery_note() {
		this.update_status("Submitted");
	}

	update_status(status) {
		var me = this;
		frappe.ui.form.is_saving = true;
		frappe.call({
			method: "erpnext.stock.doctype.delivery_note.delivery_note.update_delivery_note_status",
			args: { docname: me.frm.doc.name, status: status },
			callback: function (r) {
				if (!r.exc) me.frm.reload_doc();
			},
			always: function () {
				frappe.ui.form.is_saving = false;
			},
		});
	}
};

extend_cscript(cur_frm.cscript, new erpnext.stock.DeliveryNoteController({ frm: cur_frm }));

frappe.ui.form.on("Delivery Note", {
	setup: function (frm) {
		if (frm.doc.company) {
			frm.trigger("unhide_account_head");
		}
	},

	company: function (frm) {
		frm.trigger("unhide_account_head");
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	unhide_account_head: function (frm) {
		// unhide expense_account and cost_center if perpetual inventory is enabled in the company
		var aii_enabled = erpnext.is_perpetual_inventory_enabled(frm.doc.company);
		frm.fields_dict["items"].grid.set_column_disp(["expense_account", "cost_center"], aii_enabled);
	},
});

erpnext.stock.delivery_note.set_print_hide = function (doc, cdt, cdn) {
	var dn_fields = frappe.meta.docfield_map["Delivery Note"];
	var dn_item_fields = frappe.meta.docfield_map["Delivery Note Item"];
	var dn_fields_copy = dn_fields;
	var dn_item_fields_copy = dn_item_fields;
	if (doc.print_without_amount) {
		dn_fields["currency"].print_hide = 1;
		dn_item_fields["rate"].print_hide = 1;
		dn_item_fields["discount_percentage"].print_hide = 1;
		dn_item_fields["price_list_rate"].print_hide = 1;
		dn_item_fields["amount"].print_hide = 1;
		dn_item_fields["discount_amount"].print_hide = 1;
		dn_fields["taxes"].print_hide = 1;
	} else {
		if (dn_fields_copy["currency"].print_hide != 1) dn_fields["currency"].print_hide = 0;
		if (dn_item_fields_copy["rate"].print_hide != 1) dn_item_fields["rate"].print_hide = 0;
		if (dn_item_fields_copy["amount"].print_hide != 1) dn_item_fields["amount"].print_hide = 0;
		if (dn_item_fields_copy["discount_amount"].print_hide != 1)
			dn_item_fields["discount_amount"].print_hide = 0;
		if (dn_fields_copy["taxes"].print_hide != 1) dn_fields["taxes"].print_hide = 0;
	}
};

frappe.tour["Delivery Note"] = [
	{
		fieldname: "customer",
		title: __("Customer"),
		description: __("This field is used to set the 'Customer'."),
	},
	{
		fieldname: "items",
		title: __("Items"),
		description:
			__("This table is used to set details about the 'Item', 'Qty', 'Basic Rate', etc.") +
			" " +
			__("Different 'Source Warehouse' and 'Target Warehouse' can be set for each row."),
	},
	{
		fieldname: "set_posting_time",
		title: __("Edit Posting Date and Time"),
		description: __("This option can be checked to edit the 'Posting Date' and 'Posting Time' fields."),
	},
];

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Delayed Order Report` | Script Report | Stock |
| `Delayed Item Report` | Script Report | Stock |
| `Delivery Note Trends` | Script Report | Stock |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Delivery Trends` | Delivery Trends | Sum | Stock |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
