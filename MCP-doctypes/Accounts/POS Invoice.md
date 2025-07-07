# Master Control Plan: `POS Invoice`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | ACC-PSINV-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `customer_name` | Customer Name | Data | None |  |  | ✅ | None | None |
| `tax_id` | Tax Id | Data | None |  |  | ✅ | None | None |
| `pos_profile` | POS Profile | Link | POS Profile |  |  |  | None | None |
| `consolidated_invoice` | Consolidated Sales Invoice | Link | Sales Invoice |  |  | ✅ | None | None |
| `is_pos` | Include Payment (POS) | Check | None | ✅ |  | ✅ | 1 | None |
| `is_return` | Is Return (Credit Note) | Check | None |  |  |  | 0 | None |
| `update_billed_amount_in_sales_order` | Update Billed Amount in Sales Order | Check | None |  |  |  | 0 | None |
| `update_billed_amount_in_delivery_note` | Update Billed Amount in Delivery Note | Check | None |  |  |  | 1 | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None |  |  |  | None | None |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `due_date` | Payment Due Date | Date | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | POS Invoice |  |  | ✅ | None | None |
| `return_against` | Return Against | Link | POS Invoice |  |  | ✅ | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `customer_po_details` | Customer PO Details | Section Break | None |  |  |  | None | None |
| `po_no` | Customer's Purchase Order | Data | None |  |  |  | None | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `po_date` | Customer's Purchase Order Date | Date | None |  |  |  | None | None |
| `address_and_contact` | Address and Contact | Section Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Data | Phone |  | ✅ | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `shipping_address_name` | Shipping Address Name | Link | Address |  |  |  | None | None |
| `shipping_address` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `company_address` | Company Address Name | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address | Text Editor | None |  | ✅ | ✅ | None | None |
| `company_contact_person` | Company Contact Person | Link | Contact |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Customer Currency is converted to customer's base currency |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Price list currency is converted to customer's base currency |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `sec_warehouse` | Warehouse | Section Break | None |  |  |  | None | None |
| `set_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_section` | Items | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `update_stock` | Update Stock | Check | None |  |  |  | 0 | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `items` | Items | Table | POS Invoice Item | ✅ |  |  | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `packing_list` | Packing List | Section Break | fa fa-suitcase |  |  |  | None | None |
| `packed_items` | Packed Items | Table | Packed Item |  |  |  | None | None |
| `product_bundle_help` | Product Bundle Help | HTML | None |  |  |  | None | None |
| `time_sheet_list` | Time Sheet List | Section Break | None |  |  |  | None | None |
| `timesheets` | Time Sheets | Table | Sales Invoice Timesheet |  |  |  | None | None |
| `total_billing_amount` | Total Billing Amount | Currency | None |  |  | ✅ | 0 | None |
| `section_break_30` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `taxes_section` | None | Section Break | fa fa-money |  |  |  | None | None |
| `taxes_and_charges` | Sales Taxes and Charges Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `section_break_40` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Sales Taxes and Charges | Table | Sales Taxes and Charges |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `section_break_43` | None | Section Break | None |  |  |  | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_47` | None | Column Break | None |  |  |  | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `loyalty_points_redemption` | Loyalty Points Redemption | Section Break | None |  |  |  | None | None |
| `loyalty_points` | Loyalty Points | Int | None |  |  |  | None | None |
| `loyalty_amount` | Loyalty Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `redeem_loyalty_points` | Redeem Loyalty Points | Check | None |  |  |  | 0 | None |
| `column_break_77` | None | Column Break | None |  |  |  | None | None |
| `loyalty_program` | Loyalty Program | Link | Loyalty Program |  |  | ✅ | None | None |
| `loyalty_redemption_account` | Redemption Account | Link | Account |  |  |  | None | None |
| `loyalty_redemption_cost_center` | Redemption Cost Center | Link | Cost Center |  |  |  | None | None |
| `section_break_49` | Additional Discount | Section Break | None |  |  |  | None | None |
| `coupon_code` | Coupon Code | Link | Coupon Code |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `totals` | None | Section Break | fa fa-money |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | In Words will be visible once you save the Sales Invoice. |
| `column_break5` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency | ✅ |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `total_advance` | Total Advance | Currency | party_account_currency |  |  | ✅ | None | None |
| `outstanding_amount` | Outstanding Amount | Currency | party_account_currency |  |  | ✅ | None | None |
| `advances_section` | Advance Payments | Section Break | fa fa-money |  |  |  | None | None |
| `allocate_advances_automatically` | Allocate Advances Automatically (FIFO) | Check | None |  |  |  | 0 | None |
| `get_advances` | Get Advances Received | Button | set_advances |  |  |  | None | None |
| `advances` | Advances | Table | Sales Invoice Advance |  |  |  | None | None |
| `payment_schedule_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `payments_section` | Payments | Section Break | fa fa-money |  |  |  | None | None |
| `cash_bank_account` | Cash/Bank Account | Link | Account |  | ✅ |  | None | None |
| `payments` | Sales Invoice Payment | Table | Sales Invoice Payment |  |  |  | None | None |
| `section_break_84` | None | Section Break | None |  |  |  | None | None |
| `base_paid_amount` | Paid Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_86` | None | Column Break | None |  |  |  | None | None |
| `paid_amount` | Paid Amount | Currency | currency |  |  | ✅ | None | None |
| `section_break_88` | None | Section Break | None |  |  |  | None | None |
| `base_change_amount` | Base Change Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_90` | None | Column Break | None |  |  |  | None | None |
| `change_amount` | Change Amount | Currency | currency |  |  |  | None | None |
| `account_for_change_amount` | Account for Change Amount | Link | Account |  |  |  | None | None |
| `column_break4` | Write Off | Section Break | None |  |  |  | None | None |
| `write_off_amount` | Write Off Amount | Currency | currency |  |  |  | None | None |
| `base_write_off_amount` | Write Off Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `write_off_outstanding_amount_automatically` | Write Off Outstanding Amount | Check | None |  |  |  | 0 | None |
| `column_break_74` | None | Column Break | None |  |  |  | None | None |
| `write_off_account` | Write Off Account | Link | Account |  |  |  | None | None |
| `write_off_cost_center` | Write Off Cost Center | Link | Cost Center |  |  |  | None | None |
| `terms_section_break` | Terms and Conditions | Section Break | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions Details | Text Editor | None |  |  |  | None | None |
| `edit_printing_settings` | Printing Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `language` | Print Language | Data | None |  |  | ✅ | None | None |
| `column_break_84` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `more_information` | More Information | Section Break | None |  |  |  | None | None |
| `inter_company_invoice_reference` | Inter Company Invoice Reference | Link | Purchase Invoice |  |  | ✅ | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  | ✅ |  | None | None |
| `is_discounted` | Is Discounted | Check | None |  |  | ✅ | 0 | None |
| `col_break23` | None | Column Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `column_break_gpiw` | None | Column Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Return
Credit Note Issued
Consolidated
Submitted
Paid
Partly Paid
Unpaid
Partly Paid and Discounted
Unpaid and Discounted
Overdue and Discounted
Overdue
Cancelled |  |  | ✅ | Draft | None |
| `more_info` | Accounting Details | Section Break | fa fa-file-text |  |  |  | None | None |
| `debit_to` | Debit To | Link | Account | ✅ |  |  | None | None |
| `party_account_currency` | Party Account Currency | Link | Currency |  | ✅ | ✅ | None | None |
| `is_opening` | Is Opening Entry | Select | No
Yes |  |  |  | No | None |
| `column_break8` | None | Column Break | None |  |  |  | None | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `sales_team_section_break` | Commission | Section Break | fa fa-group |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `column_break10` | None | Column Break | None |  |  |  | None | None |
| `amount_eligible_for_commission` | Amount Eligible for Commission | Currency | None |  |  | ✅ | None | None |
| `commission_rate` | Commission Rate (%) | Float | None |  |  |  | None | None |
| `total_commission` | Total Commission | Currency | Company:company:default_currency |  |  |  | None | None |
| `section_break2` | Sales Team | Section Break | None |  |  |  | None | None |
| `sales_team` | Sales Team | Table | Sales Team |  |  |  | None | None |
| `subscription_section` | Subscription Section | Section Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `column_break_140` | None | Column Break | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `against_income_account` | Against Income Account | Small Text | None |  | ✅ |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 42
- **Dynamic Link Fields:** 0
- **Table Fields:** 9

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_invoice/pos_invoice.js`
```javascript
// Copyright (c) 2020, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.accounts");
erpnext.sales_common.setup_selling_controller();

