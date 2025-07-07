# Master Control Plan: `Purchase Receipt`

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
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `title` | Title | Data | None |  | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | MAT-PRE-.YYYY.-
MAT-PR-RET-.YYYY.- | ✅ |  |  | None | None |
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Supplier Name | Data | None |  |  | ✅ | None | None |
| `supplier_delivery_note` | Supplier Delivery Note | Data | None |  |  |  | None | None |
| `subcontracting_receipt` | Subcontracting Receipt | Link | Subcontracting Receipt |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None | ✅ |  |  | None | None |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `apply_putaway_rule` | Apply Putaway Rule | Check | None |  |  |  | 0 | None |
| `is_return` | Is Return | Check | None |  |  | ✅ | 0 | None |
| `return_against` | Return Against Purchase Receipt | Link | Purchase Receipt |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which supplier's currency is converted to company's base currency |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `buying_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency |  |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None |  |  |  | None | None |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `sec_warehouse` | Items | Section Break | None |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `column_break_31` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Accepted Warehouse | Link | Warehouse |  |  |  | None | None |
| `set_from_warehouse` | Set From Warehouse | Link | Warehouse |  |  |  | None | None |
| `col_break_warehouse` | None | Column Break | None |  |  |  | None | None |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  | ✅ | 0 | None |
| `supplier_warehouse` | Supplier Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Purchase Receipt Item | ✅ |  |  | None | None |
| `section_break0` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_43` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `column_break_27` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `tax_withholding_net_total` | Tax Withholding Net Total | Currency | currency |  | ✅ | ✅ | None | None |
| `base_tax_withholding_net_total` | Base Tax Withholding Net Total | Currency | None |  | ✅ | ✅ | None | None |
| `taxes_charges_section` | Taxes and Charges | Section Break | None |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Purchase Taxes and Charges Template | Link | Purchase Taxes and Charges Template |  |  |  | None | None |
| `shipping_col` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_53` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `taxes_section` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Purchase Taxes and Charges | Table | Purchase Taxes and Charges |  |  |  | None | None |
| `totals` | None | Section Break | fa fa-money |  |  |  | None | None |
| `base_taxes_and_charges_added` | Taxes and Charges Added (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_taxes_and_charges_deducted` | Taxes and Charges Deducted (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `taxes_and_charges_added` | Taxes and Charges Added | Currency | currency |  |  | ✅ | None | None |
| `taxes_and_charges_deducted` | Taxes and Charges Deducted | Currency | currency |  |  | ✅ | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `section_break_46` | Totals | Section Break | None |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `section_break_42` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_44` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `raw_material_details` | Raw Materials Consumed | Section Break | fa fa-table |  |  | ✅ | None | None |
| `get_current_stock` | Get Current Stock | Button | get_current_stock |  |  |  | None | None |
| `supplied_items` | Consumed Items | Table | Purchase Receipt Item Supplied |  |  |  | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `section_addresses` | Supplier Address | Section Break | None |  |  |  | None | None |
| `supplier_address` | Supplier Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break_address` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Small Text | Email |  |  | ✅ | None | None |
| `section_break_98` | Shipping Address | Section Break | None |  |  |  | None | None |
| `dispatch_address` | Dispatch Address Template | Link | Address |  |  |  | None | None |
| `dispatch_address_display` | Dispatch Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_100` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Shipping Address Template | Link | Address |  |  |  | None | None |
| `shipping_address_display` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `billing_address_section` | Company Billing Address | Section Break | None |  |  |  | None | None |
| `billing_address` | Billing Address | Link | Address |  |  |  | None | None |
| `column_break_104` | None | Column Break | None |  |  |  | None | None |
| `billing_address_display` | Billing Address | Text Editor | None |  |  | ✅ | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `status_section` | Status | Section Break | fa fa-file-text |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Partly Billed
To Bill
Completed
Return Issued
Cancelled
Closed | ✅ |  | ✅ | Draft | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `per_billed` | % Amount Billed | Percent | None |  |  | ✅ | None | None |
| `per_returned` | % Returned | Percent | None |  |  | ✅ | None | None |
| `subscription_detail` | Auto Repeat | Section Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `printing_settings` | Printing Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_97` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Data | None |  |  | ✅ | None | None |
| `transporter_info` | Transporter | Section Break | fa fa-truck |  |  |  | None | None |
| `transporter_name` | Transporter Name | Data | None |  |  |  | None | None |
| `column_break5` | None | Column Break | None |  |  |  | None | None |
| `lr_no` | Vehicle Number | Data | None |  |  |  | None | None |
| `lr_date` | Vehicle Date | Date | None |  |  |  | None | None |
| `additional_info_section` | Additional Info | Section Break | None |  |  |  | None | None |
| `instructions` | Instructions | Small Text | None |  |  |  | None | None |
| `is_internal_supplier` | Is Internal Supplier | Check | None |  |  | ✅ | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | None |
| `inter_company_reference` | Inter Company Reference | Link | Delivery Note |  |  | ✅ | None | None |
| `column_break_131` | None | Column Break | None |  |  |  | None | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `range` | Range | Data | None |  | ✅ |  | None | None |
| `amended_from` | Amended From | Link | Purchase Receipt |  | ✅ | ✅ | None | None |
| `is_old_subcontracting_flow` | Is Old Subcontracting Flow | Check | None |  | ✅ | ✅ | 0 | None |
| `other_details` | Other Details | HTML | <div class="columnHeading">Other Details</div> |  | ✅ |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 29
- **Dynamic Link Fields:** 0
- **Table Fields:** 4

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/purchase_receipt/purchase_receipt.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.stock");

cur_frm.cscript.tax_table = "Purchase Taxes and Charges";

erpnext.accounts.taxes.setup_tax_filters("Purchase Taxes and Charges");
erpnext.accounts.taxes.setup_tax_validations("Purchase Receipt");
erpnext.buying.setup_buying_controller();

frappe.ui.form.on("Purchase Receipt", {
	setup: (frm) => {
		frm.custom_make_buttons = {
			"Stock Entry": "Return",
			"Purchase Invoice": "Purchase Invoice",
			"Landed Cost Voucher": "Landed Cost Voucher",
		};

		frm.set_query("expense_account", "items", function () {
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: frm.doc.company },
			};
		});

		frm.set_query("wip_composite_asset", "items", function () {
			return {
				filters: { is_composite_asset: 1, docstatus: 0 },
			};
		});

		frm.set_query("taxes_and_charges", function () {
			return {
				filters: { company: frm.doc.company },
			};
		});

		frm.set_query("subcontracting_receipt", function () {
			return {
				filters: {
					docstatus: 1,
					supplier: frm.doc.supplier,
				},
			};
		});
	},
	onload: function (frm) {
		erpnext.queries.setup_queries(frm, "Warehouse", function () {
			return erpnext.queries.warehouse(frm.doc);
		});
	},

	refresh: function (frm) {
		if (frm.doc.company) {
			frm.trigger("toggle_display_account_head");
		}

		if (frm.doc.docstatus === 1 && frm.doc.is_return === 1 && frm.doc.per_billed !== 100) {
			frm.add_custom_button(
				__("Debit Note"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_purchase_invoice",
						frm: cur_frm,
					});
				},
				__("Create")
			);
			frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (frm.doc.docstatus === 1 && frm.doc.is_internal_supplier && !frm.doc.inter_company_reference) {
			frm.add_custom_button(
				__("Delivery Note"),
				function () {
					frappe.model.open_mapped_doc({
						method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_inter_company_delivery_note",
						frm: cur_frm,
					});
				},
				__("Create")
			);
		}

		if (frm.doc.docstatus === 0) {
			if (!frm.doc.is_return) {
				frappe.db.get_single_value("Buying Settings", "maintain_same_rate").then((value) => {
					if (value) {
						frm.doc.items.forEach((item) => {
							frm.fields_dict.items.grid.update_docfield_property(
								"rate",
								"read_only",
								item.purchase_order && item.purchase_order_item
							);
						});
					}
				});
			}
		}

		if (frm.doc.docstatus === 1) {
			frm.add_custom_button(
				__("Landed Cost Voucher"),
				() => {
					frm.events.make_lcv(frm);
				},
				__("Create")
			);
		}

		frm.events.add_custom_buttons(frm);
	},

	make_lcv(frm) {
		frappe.call({
			method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_lcv",
			args: {
				doctype: frm.doc.doctype,
				docname: frm.doc.name,
			},
			callback: (r) => {
				if (r.message) {
					var doc = frappe.model.sync(r.message);
					frappe.set_route("Form", doc[0].doctype, doc[0].name);
				}
			},
		});
	},

	add_custom_buttons: function (frm) {
		if (frm.doc.docstatus == 0) {
			frm.add_custom_button(
				__("Purchase Invoice"),
				function () {
					if (!frm.doc.supplier) {
						frappe.throw({
							title: __("Mandatory"),
							message: __("Please Select a Supplier"),
						});
					}
					erpnext.utils.map_current_doc({
						method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.make_purchase_receipt",
						source_doctype: "Purchase Invoice",
						target: frm,
						setters: {
							supplier: frm.doc.supplier,
						},
						get_query_filters: {
							docstatus: 1,
							per_received: ["<", 100],
							company: frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);
		}
	},

	company: function (frm) {
		frm.trigger("toggle_display_account_head");
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	subcontracting_receipt: (frm) => {
		if (
			frm.doc.is_subcontracted === 1 &&
			frm.doc.is_old_subcontracting_flow === 0 &&
			frm.doc.subcontracting_receipt
		) {
			frm.set_value("items", null);

			erpnext.utils.map_current_doc({
				method: "erpnext.subcontracting.doctype.subcontracting_receipt.subcontracting_receipt.make_purchase_receipt",
				source_name: frm.doc.subcontracting_receipt,
				target_doc: frm,
				freeze: true,
				freeze_message: __("Mapping Purchase Receipt ..."),
			});
		}
	},

	toggle_display_account_head: function (frm) {
		var enabled = erpnext.is_perpetual_inventory_enabled(frm.doc.company);
		frm.fields_dict["items"].grid.set_column_disp(["cost_center"], enabled);
	},
});

erpnext.stock.PurchaseReceiptController = class PurchaseReceiptController extends (
	erpnext.buying.BuyingController
) {
	setup(doc) {
		this.setup_posting_date_time_check();
		super.setup(doc);
	}

	onload() {
		this.frm.set_query("supplier", function () {
			return {
				filters: {
					is_transporter: 0,
				},
			};
		});
	}

	refresh() {
		var me = this;
		super.refresh();

		erpnext.accounts.ledger_preview.show_accounting_ledger_preview(this.frm);
		erpnext.accounts.ledger_preview.show_stock_ledger_preview(this.frm);

		if (this.frm.doc.docstatus > 0) {
			this.show_stock_ledger();
			//removed for temporary
			this.show_general_ledger();

			this.frm.add_custom_button(
				__("Asset"),
				function () {
					frappe.route_options = {
						purchase_receipt: me.frm.doc.name,
					};
					frappe.set_route("List", "Asset");
				},
				__("View")
			);

			this.frm.add_custom_button(
				__("Asset Movement"),
				function () {
					frappe.route_options = {
						reference_name: me.frm.doc.name,
					};
					frappe.set_route("List", "Asset Movement");
				},
				__("View")
			);
		}

		if (!this.frm.doc.is_return && this.frm.doc.status != "Closed") {
			if (this.frm.doc.docstatus == 0) {
				this.frm.add_custom_button(
					__("Purchase Order"),
					function () {
						if (!me.frm.doc.supplier) {
							frappe.throw({
								title: __("Mandatory"),
								message: __("Please Select a Supplier"),
							});
						}
						erpnext.utils.map_current_doc({
							method: "erpnext.buying.doctype.purchase_order.purchase_order.make_purchase_receipt",
							source_doctype: "Purchase Order",
							target: me.frm,
							setters: {
								supplier: me.frm.doc.supplier,
								schedule_date: undefined,
							},
							get_query_filters: {
								docstatus: 1,
								status: ["not in", ["Closed", "On Hold"]],
								per_received: ["<", 99.99],
								company: me.frm.doc.company,
							},
						});
					},
					__("Get Items From")
				);
			}

			if (this.frm.doc.docstatus == 1 && this.frm.doc.status != "Closed") {
				if (this.frm.has_perm("submit")) {
					cur_frm.add_custom_button(__("Close"), this.close_purchase_receipt, __("Status"));
				}

				cur_frm.add_custom_button(__("Purchase Return"), this.make_purchase_return, __("Create"));

				cur_frm.add_custom_button(
					__("Make Stock Entry"),
					cur_frm.cscript["Make Stock Entry"],
					__("Create")
				);

				if (flt(this.frm.doc.per_billed) < 100) {
					cur_frm.add_custom_button(
						__("Purchase Invoice"),
						this.make_purchase_invoice,
						__("Create")
					);
				}
				cur_frm.add_custom_button(
					__("Retention Stock Entry"),
					this.make_retention_stock_entry,
					__("Create")
				);

				cur_frm.page.set_inner_btn_group_as_primary(__("Create"));
			}
		}

		if (this.frm.doc.docstatus == 1 && this.frm.doc.status === "Closed" && this.frm.has_perm("submit")) {
			cur_frm.add_custom_button(__("Reopen"), this.reopen_purchase_receipt, __("Status"));
		}

		this.frm.toggle_reqd("supplier_warehouse", this.frm.doc.is_old_subcontracting_flow);
	}

	make_purchase_invoice() {
		frappe.model.open_mapped_doc({
			method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_purchase_invoice",
			frm: cur_frm,
		});
	}

	make_purchase_return() {
		let me = this;

		let has_rejected_items = cur_frm.doc.items.filter((item) => {
			if (item.rejected_qty > 0) {
				return true;
			}
		});

		if (has_rejected_items && has_rejected_items.length > 0) {
			frappe.prompt(
				[
					{
						label: __("Return Qty from Rejected Warehouse"),
						fieldtype: "Check",
						fieldname: "return_for_rejected_warehouse",
						default: 1,
					},
				],
				function (values) {
					if (values.return_for_rejected_warehouse) {
						frappe.call({
							method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_purchase_return_against_rejected_warehouse",
							args: {
								source_name: cur_frm.doc.name,
							},
							callback: function (r) {
								if (r.message) {
									frappe.model.sync(r.message);
									frappe.set_route("Form", r.message.doctype, r.message.name);
								}
							},
						});
					} else {
						cur_frm.cscript._make_purchase_return();
					}
				},
				__("Return Qty"),
				__("Make Return Entry")
			);
		} else {
			cur_frm.cscript._make_purchase_return();
		}
	}

	close_purchase_receipt() {
		cur_frm.cscript.update_status("Closed");
	}

	reopen_purchase_receipt() {
		cur_frm.cscript.update_status("Submitted");
	}

	make_retention_stock_entry() {
		frappe.call({
			method: "erpnext.stock.doctype.stock_entry.stock_entry.move_sample_to_retention_warehouse",
			args: {
				company: cur_frm.doc.company,
				items: cur_frm.doc.items,
			},
			callback: function (r) {
				if (r.message) {
					var doc = frappe.model.sync(r.message)[0];
					frappe.set_route("Form", doc.doctype, doc.name);
				} else {
					frappe.msgprint(
						__("Purchase Receipt doesn't have any Item for which Retain Sample is enabled.")
					);
				}
			},
		});
	}

	apply_putaway_rule() {
		if (this.frm.doc.apply_putaway_rule) erpnext.apply_putaway_rule(this.frm);
	}
};

// for backward compatibility: combine new and previous states
extend_cscript(cur_frm.cscript, new erpnext.stock.PurchaseReceiptController({ frm: cur_frm }));

cur_frm.cscript.update_status = function (status) {
	frappe.ui.form.is_saving = true;
	frappe.call({
		method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.update_purchase_receipt_status",
		args: { docname: cur_frm.doc.name, status: status },
		callback: function (r) {
			if (!r.exc) cur_frm.reload_doc();
		},
		always: function () {
			frappe.ui.form.is_saving = false;
		},
	});
};

cur_frm.fields_dict["items"].grid.get_field("project").get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Project", "status", "not in", "Completed, Cancelled"]],
	};
};

cur_frm.fields_dict["select_print_heading"].get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Print Heading", "docstatus", "!=", "2"]],
	};
};

