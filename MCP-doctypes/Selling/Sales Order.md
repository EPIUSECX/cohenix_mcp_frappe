# Master Control Plan: `Sales Order`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Maintenance User | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sales Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `column_break0` | None | Column Break | None |  |  |  | None | None |
| `naming_series` | Series | Select | SAL-ORD-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer | ✅ |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `tax_id` | Tax Id | Data | None |  |  | ✅ | None | None |
| `order_type` | Order Type | Select | 
Sales
Maintenance
Shopping Cart | ✅ |  |  | Sales | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `transaction_date` | Date | Date | None | ✅ |  |  | Today | None |
| `delivery_date` | Delivery Date | Date | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `po_no` | Customer's Purchase Order | Data | None |  |  |  | None | None |
| `po_date` | Customer's Purchase Order Date | Date | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `skip_delivery_note` | Skip Delivery Note | Check | None |  | ✅ |  | 0 | None |
| `has_unit_price_items` | Has Unit Price Items | Check | None |  | ✅ |  | 0 | None |
| `amended_from` | Amended From | Link | Sales Order |  | ✅ | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which customer's currency is converted to company's base currency |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Price list currency is converted to company's base currency |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `sec_warehouse` | Items | Section Break | None |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Set Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `reserve_stock` | Reserve Stock | Check | None |  |  |  | 0 | If checked, Stock will be reserved on <b>Submit</b> |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Sales Order Item | ✅ |  |  | None | None |
| `section_break_31` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_33a` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `taxes_section` | Taxes | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Sales Taxes and Charges Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_49` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_40` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Sales Taxes and Charges | Table | Sales Taxes and Charges |  |  |  | None | None |
| `section_break_43` | None | Section Break | None |  |  |  | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_46` | None | Column Break | None |  |  |  | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `totals` | Totals | Section Break | fa fa-money |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | In Words will be visible once you save the Sales Order. |
| `column_break3` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `advance_paid` | Advance Paid | Currency | party_account_currency |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `section_break_48` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `coupon_code` | Coupon Code | Link | Coupon Code |  |  |  | None | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `packing_list` | Packing List | Section Break | fa fa-suitcase |  |  |  | None | None |
| `packed_items` | Packed Items | Table | Packed Item |  |  |  | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `contact_info` | Address & Contact | Tab Break | fa fa-bullhorn |  |  |  | None | None |
| `billing_address_column` | Billing Address | Section Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  | ✅ |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `column_break_84` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_phone` | Phone | Data | Phone |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `shipping_address_column` | Shipping Address | Section Break | None |  |  |  | None | None |
| `shipping_address_name` | Shipping Address Name | Link | Address |  |  |  | None | None |
| `shipping_address` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_93` | None | Column Break | None |  |  |  | None | None |
| `dispatch_address_name` | Dispatch Address Name | Link | Address |  |  |  | None | None |
| `dispatch_address` | Dispatch Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break46` | Company Address | Section Break | None |  |  |  | None | None |
| `company_address` | Company Address Name | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_92` | None | Column Break | None |  |  |  | None | None |
| `company_contact_person` | Company Contact Person | Link | Contact |  |  |  | None | None |
| `payment_schedule_section` | Terms | Tab Break | None |  |  |  | None | None |
| `payment_terms_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `terms_section_break` | Terms & Conditions | Section Break | fa fa-legal |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions Details | Text Editor | None |  |  |  | None | None |
| `more_info` | More Info | Tab Break | fa fa-file-text |  |  |  | None | None |
| `section_break_78` | Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
On Hold
To Pay
To Deliver and Bill
To Bill
To Deliver
Completed
Cancelled
Closed | ✅ |  | ✅ | Draft | None |
| `delivery_status` | Delivery Status | Select | Not Delivered
Fully Delivered
Partly Delivered
Closed
Not Applicable |  | ✅ |  | None | None |
| `per_delivered` | %  Delivered | Percent | None |  |  | ✅ | None | % of materials delivered against this Sales Order |
| `column_break_81` | None | Column Break | None |  |  |  | None | None |
| `per_billed` | % Amount Billed | Percent | None |  |  | ✅ | None | % of materials billed against this Sales Order |
| `per_picked` | % Picked | Percent | None |  |  | ✅ | None | None |
| `billing_status` | Billing Status | Select | Not Billed
Fully Billed
Partly Billed
Closed |  | ✅ |  | None | None |
| `advance_payment_status` | Advance Payment Status | Select | Not Requested
Requested
Partially Paid
Fully Paid |  | ✅ |  | None | None |
| `sales_team_section_break` | Commission | Section Break | fa fa-group |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `column_break7` | None | Column Break | None |  |  |  | None | None |
| `amount_eligible_for_commission` | Amount Eligible for Commission | Currency | None |  |  | ✅ | None | None |
| `commission_rate` | Commission Rate | Float | None |  |  |  | None | None |
| `total_commission` | Total Commission | Currency | Company:company:default_currency |  |  |  | None | None |
| `section_break1` | Sales Team | Section Break | None |  |  |  | None | None |
| `sales_team` | Sales Team | Table | Sales Team |  |  |  | None | None |
| `loyalty_points_redemption` | Loyalty Points | Section Break | None |  | ✅ |  | None | None |
| `loyalty_points` | Loyalty Points | Int | None |  | ✅ | ✅ | None | None |
| `column_break_116` | None | Column Break | None |  |  |  | None | None |
| `loyalty_amount` | Loyalty Amount | Currency | None |  | ✅ | ✅ | None | None |
| `subscription_section` | Auto Repeat | Section Break | None |  |  | ✅ | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `column_break_108` | None | Column Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  |  | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `printing_details` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break4` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  | ✅ | None | None |
| `additional_info_section` | Additional Info | Section Break | None |  |  |  | None | None |
| `is_internal_customer` | Is Internal Customer | Check | None |  |  | ✅ | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | None |
| `column_break_yvzv` | None | Column Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `column_break_152` | None | Column Break | None |  |  |  | None | None |
| `inter_company_order_reference` | Inter Company Order Reference | Link | Purchase Order |  |  | ✅ | None | None |
| `party_account_currency` | Party Account Currency | Link | Currency |  | ✅ | ✅ | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 35
- **Dynamic Link Fields:** 0
- **Table Fields:** 6

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/sales_order/sales_order.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.cscript.tax_table = "Sales Taxes and Charges";

