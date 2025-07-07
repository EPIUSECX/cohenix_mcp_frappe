# Master Control Plan: `Purchase Order`

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
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `title` | Title | Data | None | ✅ | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | PUR-ORD-.YYYY.- | ✅ |  |  | None | None |
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Supplier Name | Data | None |  |  | ✅ | None | None |
| `order_confirmation_no` | Order Confirmation No | Data | None |  |  |  | None | None |
| `order_confirmation_date` | Order Confirmation Date | Date | None |  |  |  | None | None |
| `get_items_from_open_material_requests` | Get Items from Open Material Requests | Button | None |  |  |  | None | Fetch items based on Default Supplier. |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `schedule_date` | Required By | Date | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `apply_tds` | Apply Tax Withholding Amount | Check | None |  |  |  | 0 | None |
| `tax_withholding_category` | Tax Withholding Category | Link | Tax Withholding Category |  |  |  | None | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  |  | 0 | None |
| `has_unit_price_items` | Has Unit Price Items | Check | None |  | ✅ |  | 0 | None |
| `supplier_warehouse` | Supplier Warehouse | Link | Warehouse |  |  |  | None | None |
| `amended_from` | Amended From | Link | Purchase Order |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions  | Section Break | None |  |  |  | None | None |
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
| `before_items_section` | None | Section Break | None |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `set_from_warehouse` | Set From Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_col_break` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Set Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Purchase Order Item | ✅ |  |  | None | None |
| `sb_last_purchase` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_26` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `tax_withholding_net_total` | Tax Withholding Net Total | Currency | currency |  | ✅ | ✅ | 0 | None |
| `base_tax_withholding_net_total` | Base Tax Withholding Net Total | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `section_break_48` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Purchase Order Pricing Rule | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `raw_material_details` | Raw Materials Supplied | Section Break | None |  |  |  | None | None |
| `set_reserve_warehouse` | Set Reserve Warehouse | Link | Warehouse |  |  |  | None | None |
| `supplied_items` | Supplied Items | Table | Purchase Order Item Supplied |  |  | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Purchase Taxes and Charges Template | Link | Purchase Taxes and Charges Template |  |  |  | None | None |
| `column_break_53` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_52` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Purchase Taxes and Charges | Table | Purchase Taxes and Charges |  |  |  | None | None |
| `totals` | None | Section Break | fa fa-money |  |  |  | None | None |
| `base_taxes_and_charges_added` | Taxes and Charges Added (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_taxes_and_charges_deducted` | Taxes and Charges Deducted (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_39` | None | Column Break | None |  |  |  | None | None |
| `taxes_and_charges_added` | Taxes and Charges Added | Currency | currency |  |  | ✅ | None | None |
| `taxes_and_charges_deducted` | Taxes and Charges Deducted | Currency | currency |  |  | ✅ | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `totals_section` | Totals | Section Break | None |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `advance_paid` | Advance Paid | Currency | party_account_currency |  |  | ✅ | None | None |
| `discount_section` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_45` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `section_addresses` | Supplier Address | Section Break | None |  |  |  | None | None |
| `supplier_address` | Supplier Address | Link | Address |  |  |  | None | None |
| `address_display` | Supplier Address Details | Text Editor | None |  |  | ✅ | None | None |
| `col_break_address` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Supplier Contact | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact Name | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Contact Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Small Text | Email |  |  | ✅ | None | None |
| `shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `dispatch_address` | Dispatch Address | Link | Address |  |  |  | None | None |
| `dispatch_address_display` | Dispatch Address Details | Text Editor | None |  |  | ✅ | None | None |
| `column_break_99` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Shipping Address | Link | Address |  |  |  | None | None |
| `shipping_address_display` | Shipping Address Details | Text Editor | None |  |  | ✅ | None | None |
| `company_billing_address_section` | Company Billing Address | Section Break | None |  |  |  | None | None |
| `billing_address` | Company Billing Address | Link | Address |  |  |  | None | None |
| `column_break_103` | None | Column Break | None |  |  |  | None | None |
| `billing_address_display` | Billing Address Details | Text Editor | None |  |  | ✅ | None | None |
| `drop_ship` | Drop Ship | Tab Break | None |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  | ✅ | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `customer_contact_person` | Customer Contact | Link | Contact |  |  |  | None | None |
| `customer_contact_display` | Customer Contact | Small Text | None |  |  |  | None | None |
| `customer_contact_mobile` | Customer Mobile No | Small Text | Phone |  | ✅ |  | None | None |
| `customer_contact_email` | Customer Contact Email | Code | Email |  | ✅ |  | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `payment_schedule_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `terms_section_break` | Terms & Conditions | Section Break | fa fa-legal |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `tracking_section` | Order Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
On Hold
To Receive and Bill
To Bill
To Receive
Completed
Cancelled
Closed
Delivered | ✅ |  | ✅ | Draft | None |
| `advance_payment_status` | Advance Payment Status | Select | Not Initiated
Initiated
Partially Paid
Fully Paid |  | ✅ |  | None | None |
| `column_break_75` | None | Column Break | None |  |  |  | None | None |
| `per_billed` | % Billed | Percent | None |  |  | ✅ | None | None |
| `per_received` | % Received | Percent | None |  |  | ✅ | None | None |
| `column_break5` | Printing Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_86` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Data | None |  |  |  | None | None |
| `subscription_section` | Auto Repeat | Section Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `column_break_97` | None | Column Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `additional_info_section` | Additional Info | Section Break | None |  |  |  | None | None |
| `is_internal_supplier` | Is Internal Supplier | Check | None |  |  | ✅ | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | None |
| `ref_sq` | Supplier Quotation | Link | Supplier Quotation |  |  | ✅ | None | None |
| `column_break_74` | None | Column Break | None |  |  |  | None | None |
| `party_account_currency` | Party Account Currency | Link | Currency |  | ✅ | ✅ | None | None |
| `inter_company_order_reference` | Inter Company Order Reference | Link | Sales Order |  |  | ✅ | None | None |
| `is_old_subcontracting_flow` | Is Old Subcontracting Flow | Check | None |  | ✅ | ✅ | 0 | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 33
- **Dynamic Link Fields:** 0
- **Table Fields:** 5

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/purchase_order/purchase_order.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.buying");
frappe.provide("erpnext.accounts.dimensions");

cur_frm.cscript.tax_table = "Purchase Taxes and Charges";

erpnext.accounts.taxes.setup_tax_filters("Purchase Taxes and Charges");
erpnext.accounts.taxes.setup_tax_validations("Purchase Order");
erpnext.buying.setup_buying_controller();

frappe.ui.form.on("Purchase Order", {
	setup: function (frm) {
		frm.ignore_doctypes_on_cancel_all = ["Unreconcile Payment", "Unreconcile Payment Entries"];
		if (frm.doc.is_old_subcontracting_flow) {
			frm.set_query("reserve_warehouse", "supplied_items", function () {
				return {
					filters: {
						company: frm.doc.company,
						name: ["!=", frm.doc.supplier_warehouse],
						is_group: 0,
					},
				};
			});
		}

		frm.set_indicator_formatter("item_code", function (doc) {
			let color;
			if (!doc.qty && frm.doc.has_unit_price_items) {
				color = "yellow";
			} else if (doc.qty <= doc.received_qty) {
				color = "green";
			} else {
				color = "orange";
			}
			return color;
		});

		frm.set_query("expense_account", "items", function () {
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: frm.doc.company },
			};
		});

		frm.set_query("fg_item", "items", function () {
			return {
				filters: {
					is_stock_item: 1,
					is_sub_contracted_item: 1,
					default_bom: ["!=", ""],
				},
			};
		});
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);
	},

	schedule_date(frm) {
		if (frm.doc.schedule_date) {
			frm.doc.items.forEach((d) => {
				frappe.model.set_value(d.doctype, d.name, "schedule_date", frm.doc.schedule_date);
			});
		}
	},

	transaction_date(frm) {
		prevent_past_schedule_dates(frm);
		frm.set_value("schedule_date", "");
	},

	refresh: function (frm) {
		if (frm.doc.is_old_subcontracting_flow) {
			frm.trigger("get_materials_from_supplier");

			$("a.grey-link").each(function () {
				var id = $(this).children(":first-child").attr("data-label");
				if (id == "Duplicate") {
					$(this).remove();
					return false;
				}
			});
		}

		if (frm.doc.docstatus == 0) {
			erpnext.set_unit_price_items_note(frm);
		}
		prevent_past_schedule_dates(frm);
	},

	supplier: function (frm) {
		// Do not update if inter company reference is there as the details will already be updated
		if (frm.updating_party_details || frm.doc.inter_company_invoice_reference) return;

		if (frm.doc.__onload && frm.doc.__onload.load_after_mapping) return;

		erpnext.utils.get_party_details(
			frm,
			"erpnext.accounts.party.get_party_details",
			{
				posting_date: frm.doc.transaction_date,
				bill_date: frm.doc.bill_date,
				party: frm.doc.supplier,
				party_type: "Supplier",
				account: frm.doc.credit_to,
				price_list: frm.doc.buying_price_list,
				fetch_payment_terms_template: cint(!frm.doc.ignore_default_payment_terms_template),
			},
			function () {
				frm.set_df_property("apply_tds", "read_only", frm.supplier_tds ? 0 : 1);
				frm.set_df_property("tax_withholding_category", "hidden", frm.supplier_tds ? 0 : 1);
			}
		);
	},

	get_materials_from_supplier: function (frm) {
		let po_details = [];

		if (frm.doc.supplied_items && (flt(frm.doc.per_received) == 100 || frm.doc.status === "Closed")) {
			frm.doc.supplied_items.forEach((d) => {
				if (d.total_supplied_qty && d.total_supplied_qty != d.consumed_qty) {
					po_details.push(d.name);
				}
			});
		}

		if (po_details && po_details.length) {
			frm.add_custom_button(
				__("Return of Components"),
				() => {
					frm.call({
						method: "erpnext.controllers.subcontracting_controller.get_materials_from_supplier",
						freeze: true,
						freeze_message: __("Creating Stock Entry"),
						args: {
							subcontract_order: frm.doc.name,
							rm_details: po_details,
							order_doctype: frm.doc.doctype,
						},
						callback: function (r) {
							if (r && r.message) {
								const doc = frappe.model.sync(r.message);
								frappe.set_route("Form", doc[0].doctype, doc[0].name);
							}
						},
					});
				},
				__("Create")
			);
		}
	},

	onload: function (frm) {
		set_schedule_date(frm);
		if (!frm.doc.transaction_date) {
			frm.set_value("transaction_date", frappe.datetime.get_today());
		}

		if (frm.doc.__onload && frm.doc.supplier) {
			if (frm.is_new()) {
				frm.doc.apply_tds = frm.doc.__onload.supplier_tds ? 1 : 0;
			}
			if (!frm.doc.__onload.supplier_tds) {
				frm.set_df_property("apply_tds", "read_only", 1);
			}
		}

		erpnext.queries.setup_queries(frm, "Warehouse", function () {
			return erpnext.queries.warehouse(frm.doc);
		});

		// On cancel and amending a purchase order with advance payment, reset advance paid amount
		if (frm.is_new()) {
			frm.set_value("advance_paid", 0);
		}
	},

	apply_tds: function (frm) {
		if (!frm.doc.apply_tds) {
			frm.set_value("tax_withholding_category", "");
		} else {
			frm.set_value("tax_withholding_category", frm.supplier_tds);
		}
	},

	get_subcontracting_boms_for_finished_goods: function (fg_item) {
		return frappe.call({
			method: "erpnext.subcontracting.doctype.subcontracting_bom.subcontracting_bom.get_subcontracting_boms_for_finished_goods",
			args: {
				fg_items: fg_item,
			},
		});
	},

	get_subcontracting_boms_for_service_item: function (service_item) {
		return frappe.call({
			method: "erpnext.subcontracting.doctype.subcontracting_bom.subcontracting_bom.get_subcontracting_boms_for_service_item",
			args: {
				service_item: service_item,
			},
		});
	},
});

frappe.ui.form.on("Purchase Order Item", {
	schedule_date: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (row.schedule_date) {
			if (!frm.doc.schedule_date) {
				erpnext.utils.copy_value_in_all_rows(frm.doc, cdt, cdn, "items", "schedule_date");
			} else {
				set_schedule_date(frm);
			}
		}
	},

	item_code: async function (frm, cdt, cdn) {
		if (frm.doc.is_subcontracted && !frm.doc.is_old_subcontracting_flow) {
			var row = locals[cdt][cdn];

			if (row.item_code && !row.fg_item) {
				var result = await frm.events.get_subcontracting_boms_for_service_item(row.item_code);

				if (result.message && Object.keys(result.message).length) {
					var finished_goods = Object.keys(result.message);

					// Set FG if only one active Subcontracting BOM is found
					if (finished_goods.length === 1) {
						row.fg_item = result.message[finished_goods[0]].finished_good;
						row.uom = result.message[finished_goods[0]].finished_good_uom;
						refresh_field("items");
					} else {
						const dialog = new frappe.ui.Dialog({
							title: __("Select Finished Good"),
							size: "small",
							fields: [
								{
									fieldname: "finished_good",
									fieldtype: "Autocomplete",
									label: __("Finished Good"),
									options: finished_goods,
								},
							],
							primary_action_label: __("Select"),
							primary_action: () => {
								var subcontracting_bom = result.message[dialog.get_value("finished_good")];

								if (subcontracting_bom) {
									row.fg_item = subcontracting_bom.finished_good;
									row.uom = subcontracting_bom.finished_good_uom;
									refresh_field("items");
								}

								dialog.hide();
							},
						});

						dialog.show();
					}
				}
			}
		}
	},

	fg_item: async function (frm, cdt, cdn) {
		if (frm.doc.is_subcontracted && !frm.doc.is_old_subcontracting_flow) {
			var row = locals[cdt][cdn];

			if (row.fg_item) {
				var result = await frm.events.get_subcontracting_boms_for_finished_goods(row.fg_item);

				if (result.message && Object.keys(result.message).length) {
					frappe.model.set_value(cdt, cdn, "item_code", result.message.service_item);
					frappe.model.set_value(
						cdt,
						cdn,
						"qty",
						flt(row.fg_item_qty) * flt(result.message.conversion_factor)
					);
					frappe.model.set_value(cdt, cdn, "uom", result.message.service_item_uom);
				}
			}
		}
	},

	qty: async function (frm, cdt, cdn) {
		if (frm.doc.is_subcontracted && !frm.doc.is_old_subcontracting_flow) {
			var row = locals[cdt][cdn];

			if (row.fg_item) {
				var result = await frm.events.get_subcontracting_boms_for_finished_goods(row.fg_item);

				if (
					result.message &&
					row.item_code == result.message.service_item &&
					row.uom == result.message.service_item_uom
				) {
					frappe.model.set_value(
						cdt,
						cdn,
						"fg_item_qty",
						flt(row.qty) / flt(result.message.conversion_factor)
					);
				}
			}
		}
	},
});

erpnext.buying.PurchaseOrderController = class PurchaseOrderController extends (
	erpnext.buying.BuyingController
) {
	setup() {
		this.frm.custom_make_buttons = {
			"Purchase Receipt": "Purchase Receipt",
			"Purchase Invoice": "Purchase Invoice",
			"Payment Entry": "Payment",
			"Subcontracting Order": "Subcontracting Order",
			"Stock Entry": "Material to Supplier",
		};

		super.setup();
	}

	refresh(doc, cdt, cdn) {
		var me = this;
		super.refresh();
		var allow_receipt = false;
		var is_drop_ship = false;

		for (var i in this.frm.doc.items) {
			var item = this.frm.doc.items[i];
			if (item.delivered_by_supplier !== 1) {
				allow_receipt = true;
			} else {
				is_drop_ship = true;
			}

			if (is_drop_ship && allow_receipt) {
				break;
			}
		}

		this.frm.set_df_property("drop_ship", "hidden", !is_drop_ship);

		if (doc.docstatus == 1) {
			this.frm.fields_dict.items_section.wrapper.addClass("hide-border");
			if (!this.frm.doc.set_warehouse) {
				this.frm.fields_dict.items_section.wrapper.removeClass("hide-border");
			}

			if (!["Closed", "Delivered"].includes(doc.status)) {
				if (
					this.frm.doc.status !== "Closed" &&
					flt(this.frm.doc.per_received) < 100 &&
					flt(this.frm.doc.per_billed) < 100
				) {
					if (!this.frm.doc.__onload || this.frm.doc.__onload.can_update_items) {
						this.frm.add_custom_button(__("Update Items"), () => {
							erpnext.utils.update_child_items({
								frm: this.frm,
								child_docname: "items",
								child_doctype: "Purchase Order Detail",
								cannot_add_row: false,
							});
						});
					}
				}
				if (this.frm.has_perm("submit")) {
					if (flt(doc.per_billed) < 100 || flt(doc.per_received) < 100) {
						if (doc.status != "On Hold") {
							this.frm.add_custom_button(
								__("Hold"),
								() => this.hold_purchase_order(),
								__("Status")
							);
						} else {
							this.frm.add_custom_button(
								__("Resume"),
								() => this.unhold_purchase_order(),
								__("Status")
							);
						}
						this.frm.add_custom_button(
							__("Close"),
							() => this.close_purchase_order(),
							__("Status")
						);
					}
				}

				if (is_drop_ship && doc.status != "Delivered") {
					this.frm.add_custom_button(
						__("Delivered"),
						this.delivered_by_supplier.bind(this),
						__("Status")
					);

					this.frm.page.set_inner_btn_group_as_primary(__("Status"));
				}
			} else if (["Closed", "Delivered"].includes(doc.status)) {
				if (this.frm.has_perm("submit")) {
					this.frm.add_custom_button(
						__("Re-open"),
						() => this.unclose_purchase_order(),
						__("Status")
					);
				}
			}
			if (doc.status != "Closed") {
				if (doc.status != "On Hold") {
					if (flt(doc.per_received) < 100 && allow_receipt) {
						this.frm.add_custom_button(
							__("Purchase Receipt"),
							() => {
								me.make_purchase_receipt();
							},
							__("Create")
						);
						if (doc.is_subcontracted) {
							if (doc.is_old_subcontracting_flow) {
								if (me.has_unsupplied_items()) {
									this.frm.add_custom_button(
										__("Material to Supplier"),
										function () {
											me.make_stock_entry();
										},
										__("Transfer")
									);
								}
							} else {
								if (!doc.items.every((item) => item.qty == item.subcontracted_quantity)) {
									this.frm.add_custom_button(
										__("Subcontracting Order"),
										() => {
											me.make_subcontracting_order();
										},
										__("Create")
									);
								}
							}
						}
					}
					// Please do not add precision in the below flt function
					if (flt(doc.per_billed) < 100)
						this.frm.add_custom_button(
							__("Purchase Invoice"),
							() => {
								me.make_purchase_invoice();
							},
							__("Create")
						);

					if (flt(doc.per_billed) < 100 && doc.status != "Delivered") {
						this.frm.add_custom_button(
							__("Payment"),
							() => this.make_payment_entry(),
							__("Create")
						);
					}

					if (flt(doc.per_billed) < 100) {
						this.frm.add_custom_button(
							__("Payment Request"),
							function () {
								me.make_payment_request();
							},
							__("Create")
						);
					}

					if (doc.docstatus === 1 && !doc.inter_company_order_reference) {
						let me = this;
						let internal = me.frm.doc.is_internal_supplier;
						if (internal) {
							let button_label =
								me.frm.doc.company === me.frm.doc.represents_company
									? "Internal Sales Order"
									: "Inter Company Sales Order";

							me.frm.add_custom_button(
								button_label,
								function () {
									me.make_inter_company_order(me.frm);
								},
								__("Create")
							);
						}
					}
				}

				this.frm.page.set_inner_btn_group_as_primary(__("Create"));
			}
		} else if (doc.docstatus === 0) {
			this.frm.cscript.add_from_mappers();
		}
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

	get_items_from_open_material_requests() {
		erpnext.utils.map_current_doc({
			method: "erpnext.stock.doctype.material_request.material_request.make_purchase_order_based_on_supplier",
			args: {
				supplier: this.frm.doc.supplier,
			},
			source_doctype: "Material Request",
			source_name: this.frm.doc.supplier,
			target: this.frm,
			setters: {
				company: this.frm.doc.company,
			},
			get_query_filters: {
				docstatus: ["!=", 2],
				supplier: this.frm.doc.supplier,
			},
			get_query_method:
				"erpnext.stock.doctype.material_request.material_request.get_material_requests_based_on_supplier",
		});
	}

	validate() {
		set_schedule_date(this.frm);
	}

	has_unsupplied_items() {
		return this.frm.doc["supplied_items"].some((item) => item.required_qty > item.supplied_qty);
	}

	make_stock_entry() {
		frappe.call({
			method: "erpnext.controllers.subcontracting_controller.make_rm_stock_entry",
			args: {
				subcontract_order: this.frm.doc.name,
				order_doctype: this.frm.doc.doctype,
			},
			callback: function (r) {
				var doclist = frappe.model.sync(r.message);
				frappe.set_route("Form", doclist[0].doctype, doclist[0].name);
			},
		});
	}

	make_inter_company_order(frm) {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.purchase_order.purchase_order.make_inter_company_sales_order",
			frm: frm,
		});
	}

	make_purchase_receipt() {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.purchase_order.purchase_order.make_purchase_receipt",
			frm: this.frm,
			freeze_message: __("Creating Purchase Receipt ..."),
		});
	}

	make_purchase_invoice() {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.purchase_order.purchase_order.make_purchase_invoice",
			frm: this.frm,
		});
	}

	make_subcontracting_order() {
		frappe.model.open_mapped_doc({
			method: "erpnext.buying.doctype.purchase_order.purchase_order.make_subcontracting_order",
			frm: this.frm,
			freeze_message: __("Creating Subcontracting Order ..."),
		});
	}

	add_from_mappers() {
		var me = this;
		this.frm.add_custom_button(
			__("Material Request"),
			function () {
				erpnext.utils.map_current_doc({
					method: "erpnext.stock.doctype.material_request.material_request.make_purchase_order",
					source_doctype: "Material Request",
					target: me.frm,
					setters: {
						schedule_date: undefined,
					},
					get_query_filters: {
						material_request_type: "Purchase",
						docstatus: 1,
						status: ["!=", "Stopped"],
						per_ordered: ["<", 100],
						company: me.frm.doc.company,
					},
					allow_child_item_selection: true,
					child_fieldname: "items",
					child_columns: ["item_code", "qty", "ordered_qty"],
				});
			},
			__("Get Items From")
		);

		this.frm.add_custom_button(
			__("Supplier Quotation"),
			function () {
				erpnext.utils.map_current_doc({
					method: "erpnext.buying.doctype.supplier_quotation.supplier_quotation.make_purchase_order",
					source_doctype: "Supplier Quotation",
					target: me.frm,
					setters: {
						supplier: me.frm.doc.supplier,
						valid_till: undefined,
					},
					get_query_filters: {
						docstatus: 1,
						status: ["not in", ["Stopped", "Expired"]],
					},
				});
			},
			__("Get Items From")
		);

		this.frm.add_custom_button(
			__("Update Rate as per Last Purchase"),
			function () {
				frappe.call({
					method: "get_last_purchase_rate",
					doc: me.frm.doc,
					callback: function (r, rt) {
						me.frm.dirty();
						me.frm.cscript.calculate_taxes_and_totals();
					},
				});
			},
			__("Tools")
		);

		this.frm.add_custom_button(
			__("Link to Material Request"),
			function () {
				var my_items = [];
				for (var i in me.frm.doc.items) {
					if (!me.frm.doc.items[i].material_request) {
						my_items.push(me.frm.doc.items[i].item_code);
					}
				}
				frappe.call({
					method: "erpnext.buying.utils.get_linked_material_requests",
					args: {
						items: my_items,
					},
					callback: function (r) {
						if (r.exc) return;

						var i = 0;
						var item_length = me.frm.doc.items.length;
						while (i < item_length) {
							var qty = me.frm.doc.items[i].qty;
							(r.message[0] || []).forEach(function (d) {
								if (
									d.qty > 0 &&
									qty > 0 &&
									me.frm.doc.items[i].item_code == d.item_code &&
									!me.frm.doc.items[i].material_request_item
								) {
									me.frm.doc.items[i].material_request = d.mr_name;
									me.frm.doc.items[i].material_request_item = d.mr_item;
									var my_qty = Math.min(qty, d.qty);
									qty = qty - my_qty;
									d.qty = d.qty - my_qty;
									me.frm.doc.items[i].stock_qty =
										my_qty * me.frm.doc.items[i].conversion_factor;
									me.frm.doc.items[i].qty = my_qty;

									frappe.msgprint(
										"Assigning " +
											d.mr_name +
											" to " +
											d.item_code +
											" (row " +
											me.frm.doc.items[i].idx +
											")"
									);
									if (qty > 0) {
										frappe.msgprint("Splitting " + qty + " units of " + d.item_code);
										var new_row = frappe.model.add_child(
											me.frm.doc,
											me.frm.doc.items[i].doctype,
											"items"
										);
										item_length++;

										for (var key in me.frm.doc.items[i]) {
											new_row[key] = me.frm.doc.items[i][key];
										}

										new_row.idx = item_length;
										new_row["stock_qty"] = new_row.conversion_factor * qty;
										new_row["qty"] = qty;
										new_row["material_request"] = "";
										new_row["material_request_item"] = "";
									}
								}
							});
							i++;
						}
						refresh_field("items");
					},
				});
			},
			__("Tools")
		);
	}

	tc_name() {
		this.get_terms();
	}

	items_add(doc, cdt, cdn) {
		var row = frappe.get_doc(cdt, cdn);
		if (doc.schedule_date) {
			row.schedule_date = doc.schedule_date;
			refresh_field("schedule_date", cdn, "items");
		} else {
			this.frm.script_manager.copy_from_first_row("items", row, ["schedule_date"]);
		}
	}

	unhold_purchase_order() {
		this.frm.cscript.update_status("Resume", "Draft");
	}

	hold_purchase_order() {
		var me = this;
		var d = new frappe.ui.Dialog({
			title: __("Reason for Hold"),
			fields: [
				{
					fieldname: "reason_for_hold",
					fieldtype: "Text",
					reqd: 1,
				},
			],
			primary_action: function () {
				var data = d.get_values();
				let reason_for_hold = "Reason for hold: " + data.reason_for_hold;

				frappe.call({
					method: "frappe.desk.form.utils.add_comment",
					args: {
						reference_doctype: me.frm.doctype,
						reference_name: me.frm.docname,
						content: __(reason_for_hold),
						comment_email: frappe.session.user,
						comment_by: frappe.session.user_fullname,
					},
					callback: function (r) {
						if (!r.exc) {
							me.update_status("Hold", "On Hold");
							d.hide();
						}
					},
				});
			},
		});
		d.show();
	}

	unclose_purchase_order() {
		this.frm.cscript.update_status("Re-open", "Submitted");
	}

	close_purchase_order() {
		this.frm.cscript.update_status("Close", "Closed");
	}

	delivered_by_supplier() {
		this.frm.cscript.update_status("Deliver", "Delivered");
	}

	items_on_form_rendered() {
		set_schedule_date(this.frm);
	}
};

// for backward compatibility: combine new and previous states
extend_cscript(cur_frm.cscript, new erpnext.buying.PurchaseOrderController({ frm: cur_frm }));

cur_frm.cscript.update_status = function (label, status) {
	frappe.call({
		method: "erpnext.buying.doctype.purchase_order.purchase_order.update_status",
		args: { status: status, name: cur_frm.doc.name },
		callback: function (r) {
			cur_frm.set_value("status", status);
			cur_frm.reload_doc();
		},
	});
};

cur_frm.fields_dict["items"].grid.get_field("project").get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Project", "status", "not in", "Completed, Cancelled"]],
	};
};

if (cur_frm.doc.is_old_subcontracting_flow) {
	cur_frm.fields_dict["items"].grid.get_field("bom").get_query = function (doc, cdt, cdn) {
		var d = locals[cdt][cdn];
		return {
			filters: [
				["BOM", "item", "=", d.item_code],
				["BOM", "is_active", "=", "1"],
				["BOM", "docstatus", "=", "1"],
				["BOM", "company", "=", doc.company],
			],
		};
	};
}

function set_schedule_date(frm) {
	if (frm.doc.schedule_date) {
		erpnext.utils.copy_value_in_all_rows(
			frm.doc,
			frm.doc.doctype,
			frm.doc.name,
			"items",
			"schedule_date"
		);
	}
}

frappe.provide("erpnext.buying");

frappe.ui.form.on("Purchase Order", "is_subcontracted", function (frm) {
	if (frm.doc.is_old_subcontracting_flow) {
		erpnext.buying.get_default_bom(frm);
	}
});

function prevent_past_schedule_dates(frm) {
	if (frm.doc.transaction_date) {
		frm.fields_dict["schedule_date"].datepicker.update({
			minDate: new Date(frm.doc.transaction_date),
		});
	}
}

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Purchase Order Analysis` | Script Report | Buying |
| `Procurement Tracker` | Script Report | Buying |
| `Purchase Analytics` | Script Report | Buying |
| `Purchase Order Trends` | Script Report | Buying |
| `Item-wise Purchase History` | Script Report | Buying |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Purchase Orders to Bill` | Purchase Orders to Bill | Count | Buying |
| `Purchase Orders to Receive` | Purchase Orders to Receive | Count | Buying |
| `Annual Purchase` | Annual Purchase | Sum | Buying |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