cur_frm.fields_dict["items"].grid.get_field("bom").get_query = function (doc, cdt, cdn) {
	var d = locals[cdt][cdn];
	return {
		filters: [
			["BOM", "item", "=", d.item_code],
			["BOM", "is_active", "=", "1"],
			["BOM", "docstatus", "=", "1"],
		],
	};
};

frappe.provide("erpnext.buying");

frappe.ui.form.on("Purchase Receipt", "is_subcontracted", function (frm) {
	if (frm.doc.is_old_subcontracting_flow) {
		erpnext.buying.get_default_bom(frm);
	}

	frm.toggle_reqd("supplier_warehouse", frm.doc.is_old_subcontracting_flow);
});

frappe.ui.form.on("Purchase Receipt Item", {
	item_code: function (frm, cdt, cdn) {
		var d = locals[cdt][cdn];
		frappe.db.get_value("Item", { name: d.item_code }, "sample_quantity", (r) => {
			frappe.model.set_value(cdt, cdn, "sample_quantity", r.sample_quantity);
			validate_sample_quantity(frm, cdt, cdn);
		});
	},
	qty: function (frm, cdt, cdn) {
		validate_sample_quantity(frm, cdt, cdn);
	},
	sample_quantity: function (frm, cdt, cdn) {
		validate_sample_quantity(frm, cdt, cdn);
	},
	batch_no: function (frm, cdt, cdn) {
		validate_sample_quantity(frm, cdt, cdn);
	},
});

cur_frm.cscript._make_purchase_return = function () {
	frappe.model.open_mapped_doc({
		method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_purchase_return",
		frm: cur_frm,
	});
};

cur_frm.cscript["Make Stock Entry"] = function () {
	frappe.model.open_mapped_doc({
		method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_stock_entry",
		frm: cur_frm,
	});
};

var validate_sample_quantity = function (frm, cdt, cdn) {
	var d = locals[cdt][cdn];
	if (d.sample_quantity && d.qty) {
		frappe.call({
			method: "erpnext.stock.doctype.stock_entry.stock_entry.validate_sample_quantity",
			args: {
				batch_no: d.batch_no,
				item_code: d.item_code,
				sample_quantity: d.sample_quantity,
				qty: d.qty,
			},
			callback: (r) => {
				frappe.model.set_value(cdt, cdn, "sample_quantity", r.message);
			},
		});
	}
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Purchase Receipt Trends` | Script Report | Stock |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Purchase Receipt Trends` | Purchase Receipt Trends | Sum | Stock |



### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