erpnext.accounts.pos.setup("POS Invoice");
erpnext.selling.POSInvoiceController = class POSInvoiceController extends erpnext.selling.SellingController {
	settings = {};

	setup(doc) {
		this.setup_posting_date_time_check();
		super.setup(doc);
	}

	company() {
		erpnext.accounts.dimensions.update_dimension(this.frm, this.frm.doctype);
		this.frm.set_value("set_warehouse", "");
		this.frm.set_value("taxes_and_charges", "");
	}

	onload(doc) {
		super.onload();
		this.frm.ignore_doctypes_on_cancel_all = [
			"POS Invoice Merge Log",
			"POS Closing Entry",
			"Serial and Batch Bundle",
		];

		if (doc.__islocal && doc.is_pos && frappe.get_route_str() !== "point-of-sale") {
			this.frm.script_manager.trigger("is_pos");
			this.frm.refresh_fields();
		}

		this.frm.set_query("set_warehouse", function (doc) {
			return {
				filters: {
					company: doc.company ? doc.company : "",
				},
			};
		});

		this.frm.set_query("item_code", "items", function (doc) {
			return {
				query: "erpnext.accounts.doctype.pos_invoice.pos_invoice.item_query",
				filters: {
					has_variants: ["=", 0],
					is_sales_item: ["=", 1],
					disabled: ["=", 0],
					is_fixed_asset: ["=", 0],
					pos_profile: ["=", doc.pos_profile],
				},
			};
		});

		erpnext.accounts.dimensions.setup_dimension_filters(this.frm, this.frm.doctype);
	}

	onload_post_render(frm) {
		super.onload_post_render();
		this.pos_profile(frm);
	}

	refresh(doc) {
		super.refresh();

		if (doc.docstatus == 1 && !doc.is_return) {
			this.frm.add_custom_button(__("Return"), this.make_sales_return.bind(this), __("Create"));
			if (["Partly Paid", "Overdue", "Unpaid"].includes(doc.status)) {
				this.frm.add_custom_button(
					__("Payment"),
					this.collect_outstanding_payment.bind(this),
					__("Create")
				);
			}
			this.frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (doc.is_return && doc.__islocal) {
			this.frm.return_print_format = "Sales Invoice Return";
			this.frm.set_value("consolidated_invoice", "");
		}

		this.frm.set_query(
			"customer",
			function () {
				const customer_groups = this.settings?.customer_groups;

				if (!customer_groups?.length) return {};

				return {
					filters: {
						customer_group: ["in", customer_groups],
					},
				};
			}.bind(this)
		);
	}

	is_pos() {
		this.set_pos_data();
	}

	async set_pos_data() {
		if (this.frm.doc.is_pos) {
			this.frm.set_value("allocate_advances_automatically", 0);
			if (!this.frm.doc.company) {
				this.frm.set_value("is_pos", 0);
				frappe.msgprint(__("Please specify Company to proceed"));
			} else {
				const r = await this.frm.call({
					doc: this.frm.doc,
					method: "set_missing_values",
					freeze: true,
				});
				if (!r.exc) {
					if (r.message) {
						this.frm.pos_print_format = r.message.print_format || "";
						this.frm.meta.default_print_format = r.message.print_format || "";
						this.frm.doc.campaign = r.message.campaign;
						this.frm.allow_print_before_pay = r.message.allow_print_before_pay;
					}
					this.frm.script_manager.trigger("update_stock");
					this.calculate_taxes_and_totals();
					this.frm.doc.taxes_and_charges && this.frm.script_manager.trigger("taxes_and_charges");
					frappe.model.set_default_values(this.frm.doc);
					this.set_dynamic_labels();
				}
			}
		}
	}

	customer() {
		if (!this.frm.doc.customer) return;
		const pos_profile = this.frm.doc.pos_profile;
		if (this.frm.updating_party_details) return;
		erpnext.utils.get_party_details(
			this.frm,
			"erpnext.accounts.party.get_party_details",
			{
				posting_date: this.frm.doc.posting_date,
				party: this.frm.doc.customer,
				party_type: "Customer",
				account: this.frm.doc.debit_to,
				price_list: this.frm.doc.selling_price_list,
				pos_profile: pos_profile,
				company_address: this.frm.doc.company_address,
			},
			() => {
				this.apply_pricing_rule();
			}
		);
	}

	pos_profile(frm) {
		if (!frm.pos_profile || frm.pos_profile == "") {
			this.update_customer_groups_settings([]);
			return;
		}

		frappe.call({
			method: "erpnext.selling.page.point_of_sale.point_of_sale.get_pos_profile_data",
			args: { pos_profile: frm.pos_profile },
			callback: ({ message: profile }) => {
				this.update_customer_groups_settings(profile?.customer_groups);
				this.frm.set_value("company", profile?.company);
			},
		});
	}

	update_customer_groups_settings(customer_groups) {
		this.settings.customer_groups = customer_groups?.map((group) => group.name);
	}

	amount() {
		this.write_off_outstanding_amount_automatically();
	}

	change_amount() {
		if (this.frm.doc.paid_amount > this.frm.doc.grand_total) {
			this.calculate_write_off_amount();
		} else {
			this.frm.set_value("change_amount", 0.0);
			this.frm.set_value("base_change_amount", 0.0);
		}

		this.frm.refresh_fields();
	}

	loyalty_amount() {
		this.calculate_outstanding_amount();
		this.frm.refresh_field("outstanding_amount");
		this.frm.refresh_field("paid_amount");
		this.frm.refresh_field("base_paid_amount");
	}

	write_off_outstanding_amount_automatically() {
		if (cint(this.frm.doc.write_off_outstanding_amount_automatically)) {
			frappe.model.round_floats_in(this.frm.doc, ["grand_total", "paid_amount"]);
			// this will make outstanding amount 0
			this.frm.set_value(
				"write_off_amount",
				flt(
					this.frm.doc.grand_total - this.frm.doc.paid_amount - this.frm.doc.total_advance,
					precision("write_off_amount")
				)
			);
		}

		this.calculate_outstanding_amount(false);
		this.frm.refresh_fields();
	}

	make_sales_return() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.pos_invoice.pos_invoice.make_sales_return",
			frm: this.frm,
		});
	}

	async collect_outstanding_payment() {
		const total_amount = flt(this.frm.doc.rounded_total) | flt(this.frm.doc.grand_total);
		const paid_amount = flt(this.frm.doc.paid_amount);
		const outstanding_amount = flt(this.frm.doc.outstanding_amount);
		const me = this;

		const table_fields = [
			{
				fieldname: "mode_of_payment",
				fieldtype: "Link",
				in_list_view: 1,
				label: __("Mode of Payment"),
				options: "Mode of Payment",
				reqd: 1,
			},
			{
				fieldname: "amount",
				fieldtype: "Currency",
				in_list_view: 1,
				label: __("Amount"),
				options: this.frm.doc.currency,
				reqd: 1,
				onchange: function () {
					dialog.fields_dict.payments.df.data.some((d) => {
						if (d.idx == this.doc.idx) {
							d.amount = this.value === null ? 0 : this.value;
							dialog.fields_dict.payments.grid.refresh();
							return true;
						}
					});

					let amount = 0;
					for (let d of dialog.fields_dict.payments.df.data) {
						amount += d.amount;
					}

					let change_amount = total_amount - (paid_amount + amount);

					dialog.fields_dict.outstanding_amount.set_value(
						outstanding_amount - amount < 0 ? 0 : outstanding_amount - amount
					);
					dialog.fields_dict.paid_amount.set_value(paid_amount + amount);
					dialog.fields_dict.change_amount.set_value(change_amount < 0 ? change_amount * -1 : 0);
				},
			},
		];
		const payment_method_data = await this.fetch_pos_payment_methods();
		const dialog = new frappe.ui.Dialog({
			title: __("Collect Outstanding Amount"),
			fields: [
				{
					fieldname: "payments",
					fieldtype: "Table",
					label: __("Payments"),
					cannot_add_rows: false,
					in_place_edit: true,
					reqd: 1,
					data: payment_method_data,
					fields: table_fields,
				},
				{
					fieldname: "section_break_1",
					fieldtype: "Section Break",
				},
				{
					fieldname: "outstanding_amount",
					fieldtype: "Currency",
					label: __("Outstanding Amount"),
					read_only: 1,
					default: outstanding_amount,
				},
				{
					fieldname: "column_break_1",
					fieldtype: "Column Break",
				},
				{
					fieldname: "paid_amount",
					fieldtype: "Currency",
					label: __("Paid Amount"),
					read_only: 1,
					default: paid_amount,
				},
				{
					fieldname: "change_amount",
					fieldtype: "Currency",
					label: __("Change Amount"),
					read_only: 1,
					default: 0,
				},
			],
			primary_action_label: __("Submit"),
			primary_action(values) {
				dialog.hide();
				me.frm.call({
					doc: me.frm.doc,
					method: "update_payments",
					args: {
						payments: values.payments.filter((d) => d.amount != 0),
					},
					freeze: true,
					callback: function (r) {
						if (!r.exc) {
							frappe.show_alert({
								message: __("Payments updated."),
								indicator: "green",
							});
							me.frm.reload_doc();
						} else {
							frappe.show_alert({
								message: __("Payments could not be updated."),
								indicator: "red",
							});
						}
					},
				});
			},
		});
		dialog.show();
	}

	async fetch_pos_payment_methods() {
		const pos_profile = this.frm.doc.pos_profile;
		if (!pos_profile) return;
		const pos_profile_doc = await frappe.db.get_doc("POS Profile", pos_profile);
		const data = [];
		pos_profile_doc.payments.forEach((pay) => {
			const { mode_of_payment } = pay;
			data.push({ mode_of_payment, amount: 0 });
		});
		return data;
	}
};