erpnext.accounts.taxes.setup_tax_filters("Sales Taxes and Charges");
erpnext.accounts.taxes.setup_tax_validations("Sales Order");
erpnext.sales_common.setup_selling_controller();

frappe.ui.form.on("Sales Order", {
	setup: function (frm) {
		frm.custom_make_buttons = {
			"Delivery Note": "Delivery Note",
			"Pick List": "Pick List",
			"Sales Invoice": "Sales Invoice",
			"Material Request": "Material Request",
			"Purchase Order": "Purchase Order",
			Project: "Project",
			"Payment Entry": "Payment",
			"Work Order": "Work Order",
		};
		frm.add_fetch("customer", "tax_id", "tax_id");

		// formatter for material request item
		frm.set_indicator_formatter("item_code", function (doc) {
			let color;
			if (!doc.qty && frm.doc.has_unit_price_items) {
				color = "yellow";
			} else if (doc.stock_qty <= doc.delivered_qty) {
				color = "green";
			} else {
				color = "orange";
			}

			return color;
		});

		frm.set_query("bom_no", "items", function (doc, cdt, cdn) {
			var row = locals[cdt][cdn];
			return {
				filters: {
					item: row.item_code,
				},
			};
		});

		frm.set_df_property("packed_items", "cannot_add_rows", true);
		frm.set_df_property("packed_items", "cannot_delete_rows", true);
	},

	refresh: function (frm) {
		if (frm.doc.docstatus === 1) {
			if (
				frm.doc.status !== "Closed" &&
				flt(frm.doc.per_delivered) < 100 &&
				flt(frm.doc.per_billed) < 100 &&
				frm.has_perm("write")
			) {
				frm.add_custom_button(__("Update Items"), () => {
					erpnext.utils.update_child_items({
						frm: frm,
						child_docname: "items",
						child_doctype: "Sales Order Detail",
						cannot_add_row: false,
						has_reserved_stock: frm.doc.__onload && frm.doc.__onload.has_reserved_stock,
					});
				});

				// Stock Reservation > Reserve button should only be visible if the SO has unreserved stock and no Pick List is created against the SO.
				if (
					frm.doc.__onload &&
					frm.doc.__onload.has_unreserved_stock &&
					flt(frm.doc.per_picked) === 0
				) {
					frm.add_custom_button(
						__("Reserve"),
						() => frm.events.create_stock_reservation_entries(frm),
						__("Stock Reservation")
					);
				}
			}

			// Stock Reservation > Unreserve button will be only visible if the SO has un-delivered reserved stock.
			if (
				frm.doc.__onload &&
				frm.doc.__onload.has_reserved_stock &&
				frappe.model.can_cancel("Stock Reservation Entry")
			) {
				frm.add_custom_button(
					__("Unreserve"),
					() => frm.events.cancel_stock_reservation_entries(frm),
					__("Stock Reservation")
				);
			}

			frm.doc.items.forEach((item) => {
				if (flt(item.stock_reserved_qty) > 0 && frappe.model.can_read("Stock Reservation Entry")) {
					frm.add_custom_button(
						__("Reserved Stock"),
						() => frm.events.show_reserved_stock(frm),
						__("Stock Reservation")
					);
					return;
				}
			});
		}

		if (frm.doc.docstatus === 0) {
			erpnext.set_unit_price_items_note(frm);

			if (frm.doc.is_internal_customer) {
				frm.events.get_items_from_internal_purchase_order(frm);
			}

			if (frm.doc.docstatus === 0) {
				frappe.call({
					method: "erpnext.selling.doctype.sales_order.sales_order.get_stock_reservation_status",
					callback: function (r) {
						if (!r.message) {
							frm.set_value("reserve_stock", 0);
							frm.set_df_property("reserve_stock", "read_only", 1);
							frm.set_df_property("reserve_stock", "hidden", 1);
							frm.fields_dict.items.grid.update_docfield_property("reserve_stock", "hidden", 1);
							frm.fields_dict.items.grid.update_docfield_property(
								"reserve_stock",
								"default",
								0
							);
							frm.fields_dict.items.grid.update_docfield_property(
								"reserve_stock",
								"read_only",
								1
							);
						}
					},
				});
			}
		}

		// Hide `Reserve Stock` field description in submitted or cancelled Sales Order.
		if (frm.doc.docstatus > 0) {
			frm.set_df_property("reserve_stock", "description", null);
		}
	},

	get_items_from_internal_purchase_order(frm) {
		if (!frappe.model.can_read("Purchase Order")) {
			return;
		}

		frm.add_custom_button(
			__("Purchase Order"),
			() => {
				erpnext.utils.map_current_doc({
					method: "erpnext.buying.doctype.purchase_order.purchase_order.make_inter_company_sales_order",
					source_doctype: "Purchase Order",
					target: frm,
					setters: [
						{
							label: __("Supplier"),
							fieldname: "supplier",
							fieldtype: "Link",
							options: "Supplier",
						},
					],
					get_query_filters: {
						company: frm.doc.company,
						is_internal_supplier: 1,
						docstatus: 1,
						status: ["!=", "Completed"],
					},
				});
			},
			__("Get Items From")
		);
	},

	onload: function (frm) {
		if (!frm.doc.transaction_date) {
			frm.set_value("transaction_date", frappe.datetime.get_today());
		}
		erpnext.queries.setup_queries(frm, "Warehouse", function () {
			return {
				filters: [
					["Warehouse", "company", "in", ["", cstr(frm.doc.company)]],
					["Warehouse", "is_group", "=", 0],
				],
			};
		});

		frm.set_query("warehouse", "items", function (doc, cdt, cdn) {
			let row = locals[cdt][cdn];
			let query = {
				filters: [
					["Warehouse", "company", "in", ["", cstr(frm.doc.company)]],
					["Warehouse", "is_group", "=", 0],
				],
			};
			if (row.item_code) {
				query.query = "erpnext.controllers.queries.warehouse_query";
				query.filters.push(["Bin", "item_code", "=", row.item_code]);
			}
			return query;
		});

		// On cancel and amending a sales order with advance payment, reset advance paid amount
		if (frm.is_new()) {
			frm.set_value("advance_paid", 0);
		}

		frm.ignore_doctypes_on_cancel_all = [
			"Purchase Order",
			"Unreconcile Payment",
			"Unreconcile Payment Entries",
		];
	},

	delivery_date: function (frm) {
		$.each(frm.doc.items || [], function (i, d) {
			if (!d.delivery_date) d.delivery_date = frm.doc.delivery_date;
		});
		refresh_field("items");
	},

	create_stock_reservation_entries(frm) {
		const dialog = new frappe.ui.Dialog({
			title: __("Stock Reservation"),
			size: "extra-large",
			fields: [
				{
					fieldname: "set_warehouse",
					fieldtype: "Link",
					label: __("Set Warehouse"),
					options: "Warehouse",
					default: frm.doc.set_warehouse,
					get_query: () => {
						return {
							filters: [["Warehouse", "is_group", "!=", 1]],
						};
					},
					onchange: () => {
						if (dialog.get_value("set_warehouse")) {
							dialog.fields_dict.items.df.data.forEach((row) => {
								row.warehouse = dialog.get_value("set_warehouse");
							});
							dialog.fields_dict.items.grid.refresh();
						}
					},
				},
				{ fieldtype: "Column Break" },
				{
					fieldname: "add_item",
					fieldtype: "Link",
					label: __("Add Item"),
					options: "Sales Order Item",
					get_query: () => {
						return {
							query: "erpnext.controllers.queries.get_filtered_child_rows",
							filters: {
								parenttype: frm.doc.doctype,
								parent: frm.doc.name,
								reserve_stock: 1,
							},
						};
					},
					onchange: () => {
						let sales_order_item = dialog.get_value("add_item");

						if (sales_order_item) {
							frm.doc.items.forEach((item) => {
								if (item.name === sales_order_item) {
									let unreserved_qty =
										(flt(item.stock_qty) -
											(item.stock_reserved_qty
												? flt(item.stock_reserved_qty)
												: flt(item.delivered_qty) * flt(item.conversion_factor))) /
										flt(item.conversion_factor);

									if (unreserved_qty > 0) {
										dialog.fields_dict.items.df.data.forEach((row) => {
											if (row.sales_order_item === sales_order_item) {
												unreserved_qty -= row.qty_to_reserve;
											}
										});
									}

									dialog.fields_dict.items.df.data.push({
										sales_order_item: item.name,
										item_code: item.item_code,
										warehouse: dialog.get_value("set_warehouse") || item.warehouse,
										qty_to_reserve: Math.max(unreserved_qty, 0),
									});
									dialog.fields_dict.items.grid.refresh();
									dialog.set_value("add_item", undefined);
								}
							});
						}
					},
				},
				{ fieldtype: "Section Break" },
				{
					fieldname: "items",
					fieldtype: "Table",
					label: __("Items to Reserve"),
					allow_bulk_edit: false,
					cannot_add_rows: true,
					cannot_delete_rows: true,
					data: [],
					fields: [
						{
							fieldname: "sales_order_item",
							fieldtype: "Link",
							label: __("Sales Order Item"),
							options: "Sales Order Item",
							reqd: 1,
							in_list_view: 1,
							get_query: () => {
								return {
									query: "erpnext.controllers.queries.get_filtered_child_rows",
									filters: {
										parenttype: frm.doc.doctype,
										parent: frm.doc.name,
										reserve_stock: 1,
									},
								};
							},
							onchange: (event) => {
								if (event) {
									let name = $(event.currentTarget).closest(".grid-row").attr("data-name");
									let item_row =
										dialog.fields_dict.items.grid.grid_rows_by_docname[name].doc;

									frm.doc.items.forEach((item) => {
										if (item.name === item_row.sales_order_item) {
											item_row.item_code = item.item_code;
										}
									});
									dialog.fields_dict.items.grid.refresh();
								}
							},
						},
						{
							fieldname: "item_code",
							fieldtype: "Link",
							label: __("Item Code"),
							options: "Item",
							reqd: 1,
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldname: "warehouse",
							fieldtype: "Link",
							label: __("Warehouse"),
							options: "Warehouse",
							reqd: 1,
							in_list_view: 1,
							get_query: () => {
								return {
									filters: [["Warehouse", "is_group", "!=", 1]],
								};
							},
						},
						{
							fieldname: "qty_to_reserve",
							fieldtype: "Float",
							label: __("Qty"),
							reqd: 1,
							in_list_view: 1,
						},
					],
				},
			],
			primary_action_label: __("Reserve Stock"),
			primary_action: () => {
				var data = { items: dialog.fields_dict.items.grid.get_selected_children() };

				if (data.items && data.items.length > 0) {
					frappe.call({
						doc: frm.doc,
						method: "create_stock_reservation_entries",
						args: {
							items_details: data.items,
							notify: true,
						},
						freeze: true,
						freeze_message: __("Reserving Stock..."),
						callback: (r) => {
							frm.doc.__onload.has_unreserved_stock = false;
							frm.reload_doc();
						},
					});

					dialog.hide();
				} else {
					frappe.msgprint(__("Please select items to reserve."));
				}
			},
		});

		frm.doc.items.forEach((item) => {
			if (item.reserve_stock) {
				let unreserved_qty =
					(flt(item.stock_qty) -
						(item.stock_reserved_qty
							? flt(item.stock_reserved_qty)
							: flt(item.delivered_qty) * flt(item.conversion_factor))) /
					flt(item.conversion_factor);

				if (unreserved_qty > 0) {
					dialog.fields_dict.items.df.data.push({
						__checked: 1,
						sales_order_item: item.name,
						item_code: item.item_code,
						warehouse: item.warehouse,
						qty_to_reserve: unreserved_qty,
					});
				}
			}
		});

		dialog.fields_dict.items.grid.refresh();
		dialog.show();
	},

	cancel_stock_reservation_entries(frm) {
		const dialog = new frappe.ui.Dialog({
			title: __("Stock Unreservation"),
			size: "extra-large",
			fields: [
				{
					fieldname: "sr_entries",
					fieldtype: "Table",
					label: __("Reserved Stock"),
					allow_bulk_edit: false,
					cannot_add_rows: true,
					cannot_delete_rows: true,
					in_place_edit: true,
					data: [],
					fields: [
						{
							fieldname: "sre",
							fieldtype: "Link",
							label: __("Stock Reservation Entry"),
							options: "Stock Reservation Entry",
							reqd: 1,
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldname: "item_code",
							fieldtype: "Link",
							label: __("Item Code"),
							options: "Item",
							reqd: 1,
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldname: "warehouse",
							fieldtype: "Link",
							label: __("Warehouse"),
							options: "Warehouse",
							reqd: 1,
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldname: "qty",
							fieldtype: "Float",
							label: __("Qty"),
							reqd: 1,
							read_only: 1,
							in_list_view: 1,
						},
					],
				},
			],
			primary_action_label: __("Unreserve Stock"),
			primary_action: () => {
				var data = { sr_entries: dialog.fields_dict.sr_entries.grid.get_selected_children() };

				if (data.sr_entries && data.sr_entries.length > 0) {
					frappe.call({
						doc: frm.doc,
						method: "cancel_stock_reservation_entries",
						args: {
							sre_list: data.sr_entries.map((item) => item.sre),
						},
						freeze: true,
						freeze_message: __("Unreserving Stock..."),
						callback: (r) => {
							frm.doc.__onload.has_reserved_stock = false;
							frm.reload_doc();
						},
					});

					dialog.hide();
				} else {
					frappe.msgprint(__("Please select items to unreserve."));
				}
			},
		});

		frappe
			.call({
				method: "erpnext.stock.doctype.stock_reservation_entry.stock_reservation_entry.get_stock_reservation_entries_for_voucher",
				args: {
					voucher_type: frm.doctype,
					voucher_no: frm.docname,
				},
				callback: (r) => {
					if (!r.exc && r.message) {
						r.message.forEach((sre) => {
							if (flt(sre.reserved_qty) > flt(sre.delivered_qty)) {
								dialog.fields_dict.sr_entries.df.data.push({
									sre: sre.name,
									item_code: sre.item_code,
									warehouse: sre.warehouse,
									qty: flt(sre.reserved_qty) - flt(sre.delivered_qty),
								});
							}
						});
					}
				},
			})
			.then((r) => {
				dialog.fields_dict.sr_entries.grid.refresh();
				dialog.show();
			});
	},

	show_reserved_stock(frm) {
		// Get the latest modified date from the items table.
		var to_date = moment(new Date(Math.max(...frm.doc.items.map((e) => new Date(e.modified))))).format(
			"YYYY-MM-DD"
		);

		frappe.route_options = {
			company: frm.doc.company,
			from_date: frm.doc.transaction_date,
			to_date: to_date,
			voucher_type: frm.doc.doctype,
			voucher_no: frm.doc.name,
		};
		frappe.set_route("query-report", "Reserved Stock");
	},
});

frappe.ui.form.on("Sales Order Item", {
	item_code: function (frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (frm.doc.delivery_date) {
			row.delivery_date = frm.doc.delivery_date;
			refresh_field("delivery_date", cdn, "items");
		} else {
			frm.script_manager.copy_from_first_row("items", row, ["delivery_date"]);
		}
	},
	delivery_date: function (frm, cdt, cdn) {
		if (!frm.doc.delivery_date) {
			erpnext.utils.copy_value_in_all_rows(frm.doc, cdt, cdn, "items", "delivery_date");
		}
	},
});

erpnext.selling.SalesOrderController = class SalesOrderController extends erpnext.selling.SellingController {
	onload(doc, dt, dn) {
		super.onload(doc, dt, dn);
	}

	refresh(doc, dt, dn) {
		var me = this;
		super.refresh();
		let allow_delivery = false;

		if (doc.docstatus == 1) {
			if (this.frm.has_perm("submit")) {
				if (doc.status === "On Hold") {
					// un-hold
					this.frm.add_custom_button(
						__("Resume"),
						function () {
							me.frm.cscript.update_status("Resume", "Draft");
						},
						__("Status")
					);

					if (flt(doc.per_delivered) < 100 || flt(doc.per_billed) < 100) {
						// close
						this.frm.add_custom_button(__("Close"), () => this.close_sales_order(), __("Status"));
					}
				} else if (doc.status === "Closed") {
					// un-close
					this.frm.add_custom_button(
						__("Re-open"),
						function () {
							me.frm.cscript.update_status("Re-open", "Draft");
						},
						__("Status")
					);
				}
			}
			if (doc.status !== "Closed") {
				if (doc.status !== "On Hold") {
					const items_are_deliverable = this.frm.doc.items.some(
						(item) => item.delivered_by_supplier === 0 && item.qty > flt(item.delivered_qty)
					);
					allow_delivery =
						(this.frm.doc.has_unit_price_items || items_are_deliverable) &&
						!this.frm.doc.skip_delivery_note;

					if (this.frm.has_perm("submit")) {
						if (flt(doc.per_delivered) < 100 || flt(doc.per_billed) < 100) {
							// hold
							this.frm.add_custom_button(
								__("Hold"),
								() => this.hold_sales_order(),
								__("Status")
							);
							// close
							this.frm.add_custom_button(
								__("Close"),
								() => this.close_sales_order(),
								__("Status")
							);
						}
					}

					if (
						(!doc.__onload || !doc.__onload.has_reserved_stock) &&
						flt(doc.per_picked) < 100 &&
						flt(doc.per_delivered) < 100 &&
						frappe.model.can_create("Pick List")
					) {
						this.frm.add_custom_button(
							__("Pick List"),
							() => this.create_pick_list(),
							__("Create")
						);
					}

					const order_is_a_sale = ["Sales", "Shopping Cart"].indexOf(doc.order_type) !== -1;
					const order_is_maintenance = ["Maintenance"].indexOf(doc.order_type) !== -1;
					// order type has been customised then show all the action buttons
					const order_is_a_custom_sale =
						["Sales", "Shopping Cart", "Maintenance"].indexOf(doc.order_type) === -1;

					// delivery note
					if (
						flt(doc.per_delivered) < 100 &&
						(order_is_a_sale || order_is_a_custom_sale) &&
						allow_delivery
					) {
						if (frappe.model.can_create("Delivery Note")) {
							this.frm.add_custom_button(
								__("Delivery Note"),
								() => this.make_delivery_note_based_on_delivery_date(true),
								__("Create")
							);
						}

						if (frappe.model.can_create("Work Order")) {
							this.frm.add_custom_button(
								__("Work Order"),
								() => this.make_work_order(),
								__("Create")
							);
						}
					}

					// sales invoice
					if (flt(doc.per_billed) < 100 && frappe.model.can_create("Sales Invoice")) {
						this.frm.add_custom_button(
							__("Sales Invoice"),
							() => me.make_sales_invoice(),
							__("Create")
						);
					}

					// material request
					if (
						(!doc.order_type ||
							((order_is_a_sale || order_is_a_custom_sale) && flt(doc.per_delivered) < 100)) &&
						frappe.model.can_create("Material Request")
					) {
						this.frm.add_custom_button(
							__("Material Request"),
							() => this.make_material_request(),
							__("Create")
						);
						this.frm.add_custom_button(
							__("Request for Raw Materials"),
							() => this.make_raw_material_request(),
							__("Create")
						);
					}

					// Make Purchase Order
					if (!this.frm.doc.is_internal_customer && frappe.model.can_create("Purchase Order")) {
						this.frm.add_custom_button(
							__("Purchase Order"),
							() => this.make_purchase_order(),
							__("Create")
						);
					}

					// maintenance
					if (flt(doc.per_delivered) < 100 && (order_is_maintenance || order_is_a_custom_sale)) {
						if (frappe.model.can_create("Maintenance Visit")) {
							this.frm.add_custom_button(
								__("Maintenance Visit"),
								() => this.make_maintenance_visit(),
								__("Create")
							);
						}
						if (frappe.model.can_create("Maintenance Schedule")) {
							this.frm.add_custom_button(
								__("Maintenance Schedule"),
								() => this.make_maintenance_schedule(),
								__("Create")
							);
						}
					}

					// project
					if (flt(doc.per_delivered) < 100 && frappe.model.can_create("Project")) {
						this.frm.add_custom_button(__("Project"), () => this.make_project(), __("Create"));
					}

					if (
						doc.docstatus === 1 &&
						!doc.inter_company_order_reference &&
						frappe.model.can_create("Purchase Order")
					) {
						let me = this;
						let internal = me.frm.doc.is_internal_customer;
						if (internal) {
							let button_label =
								me.frm.doc.company === me.frm.doc.represents_company
									? "Internal Purchase Order"
									: "Inter Company Purchase Order";

							me.frm.add_custom_button(
								button_label,
								function () {
									me.make_inter_company_order();
								},
								__("Create")
							);
						}
					}
				}
				// payment request
				if (flt(doc.per_billed) < 100 + frappe.boot.sysdefaults.over_billing_allowance) {
					this.frm.add_custom_button(
						__("Payment Request"),
						() => this.make_payment_request(),
						__("Create")
					);

					if (frappe.model.can_create("Payment Entry")) {
						this.frm.add_custom_button(
							__("Payment"),
							() => this.make_payment_entry(),
							__("Create")
						);
					}
				}
				this.frm.page.set_inner_btn_group_as_primary(__("Create"));
			}
		}

		if (this.frm.doc.docstatus === 0 && frappe.model.can_read("Quotation")) {
			this.frm.add_custom_button(
				__("Quotation"),
				function () {
					let d = erpnext.utils.map_current_doc({
						method: "erpnext.selling.doctype.quotation.quotation.make_sales_order",
						source_doctype: "Quotation",
						target: me.frm,
						setters: [
							{
								label: __("Customer"),
								fieldname: "party_name",
								fieldtype: "Link",
								options: "Customer",
								default: me.frm.doc.customer || undefined,
							},
						],
						get_query_filters: {
							company: me.frm.doc.company,
							docstatus: 1,
							status: ["!=", "Lost"],
						},
					});
				},
				__("Get Items From")
			);
		}

		this.order_type(doc);
	}

	create_pick_list() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.create_pick_list",
			frm: this.frm,
		});
	}

	make_work_order() {
		var me = this;
		me.frm.call({
			method: "erpnext.selling.doctype.sales_order.sales_order.get_work_order_items",
			args: {
				sales_order: this.frm.docname,
			},
			freeze: true,
			callback: function (r) {
				if (!r.message) {
					frappe.msgprint({
						title: __("Work Order not created"),
						message: __("No Items with Bill of Materials to Manufacture"),
						indicator: "orange",
					});
					return;
				} else {
					const fields = [
						{
							label: __("Items"),
							fieldtype: "Table",
							fieldname: "items",
							description: __("Select BOM and Qty for Production"),
							fields: [
								{
									fieldtype: "Read Only",
									fieldname: "item_code",
									label: __("Item Code"),
									in_list_view: 1,
								},
								{
									fieldtype: "Read Only",
									fieldname: "item_name",
									label: __("Item Name"),
									in_list_view: 1,
								},
								{
									fieldtype: "Link",
									fieldname: "bom",
									options: "BOM",
									reqd: 1,
									label: __("Select BOM"),
									in_list_view: 1,
									get_query: function (doc) {
										return { filters: { item: doc.item_code } };
									},
								},
								{
									fieldtype: "Float",
									fieldname: "pending_qty",
									reqd: 1,
									label: __("Qty"),
									in_list_view: 1,
								},
								{
									fieldtype: "Data",
									fieldname: "sales_order_item",
									reqd: 1,
									label: __("Sales Order Item"),
									hidden: 1,
								},
							],
							data: r.message,
							get_data: () => {
								return r.message;
							},
						},
					];
					var d = new frappe.ui.Dialog({
						title: __("Select Items to Manufacture"),
						fields: fields,
						primary_action: function () {
							var data = { items: d.fields_dict.items.grid.get_selected_children() };
							if (!data.items.length) {
								frappe.throw(__("Please select atleast one item to continue"));
							}
							me.frm.call({
								method: "make_work_orders",
								args: {
									items: data,
									company: me.frm.doc.company,
									sales_order: me.frm.docname,
									project: me.frm.project,
								},
								freeze: true,
								callback: function (r) {
									if (r.message) {
										frappe.msgprint({
											message: __("Work Orders Created: {0}", [
												r.message
													.map(function (d) {
														return repl(
															'<a href="/app/work-order/%(name)s">%(name)s</a>',
															{ name: d }
														);
													})
													.join(", "),
											]),
											indicator: "green",
										});
									}
									d.hide();
								},
							});
						},
						primary_action_label: __("Create"),
					});
					d.show();
				}
			},
		});
	}

	order_type() {
		this.toggle_delivery_date();
	}

	tc_name() {
		this.get_terms();
	}

	make_material_request() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_material_request",
			frm: this.frm,
		});
	}

	skip_delivery_note() {
		this.toggle_delivery_date();
	}

	toggle_delivery_date() {
		this.frm.fields_dict.items.grid.toggle_reqd(
			"delivery_date",
			this.frm.doc.order_type == "Sales" && !this.frm.doc.skip_delivery_note
		);
	}

	make_raw_material_request() {
		var me = this;
		this.frm.call({
			method: "erpnext.selling.doctype.sales_order.sales_order.get_work_order_items",
			args: {
				sales_order: this.frm.docname,
				for_raw_material_request: 1,
			},
			callback: function (r) {
				if (!r.message) {
					frappe.msgprint({
						message: __("No Items with Bill of Materials."),
						indicator: "orange",
					});
					return;
				} else {
					me.make_raw_material_request_dialog(r);
				}
			},
		});
	}

	make_raw_material_request_dialog(r) {
		var me = this;
		var fields = [
			{ fieldtype: "Check", fieldname: "include_exploded_items", label: __("Include Exploded Items") },
			{
				fieldtype: "Check",
				fieldname: "ignore_existing_ordered_qty",
				label: __("Ignore Existing Ordered Qty"),
			},
			{
				fieldtype: "Table",
				fieldname: "items",
				description: __("Select BOM, Qty and For Warehouse"),
				fields: [
					{
						fieldtype: "Read Only",
						fieldname: "item_code",
						label: __("Item Code"),
						in_list_view: 1,
					},
					{
						fieldtype: "Link",
						fieldname: "warehouse",
						options: "Warehouse",
						label: __("For Warehouse"),
						in_list_view: 1,
					},
					{
						fieldtype: "Link",
						fieldname: "bom",
						options: "BOM",
						reqd: 1,
						label: __("BOM"),
						in_list_view: 1,
						get_query: function (doc) {
							return { filters: { item: doc.item_code } };
						},
					},
					{
						fieldtype: "Float",
						fieldname: "required_qty",
						reqd: 1,
						label: __("Qty"),
						in_list_view: 1,
					},
				],
				data: r.message,
				get_data: function () {
					return r.message;
				},
			},
		];
		var d = new frappe.ui.Dialog({
			title: __("Items for Raw Material Request"),
			fields: fields,
			primary_action: function () {
				var data = d.get_values();
				me.frm.call({
					method: "erpnext.selling.doctype.sales_order.sales_order.make_raw_material_request",
					args: {
						items: data,
						company: me.frm.doc.company,
						sales_order: me.frm.docname,
						project: me.frm.doc.project,
					},
					freeze: true,
					callback: function (r) {
						if (r.message) {
							frappe.msgprint(
								__("Material Request {0} submitted.", [
									'<a href="/app/material-request/' +
										r.message.name +
										'">' +
										r.message.name +
										"</a>",
								])
							);
						}
						d.hide();
						me.frm.reload_doc();
					},
				});
			},
			primary_action_label: __("Create"),
		});
		d.show();
	}

	make_delivery_note_based_on_delivery_date(for_reserved_stock = false) {
		var me = this;

		var delivery_dates = this.frm.doc.items.map((i) => i.delivery_date);
		delivery_dates = [...new Set(delivery_dates)];

		var today = new Date();

		var item_grid = this.frm.fields_dict["items"].grid;
		if (!item_grid.get_selected().length && delivery_dates.length > 1) {
			var dialog = new frappe.ui.Dialog({
				title: __("Select Items based on Delivery Date"),
				fields: [{ fieldtype: "HTML", fieldname: "dates_html" }],
			});

			var html = $(`
				<div style="border: 1px solid #d1d8dd">
					<div class="list-item list-item--head">
						<div class="list-item__content list-item__content--flex-2">
							${__("Delivery Date")}
						</div>
					</div>
					${delivery_dates
						.map(
							(date) => `
						<div class="list-item">
							<div class="list-item__content list-item__content--flex-2">
								<label>
								<input
									type="checkbox"
									data-date="${date}"
									${frappe.datetime.get_day_diff(new Date(date), today) > 0 ? "" : 'checked="checked"'}
								/>
								${frappe.datetime.str_to_user(date)}
								</label>
							</div>
						</div>
					`
						)
						.join("")}
				</div>
			`);

			var wrapper = dialog.fields_dict.dates_html.$wrapper;
			wrapper.html(html);

			dialog.set_primary_action(__("Select"), function () {
				var dates = wrapper
					.find("input[type=checkbox]:checked")
					.map((i, el) => $(el).attr("data-date"))
					.toArray();

				if (!dates) return;

				me.make_delivery_note(dates, for_reserved_stock);
				dialog.hide();
			});
			dialog.show();
		} else {
			this.make_delivery_note([], for_reserved_stock);
		}
	}

	make_delivery_note(delivery_dates, for_reserved_stock = false) {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_delivery_note",
			frm: this.frm,
			args: {
				delivery_dates,
				for_reserved_stock: for_reserved_stock,
			},
			freeze: true,
			freeze_message: __("Creating Delivery Note ..."),
		});
	}

	make_sales_invoice() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_sales_invoice",
			frm: this.frm,
		});
	}

	make_maintenance_schedule() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_maintenance_schedule",
			frm: this.frm,
		});
	}

	make_project() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_project",
			frm: this.frm,
		});
	}

	make_inter_company_order() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_inter_company_purchase_order",
			frm: this.frm,
		});
	}

	make_maintenance_visit() {
		frappe.model.open_mapped_doc({
			method: "erpnext.selling.doctype.sales_order.sales_order.make_maintenance_visit",
			frm: this.frm,
		});
	}

	make_purchase_order() {
		let pending_items = this.frm.doc.items.some((item) => {
			let pending_qty = flt(item.stock_qty) - flt(item.ordered_qty);
			return pending_qty > 0;
		});
		if (!pending_items) {
			frappe.throw({
				message: __("Purchase Order already created for all Sales Order items"),
				title: __("Note"),
			});
		}

		var me = this;
		var dialog = new frappe.ui.Dialog({
			title: __("Select Items"),
			size: "large",
			fields: [
				{
					fieldtype: "Check",
					label: __("Against Default Supplier"),
					fieldname: "against_default_supplier",
					default: 0,
				},
				{
					fieldname: "items_for_po",
					fieldtype: "Table",
					label: __("Select Items"),
					fields: [
						{
							fieldtype: "Data",
							fieldname: "item_code",
							label: __("Item"),
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldtype: "Data",
							fieldname: "item_name",
							label: __("Item name"),
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldtype: "Float",
							fieldname: "pending_qty",
							label: __("Pending Qty"),
							read_only: 1,
							in_list_view: 1,
						},
						{
							fieldtype: "Link",
							read_only: 1,
							fieldname: "uom",
							label: __("UOM"),
							in_list_view: 1,
						},
						{
							fieldtype: "Data",
							fieldname: "supplier",
							label: __("Supplier"),
							read_only: 1,
							in_list_view: 1,
						},
					],
				},
			],
			primary_action_label: __("Create Purchase Order"),
			primary_action(args) {
				if (!args) return;

				let selected_items = dialog.fields_dict.items_for_po.grid.get_selected_children();
				if (selected_items.length == 0) {
					frappe.throw({
						message: "Please select Items from the Table",
						title: __("Items Required"),
						indicator: "blue",
					});
				}

				dialog.hide();

				var method = args.against_default_supplier
					? "make_purchase_order_for_default_supplier"
					: "make_purchase_order";
				return frappe.call({
					method: "erpnext.selling.doctype.sales_order.sales_order." + method,
					freeze_message: __("Creating Purchase Order ..."),
					args: {
						source_name: me.frm.doc.name,
						selected_items: selected_items,
					},
					freeze: true,
					callback: function (r) {
						if (!r.exc) {
							if (!args.against_default_supplier) {
								frappe.model.sync(r.message);
								frappe.set_route("Form", r.message.doctype, r.message.name);
							} else {
								frappe.route_options = {
									sales_order: me.frm.doc.name,
								};
								frappe.set_route("List", "Purchase Order");
							}
						}
					},
				});
			},
		});

		dialog.fields_dict["against_default_supplier"].df.onchange = () => set_po_items_data(dialog);

		function set_po_items_data(dialog) {
			var against_default_supplier = dialog.get_value("against_default_supplier");
			var items_for_po = dialog.get_value("items_for_po");

			if (against_default_supplier) {
				let items_with_supplier = items_for_po.filter((item) => item.supplier);

				dialog.fields_dict["items_for_po"].df.data = items_with_supplier;
				dialog.get_field("items_for_po").refresh();
			} else {
				let po_items = [];
				me.frm.doc.items.forEach((d) => {
					let ordered_qty = me.get_ordered_qty(d, me.frm.doc);
					let pending_qty = (flt(d.stock_qty) - ordered_qty) / flt(d.conversion_factor);
					if (pending_qty > 0) {
						po_items.push({
							doctype: "Sales Order Item",
							name: d.name,
							item_name: d.item_name,
							item_code: d.item_code,
							pending_qty: pending_qty,
							uom: d.uom,
							supplier: d.supplier,
						});
					}
				});

				dialog.fields_dict["items_for_po"].df.data = po_items;
				dialog.get_field("items_for_po").refresh();
			}
		}

		set_po_items_data(dialog);
		dialog.get_field("items_for_po").grid.only_sortable();
		dialog.get_field("items_for_po").refresh();
		dialog.wrapper.find(".grid-heading-row .grid-row-check").click();
		dialog.show();
	}

	get_ordered_qty(item, so) {
		let ordered_qty = item.ordered_qty;
		if (so.packed_items && so.packed_items.length) {
			// calculate ordered qty based on packed items in case of product bundle
			let packed_items = so.packed_items.filter((pi) => pi.parent_detail_docname == item.name);
			if (packed_items && packed_items.length) {
				ordered_qty = packed_items.reduce((sum, pi) => sum + flt(pi.ordered_qty), 0);
				ordered_qty = ordered_qty / packed_items.length;
			}
		}
		return ordered_qty;
	}

	hold_sales_order() {
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
				frappe.call({
					method: "frappe.desk.form.utils.add_comment",
					args: {
						reference_doctype: me.frm.doctype,
						reference_name: me.frm.docname,
						content: __("Reason for hold:") + " " + data.reason_for_hold,
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
	close_sales_order() {
		this.frm.cscript.update_status("Close", "Closed");
	}
	update_status(label, status) {
		var doc = this.frm.doc;
		var me = this;
		frappe.ui.form.is_saving = true;
		frappe.call({
			method: "erpnext.selling.doctype.sales_order.sales_order.update_status",
			args: { status: status, name: doc.name },
			callback: function (r) {
				me.frm.reload_doc();
			},
			always: function () {
				frappe.ui.form.is_saving = false;
			},
		});
	}
};

extend_cscript(cur_frm.cscript, new erpnext.selling.SalesOrderController({ frm: cur_frm }));

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Payment Terms Status for Sales Order` | Script Report | Selling |
| `Sales Order Analysis` | Script Report | Selling |
| `Exponential Smoothing Forecasting` | Script Report | Manufacturing |
| `Territory Target Variance Based On Item Group` | Script Report | Selling |
| `Sales Person Target Variance Based On Item Group` | Script Report | Selling |
| `Sales Partner Target Variance based on Item Group` | Script Report | Selling |
| `Sales Partner Transaction Summary` | Script Report | Selling |
| `Sales Partner Commission Summary` | Script Report | Selling |
| `Pending SO Items For Purchase Request` | Script Report | Selling |
| `Sales Analytics` | Script Report | Selling |
| `Sales Person Commission Summary` | Script Report | Selling |
| `Inactive Customers` | Script Report | Selling |
| `Sales Order Trends` | Script Report | Selling |
| `Item-wise Sales History` | Script Report | Selling |
| `Sales Person-wise Transaction Summary` | Script Report | Selling |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Sales Orders to Bill` | Sales Orders to Bill | Count | Selling |
| `Sales Orders to Deliver` | Sales Orders to Deliver | Count | Selling |
| `Annual Sales` | Annual Sales | Sum | Selling |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