extend_cscript(cur_frm.cscript, new erpnext.selling.POSInvoiceController({ frm: cur_frm }));

frappe.ui.form.on("POS Invoice", {
	redeem_loyalty_points: function (frm) {
		frm.events.get_loyalty_details(frm);
	},

	loyalty_points: function (frm) {
		if (frm.redemption_conversion_factor) {
			frm.events.set_loyalty_points(frm);
		} else {
			frappe.call({
				method: "erpnext.accounts.doctype.loyalty_program.loyalty_program.get_redeemption_factor",
				args: {
					loyalty_program: frm.doc.loyalty_program,
				},
				callback: function (r) {
					if (r) {
						frm.redemption_conversion_factor = r.message;
						frm.events.set_loyalty_points(frm);
					}
				},
			});
		}
	},

	get_loyalty_details: function (frm) {
		if (frm.doc.customer && frm.doc.redeem_loyalty_points) {
			frappe.call({
				method: "erpnext.accounts.doctype.loyalty_program.loyalty_program.get_loyalty_program_details",
				args: {
					customer: frm.doc.customer,
					loyalty_program: frm.doc.loyalty_program,
					expiry_date: frm.doc.posting_date,
					company: frm.doc.company,
				},
				callback: function (r) {
					if (r) {
						frm.set_value("loyalty_redemption_account", r.message.expense_account);
						frm.set_value("loyalty_redemption_cost_center", r.message.cost_center);
						frm.redemption_conversion_factor = r.message.conversion_factor;
					}
				},
			});
		}
	},

	set_loyalty_points: function (frm) {
		if (frm.redemption_conversion_factor) {
			let loyalty_amount = flt(
				frm.redemption_conversion_factor * flt(frm.doc.loyalty_points),
				precision("loyalty_amount")
			);
			var remaining_amount =
				flt(frm.doc.grand_total) - flt(frm.doc.total_advance) - flt(frm.doc.write_off_amount);
			if (frm.doc.grand_total && remaining_amount < loyalty_amount) {
				let redeemable_points = parseInt(remaining_amount / frm.redemption_conversion_factor);
				frappe.throw(__("You can only redeem max {0} points in this order.", [redeemable_points]));
			}
			frm.set_value("loyalty_amount", loyalty_amount);
		}
	},

	request_for_payment: function (frm) {
		if (!frm.doc.contact_mobile) {
			frappe.throw(__("Please enter mobile number first."));
		}
		frm.dirty();
		frm.save().then(() => {
			frappe.dom.freeze(__("Waiting for payment..."));
			frappe
				.call({
					method: "create_payment_request",
					doc: frm.doc,
				})
				.fail(() => {
					frappe.dom.unfreeze();
					frappe.msgprint(__("Payment request failed"));
				})
				.then(({ message }) => {
					const payment_request_name = message.name;
					setTimeout(() => {
						frappe.db
							.get_value("Payment Request", payment_request_name, ["status", "grand_total"])
							.then(({ message }) => {
								if (message.status != "Paid") {
									frappe.dom.unfreeze();
									frappe.msgprint({
										message: __(
											"Payment Request took too long to respond. Please try requesting for payment again."
										),
										title: __("Request Timeout"),
									});
								} else if (frappe.dom.freeze_count != 0) {
									frappe.dom.unfreeze();
									frm.reload_doc();
									cur_pos.payment.events.submit_invoice();

									frappe.show_alert({
										message: __("Payment of {0} received successfully.", [
											format_currency(message.grand_total, frm.doc.currency, 0),
										]),
										indicator: "green",
									});
								}
							});
					}, 60000);
				});
		});
	},
});

frappe.ui.form.on("Sales Invoice Payment", {
	mode_of_payment: function (frm) {
		frappe.call({
			doc: frm.doc,
			method: "set_account_for_mode_of_payment",
			callback: function (r) {
				refresh_field("payments");
			},
		});
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `POS Register` | Script Report | Accounts |



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
