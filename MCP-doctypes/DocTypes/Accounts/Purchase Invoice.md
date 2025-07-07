# Master Control Plan: `Purchase Invoice`

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
| Accounts User | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Auditor | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Accounts Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `title` | Title | Data | None |  | ✅ |  | {supplier_name} | None |
| `naming_series` | Series | Select | ACC-PINV-.YYYY.-
ACC-PINV-RET-.YYYY.- | ✅ |  |  | None | None |
| `supplier` | Supplier | Link | Supplier | ✅ |  |  | None | None |
| `supplier_name` | Supplier Name | Data | None |  |  | ✅ | None | None |
| `tax_id` | Tax Id | Read Only | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `column_break_6` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None |  |  |  | None | None |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `due_date` | Due Date | Date | None |  |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `is_paid` | Is Paid | Check | None |  |  |  | 0 | None |
| `is_return` | Is Return (Debit Note) | Check | None |  |  |  | 0 | None |
| `return_against` | Return Against Purchase Invoice | Link | Purchase Invoice |  |  | ✅ | None | None |
| `update_outstanding_for_self` | Update Outstanding for Self | Check | None |  |  |  | 1 | Debit Note will update it's own outstanding amount, even if 'Return Against' is specified. |
| `update_billed_amount_in_purchase_order` | Update Billed Amount in Purchase Order | Check | None |  |  |  | 0 | None |
| `update_billed_amount_in_purchase_receipt` | Update Billed Amount in Purchase Receipt | Check | None |  |  |  | 1 | None |
| `apply_tds` | Apply Tax Withholding Amount | Check | None |  |  |  | 0 | None |
| `tax_withholding_category` | Tax Withholding Category | Link | Tax Withholding Category |  | ✅ |  | None | None |
| `amended_from` | Amended From | Link | Purchase Invoice |  |  | ✅ | None | None |
| `supplier_invoice_details` | Supplier Invoice | Section Break | None |  |  |  | None | None |
| `bill_no` | Supplier Invoice No | Data | None |  |  |  | None | None |
| `column_break_15` | None | Column Break | None |  |  |  | None | None |
| `bill_date` | Supplier Invoice Date | Date | None |  |  |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions  | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | fa fa-tag |  |  |  | None | None |
| `currency` | Currency | Link | Currency |  |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None |  |  |  | None | None |
| `use_transaction_date_exchange_rate` | Use Transaction Date Exchange Rate | Check | None |  |  | ✅ | 0 | None |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `buying_price_list` | Price List | Link | Price List |  |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency |  |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None |  |  |  | None | None |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `sec_warehouse` | Items | Section Break | None |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `col_break_warehouse` | None | Column Break | None |  |  |  | None | None |
| `update_stock` | Update Stock | Check | None |  |  |  | 0 | None |
| `set_warehouse` | Set Accepted Warehouse | Link | Warehouse |  |  |  | None | None |
| `set_from_warehouse` | Set From Warehouse | Link | Warehouse |  |  |  | None | None |
| `is_subcontracted` | Is Subcontracted | Check | None |  |  | ✅ | 0 | None |
| `rejected_warehouse` | Rejected Warehouse | Link | Warehouse |  |  |  | None | None |
| `supplier_warehouse` | Supplier Warehouse | Link | Warehouse |  |  |  | None | None |
| `items_section` | None | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `items` | Items | Table | Purchase Invoice Item | ✅ |  |  | None | None |
| `section_break_26` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_50` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_28` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `tax_withholding_net_total` | Tax Withholding Net Total | Currency | currency |  | ✅ | ✅ | 0 | None |
| `base_tax_withholding_net_total` | Base Tax Withholding Net Total | Currency | Company:company:default_currency |  | ✅ | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Purchase Taxes and Charges Template | Link | Purchase Taxes and Charges Template |  |  |  | None | None |
| `column_break_58` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_49` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_51` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Purchase Taxes and Charges | Table | Purchase Taxes and Charges |  |  |  | None | None |
| `totals` | None | Section Break | fa fa-money |  |  |  | None | None |
| `base_taxes_and_charges_added` | Taxes and Charges Added (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_taxes_and_charges_deducted` | Taxes and Charges Deducted (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_40` | None | Column Break | None |  |  |  | None | None |
| `taxes_and_charges_added` | Taxes and Charges Added | Currency | currency |  |  | ✅ | None | None |
| `taxes_and_charges_deducted` | Taxes and Charges Deducted | Currency | currency |  |  | ✅ | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `section_break_49` | Totals | Section Break | None |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Data | None |  |  | ✅ | None | None |
| `column_break8` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency |  |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `use_company_roundoff_cost_center` | Use Company Default Round Off Cost Center | Check | None |  |  |  | 0 | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Data | None |  |  | ✅ | None | None |
| `total_advance` | Total Advance | Currency | party_account_currency |  |  | ✅ | None | None |
| `outstanding_amount` | Outstanding Amount | Currency | party_account_currency |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `section_break_44` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_46` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `tax_withheld_vouchers_section` | Tax Withheld Vouchers | Section Break | None |  |  |  | None | None |
| `tax_withheld_vouchers` | Tax Withheld Vouchers | Table | Tax Withheld Vouchers |  |  | ✅ | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `raw_materials_supplied` | Raw Materials Supplied | Section Break | None |  |  |  | None | None |
| `supplied_items` | Supplied Items | Table | Purchase Receipt Item Supplied |  |  |  | None | None |
| `payments_tab` | Payments | Tab Break | None |  |  |  | None | None |
| `payments_section` | Payments | Section Break | None |  |  |  | None | None |
| `mode_of_payment` | Mode of Payment | Link | Mode of Payment |  |  |  | None | None |
| `base_paid_amount` | Paid Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `clearance_date` | Clearance Date | Date | None |  |  | ✅ | None | None |
| `col_br_payments` | None | Column Break | None |  |  |  | None | None |
| `cash_bank_account` | Cash/Bank Account | Link | Account |  |  |  | None | None |
| `paid_amount` | Paid Amount | Currency | currency |  |  |  | None | None |
| `advances_section` | Advance Payments | Section Break | fa fa-money |  |  |  | None | None |
| `allocate_advances_automatically` | Set Advances and Allocate (FIFO) | Check | None |  |  |  | 0 | None |
| `only_include_allocated_payments` | Only Include Allocated Payments | Check | None |  |  |  | 0 | Advance payments allocated against orders will only be fetched |
| `get_advances` | Get Advances Paid | Button | set_advances |  |  |  | None | None |
| `advances` | Advances | Table | Purchase Invoice Advance |  |  |  | None | None |
| `advance_tax` | Advance Tax | Table | Advance Tax |  | ✅ | ✅ | None | None |
| `write_off` | Write Off | Section Break | None |  |  |  | None | None |
| `write_off_amount` | Write Off Amount | Currency | currency |  |  |  | None | None |
| `base_write_off_amount` | Write Off Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_61` | None | Column Break | None |  |  |  | None | None |
| `write_off_account` | Write Off Account | Link | Account |  |  |  | None | None |
| `write_off_cost_center` | Write Off Cost Center | Link | Cost Center |  |  |  | None | None |
| `address_and_contact_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `section_addresses` | Supplier Address | Section Break | None |  |  |  | None | None |
| `supplier_address` | Select Supplier Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break_address` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  |  | ✅ | None | None |
| `contact_email` | Contact Email | Small Text | Email |  |  | ✅ | None | None |
| `company_shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `dispatch_address` | Select Dispatch Address  | Link | Address |  |  |  | None | None |
| `dispatch_address_display` | Dispatch Address | Text Editor | None |  |  | ✅ | None | None |
| `column_break_126` | None | Column Break | None |  |  |  | None | None |
| `shipping_address` | Select Shipping Address | Link | Address |  |  |  | None | None |
| `shipping_address_display` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `company_billing_address_section` | Company Billing Address | Section Break | None |  |  |  | None | None |
| `billing_address` | Select Billing Address | Link | Address |  |  |  | None | None |
| `column_break_130` | None | Column Break | None |  |  |  | None | None |
| `billing_address_display` | Billing Address | Text Editor | None |  |  | ✅ | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `payment_schedule_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `ignore_default_payment_terms_template` | Ignore Default Payment Terms Template | Check | None |  | ✅ | ✅ | 0 | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `terms_section_break` | Terms and Conditions | Section Break | fa fa-legal |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `status_section` | Status | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Return
Debit Note Issued
Submitted
Paid
Partly Paid
Unpaid
Overdue
Cancelled
Internal Transfer |  |  |  | Draft | None |
| `column_break_177` | None | Column Break | None |  |  |  | None | None |
| `per_received` | Per Received | Percent | None |  | ✅ | ✅ | None | None |
| `accounting_details_section` | Accounting Details | Section Break | None |  |  |  | None | None |
| `credit_to` | Credit To | Link | Account | ✅ |  |  | None | None |
| `party_account_currency` | Party Account Currency | Link | Currency |  | ✅ | ✅ | None | None |
| `is_opening` | Is Opening Entry | Select | No
Yes |  |  |  | No | None |
| `against_expense_account` | Against Expense Account | Small Text | None |  | ✅ |  | None | None |
| `column_break_63` | None | Column Break | None |  |  |  | None | None |
| `unrealized_profit_loss_account` | Unrealized Profit / Loss Account | Link | Account |  |  |  | None | Unrealized Profit/Loss account for intra-company transfers |
| `subscription_section` | Subscription | Section Break | None |  |  |  | None | None |
| `subscription` | Subscription | Link | Subscription |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `column_break_114` | None | Column Break | None |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | Start date of current invoice's period |
| `to_date` | To Date | Date | None |  |  |  | None | End date of current invoice's period |
| `printing_settings` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_112` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Data | None |  |  | ✅ | None | None |
| `sb_14` | Hold Invoice | Section Break | None |  |  |  | None | None |
| `on_hold` | Hold Invoice | Check | None |  |  |  | 0 | None |
| `release_date` | Release Date | Date | None |  |  |  | None | Once set, this invoice will be on hold till the set date |
| `cb_17` | None | Column Break | None |  |  |  | None | None |
| `hold_comment` | Reason For Putting On Hold | Small Text | None |  |  |  | None | None |
| `additional_info_section` | Additional Info | Section Break | fa fa-file-text |  |  |  | None | None |
| `is_internal_supplier` | Is Internal Supplier | Check | None |  |  | ✅ | 0 | None |
| `represents_company` | Represents Company | Link | Company |  |  |  | None | Company which internal supplier represents |
| `supplier_group` | Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `sender` | Sender | Data | Email |  |  |  | None | None |
| `column_break_147` | None | Column Break | None |  |  |  | None | None |
| `inter_company_invoice_reference` | Inter Company Invoice Reference | Link | Sales Invoice |  |  | ✅ | None | None |
| `is_old_subcontracting_flow` | Is Old Subcontracting Flow | Check | None |  | ✅ | ✅ | 0 | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 39
- **Dynamic Link Fields:** 0
- **Table Fields:** 8

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/purchase_invoice/purchase_invoice.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.accounts");

cur_frm.cscript.tax_table = "Purchase Taxes and Charges";

erpnext.accounts.payment_triggers.setup("Purchase Invoice");
erpnext.accounts.taxes.setup_tax_filters("Purchase Taxes and Charges");
erpnext.accounts.taxes.setup_tax_validations("Purchase Invoice");
erpnext.buying.setup_buying_controller();

erpnext.accounts.PurchaseInvoice = class PurchaseInvoice extends erpnext.buying.BuyingController {
	setup(doc) {
		this.setup_posting_date_time_check();
		super.setup(doc);

		// formatter for purchase invoice item
		if (this.frm.doc.update_stock) {
			this.frm.set_indicator_formatter("item_code", function (doc) {
				return doc.qty <= doc.received_qty ? "green" : "orange";
			});
		}

		this.frm.set_query("unrealized_profit_loss_account", function () {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
					root_type: "Liability",
				},
			};
		});

		this.frm.set_query("expense_account", "items", function () {
			return {
				query: "erpnext.controllers.queries.get_expense_account",
				filters: { company: doc.company },
			};
		});
	}

	onload() {
		super.onload();

		// Ignore linked advances
		this.frm.ignore_doctypes_on_cancel_all = [
			"Journal Entry",
			"Payment Entry",
			"Purchase Invoice",
			"Repost Payment Ledger",
			"Repost Accounting Ledger",
			"Unreconcile Payment",
			"Unreconcile Payment Entries",
			"Serial and Batch Bundle",
			"Bank Transaction",
		];

		if (!this.frm.doc.__islocal) {
			// show credit_to in print format
			if (!this.frm.doc.supplier && this.frm.doc.credit_to) {
				this.frm.set_df_property("credit_to", "print_hide", 0);
			}
		}

		// Trigger supplier event on load if supplier is available
		// The reason for this is PI can be created from PR or PO and supplier is pre populated
		if (this.frm.doc.supplier && this.frm.doc.__islocal) {
			this.frm.trigger("supplier");
		}

		this.frm.set_query("supplier", function () {
			return {
				filters: {
					is_transporter: 0,
				},
			};
		});
	}

	refresh(doc) {
		const me = this;
		super.refresh();

		hide_fields(this.frm.doc);
		// Show / Hide button
		this.show_general_ledger();
		erpnext.accounts.ledger_preview.show_accounting_ledger_preview(this.frm);

		if (doc.update_stock == 1) {
			this.show_stock_ledger();
			erpnext.accounts.ledger_preview.show_stock_ledger_preview(this.frm);
		}

		if (!doc.is_return && doc.docstatus == 1 && doc.outstanding_amount != 0) {
			if (doc.on_hold) {
				this.frm.add_custom_button(
					__("Change Release Date"),
					function () {
						me.change_release_date();
					},
					__("Hold Invoice")
				);
				this.frm.add_custom_button(
					__("Unblock Invoice"),
					function () {
						me.unblock_invoice();
					},
					__("Create")
				);
			} else if (!doc.on_hold) {
				this.frm.add_custom_button(
					__("Block Invoice"),
					function () {
						me.block_invoice();
					},
					__("Create")
				);
			}
		}

		if (doc.docstatus == 1 && doc.outstanding_amount != 0 && !doc.on_hold) {
			this.frm.add_custom_button(__("Payment"), () => this.make_payment_entry(), __("Create"));
			this.frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (!doc.is_return && doc.docstatus == 1) {
			if (doc.outstanding_amount >= 0 || Math.abs(flt(doc.outstanding_amount)) < flt(doc.grand_total)) {
				this.frm.add_custom_button(
					__("Return / Debit Note"),
					this.make_debit_note.bind(this),
					__("Create")
				);
			}
		}

		if (doc.outstanding_amount > 0 && !cint(doc.is_return) && !doc.on_hold) {
			this.frm.add_custom_button(
				__("Payment Request"),
				function () {
					me.make_payment_request();
				},
				__("Create")
			);
		}

		if (doc.docstatus === 0) {
			this.frm.add_custom_button(
				__("Purchase Order"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.buying.doctype.purchase_order.purchase_order.make_purchase_invoice",
						source_doctype: "Purchase Order",
						target: me.frm,
						setters: {
							supplier: me.frm.doc.supplier || undefined,
							schedule_date: undefined,
						},
						get_query_filters: {
							docstatus: 1,
							status: ["not in", ["Closed", "On Hold"]],
							per_billed: ["<", 99.99],
							company: me.frm.doc.company,
						},
					});
				},
				__("Get Items From")
			);

			this.frm.add_custom_button(
				__("Purchase Receipt"),
				function () {
					erpnext.utils.map_current_doc({
						method: "erpnext.stock.doctype.purchase_receipt.purchase_receipt.make_purchase_invoice",
						source_doctype: "Purchase Receipt",
						target: me.frm,
						setters: {
							supplier: me.frm.doc.supplier || undefined,
							posting_date: undefined,
						},
						get_query_filters: {
							docstatus: 1,
							status: ["not in", ["Closed", "Completed", "Return Issued"]],
							company: me.frm.doc.company,
							is_return: 0,
						},
					});
				},
				__("Get Items From")
			);

			if (!this.frm.doc.is_return) {
				frappe.db.get_single_value("Buying Settings", "maintain_same_rate").then((value) => {
					if (value) {
						this.frm.doc.items.forEach((item) => {
							this.frm.fields_dict.items.grid.update_docfield_property(
								"rate",
								"read_only",
								item.purchase_receipt && item.pr_detail
							);
						});
					}
				});
			}
		}
		this.frm.toggle_reqd("supplier_warehouse", this.frm.doc.is_subcontracted);

		if (doc.docstatus == 1 && !doc.inter_company_invoice_reference) {
			frappe.model.with_doc("Supplier", me.frm.doc.supplier, function () {
				var supplier = frappe.model.get_doc("Supplier", me.frm.doc.supplier);
				var internal = supplier.is_internal_supplier;
				var disabled = supplier.disabled;
				if (internal == 1 && disabled == 0) {
					me.frm.add_custom_button(
						"Inter Company Invoice",
						function () {
							me.make_inter_company_invoice(me.frm);
						},
						__("Create")
					);
				}
			});
		}

		this.frm.set_df_property("tax_withholding_category", "hidden", doc.apply_tds ? 0 : 1);
		erpnext.accounts.unreconcile_payment.add_unreconcile_btn(me.frm);
	}

	unblock_invoice() {
		const me = this;
		frappe.call({
			method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.unblock_invoice",
			args: { name: me.frm.doc.name },
			callback: (r) => me.frm.reload_doc(),
		});
	}

	block_invoice() {
		this.make_comment_dialog_and_block_invoice();
	}

	change_release_date() {
		this.make_dialog_and_set_release_date();
	}

	can_change_release_date(date) {
		const diff = frappe.datetime.get_diff(date, frappe.datetime.nowdate());
		if (diff < 0) {
			frappe.throw(__("New release date should be in the future"));
			return false;
		} else {
			return true;
		}
	}

	make_comment_dialog_and_block_invoice() {
		const me = this;

		const title = __("Block Invoice");
		const fields = [
			{
				fieldname: "release_date",
				read_only: 0,
				fieldtype: "Date",
				label: __("Release Date"),
				default: me.frm.doc.release_date,
				reqd: 1,
			},
			{
				fieldname: "hold_comment",
				read_only: 0,
				fieldtype: "Small Text",
				label: __("Reason For Putting On Hold"),
				default: "",
			},
		];

		this.dialog = new frappe.ui.Dialog({
			title: title,
			fields: fields,
		});

		this.dialog.set_primary_action(__("Save"), function () {
			const dialog_data = me.dialog.get_values();
			frappe.call({
				method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.block_invoice",
				args: {
					name: me.frm.doc.name,
					hold_comment: dialog_data.hold_comment,
					release_date: dialog_data.release_date,
				},
				callback: (r) => me.frm.reload_doc(),
			});
			me.dialog.hide();
		});

		this.dialog.show();
	}

	make_dialog_and_set_release_date() {
		const me = this;

		const title = __("Set New Release Date");
		const fields = [
			{
				fieldname: "release_date",
				read_only: 0,
				fieldtype: "Date",
				label: __("Release Date"),
				default: me.frm.doc.release_date,
			},
		];

		this.dialog = new frappe.ui.Dialog({
			title: title,
			fields: fields,
		});

		this.dialog.set_primary_action(__("Save"), function () {
			me.dialog_data = me.dialog.get_values();
			if (me.can_change_release_date(me.dialog_data.release_date)) {
				me.dialog_data.name = me.frm.doc.name;
				me.set_release_date(me.dialog_data);
				me.dialog.hide();
			}
		});

		this.dialog.show();
	}

	set_release_date(data) {
		return frappe.call({
			method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.change_release_date",
			args: data,
			callback: (r) => this.frm.reload_doc(),
		});
	}

	supplier() {
		var me = this;

		// Do not update if inter company reference is there as the details will already be updated
		if (this.frm.updating_party_details || this.frm.doc.inter_company_invoice_reference) return;

		if (this.frm.doc.__onload && this.frm.doc.__onload.load_after_mapping) return;

		let payment_terms_template = this.frm.doc.payment_terms_template;

		erpnext.utils.get_party_details(
			this.frm,
			"erpnext.accounts.party.get_party_details",
			{
				posting_date: this.frm.doc.posting_date,
				bill_date: this.frm.doc.bill_date,
				party: this.frm.doc.supplier,
				party_type: "Supplier",
				account: this.frm.doc.credit_to,
				price_list: this.frm.doc.buying_price_list,
				fetch_payment_terms_template: cint(
					(this.frm.doc.is_return == 0) & !this.frm.doc.ignore_default_payment_terms_template
				),
			},
			function () {
				me.apply_pricing_rule();
				me.frm.doc.apply_tds = me.frm.supplier_tds ? 1 : 0;
				me.frm.doc.tax_withholding_category = me.frm.supplier_tds;
				me.frm.set_df_property("apply_tds", "read_only", me.frm.supplier_tds ? 0 : 1);
				me.frm.set_df_property("tax_withholding_category", "hidden", me.frm.supplier_tds ? 0 : 1);

				// while duplicating, don't change payment terms
				if (me.frm.doc.__run_link_triggers === false) {
					me.frm.set_value("payment_terms_template", payment_terms_template);
					me.frm.refresh_field("payment_terms_template");
				}
			}
		);
	}

	apply_tds(frm) {
		var me = this;
		me.frm.set_value("tax_withheld_vouchers", []);
		if (!me.frm.doc.apply_tds) {
			me.frm.set_value("tax_withholding_category", "");
			me.frm.set_df_property("tax_withholding_category", "hidden", 1);
		} else {
			me.frm.set_value("tax_withholding_category", me.frm.supplier_tds);
			me.frm.set_df_property("tax_withholding_category", "hidden", 0);
		}
	}

	tax_withholding_category(frm) {
		var me = this;
		let filtered_taxes = (me.frm.doc.taxes || []).filter((row) => !row.is_tax_withholding_account);
		me.frm.clear_table("taxes");

		filtered_taxes.forEach((row) => {
			me.frm.add_child("taxes", row);
		});

		me.frm.refresh_field("taxes");
	}

	credit_to() {
		var me = this;
		if (this.frm.doc.credit_to) {
			me.frm.call({
				method: "frappe.client.get_value",
				args: {
					doctype: "Account",
					fieldname: "account_currency",
					filters: { name: me.frm.doc.credit_to },
				},
				callback: function (r, rt) {
					if (r.message) {
						me.frm.set_value("party_account_currency", r.message.account_currency);
						me.set_dynamic_labels();
					}
				},
			});
		}
	}

	make_inter_company_invoice(frm) {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.make_inter_company_sales_invoice",
			frm: frm,
		});
	}

	is_paid() {
		hide_fields(this.frm.doc);
		if (cint(this.frm.doc.is_paid)) {
			this.frm.set_value("allocate_advances_automatically", 0);
			this.frm.set_value("payment_terms_template", "");
			this.frm.set_value("payment_schedule", []);
			if (!this.frm.doc.company) {
				this.frm.set_value("is_paid", 0);
				frappe.msgprint(__("Please specify Company to proceed"));
			}
		} else {
			this.frm.set_value("paid_amount", 0);
		}
		this.calculate_outstanding_amount();
		this.frm.refresh_fields();
	}

	write_off_amount() {
		this.set_in_company_currency(this.frm.doc, ["write_off_amount"]);
		this.calculate_outstanding_amount();
		this.frm.refresh_fields();
	}

	paid_amount() {
		this.set_in_company_currency(this.frm.doc, ["paid_amount"]);
		this.write_off_amount();
		this.frm.refresh_fields();
	}

	allocated_amount() {
		this.calculate_total_advance();
		this.frm.refresh_fields();
	}

	items_add(doc, cdt, cdn) {
		var row = frappe.get_doc(cdt, cdn);
		this.frm.script_manager.copy_from_first_row("items", row, [
			"expense_account",
			"discount_account",
			"cost_center",
			"project",
		]);
	}

	on_submit() {
		super.on_submit();

		$.each(this.frm.doc["items"] || [], function (i, row) {
			if (row.purchase_receipt) frappe.model.clear_doc("Purchase Receipt", row.purchase_receipt);
		});
	}

	make_debit_note() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.make_debit_note",
			frm: this.frm,
		});
	}
};

cur_frm.script_manager.make(erpnext.accounts.PurchaseInvoice);

// Hide Fields
// ------------
function hide_fields(doc) {
	var parent_fields = ["due_date", "is_opening", "advances_section", "from_date", "to_date"];

	if (cint(doc.is_paid) == 1) {
		hide_field(parent_fields);
	} else {
		for (var i in parent_fields) {
			var docfield = frappe.meta.docfield_map[doc.doctype][parent_fields[i]];
			if (!docfield.hidden) unhide_field(parent_fields[i]);
		}
	}

	var item_fields_stock = ["warehouse_section", "received_qty", "rejected_qty"];

	if (cur_frm.fields_dict["items"]) {
		cur_frm.fields_dict["items"].grid.set_column_disp(
			item_fields_stock,
			cint(doc.update_stock) == 1 || cint(doc.is_return) == 1 ? true : false
		);
	}

	cur_frm.refresh_fields();
}

cur_frm.fields_dict.cash_bank_account.get_query = function (doc) {
	return {
		filters: [
			["Account", "account_type", "in", ["Cash", "Bank"]],
			["Account", "is_group", "=", 0],
			["Account", "company", "=", doc.company],
			["Account", "report_type", "=", "Balance Sheet"],
		],
	};
};

cur_frm.fields_dict["items"].grid.get_field("item_code").get_query = function (doc, cdt, cdn) {
	return {
		query: "erpnext.controllers.queries.item_query",
		filters: { is_purchase_item: 1 },
	};
};

cur_frm.fields_dict["credit_to"].get_query = function (doc) {
	// filter on Account
	return {
		filters: {
			account_type: "Payable",
			is_group: 0,
			company: doc.company,
		},
	};
};

// Get Print Heading
cur_frm.fields_dict["select_print_heading"].get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Print Heading", "docstatus", "!=", 2]],
	};
};

cur_frm.set_query("wip_composite_asset", "items", function () {
	return {
		filters: { is_composite_asset: 1, docstatus: 0 },
	};
});

cur_frm.cscript.expense_account = function (doc, cdt, cdn) {
	var d = locals[cdt][cdn];
	if (d.idx == 1 && d.expense_account) {
		var cl = doc.items || [];
		for (var i = 0; i < cl.length; i++) {
			if (!cl[i].expense_account) cl[i].expense_account = d.expense_account;
		}
	}
	refresh_field("items");
};

cur_frm.fields_dict["items"].grid.get_field("cost_center").get_query = function (doc) {
	return {
		filters: {
			company: doc.company,
			is_group: 0,
		},
	};
};

cur_frm.cscript.cost_center = function (doc, cdt, cdn) {
	var d = locals[cdt][cdn];
	if (d.cost_center) {
		var cl = doc.items || [];
		for (var i = 0; i < cl.length; i++) {
			if (!cl[i].cost_center) cl[i].cost_center = d.cost_center;
		}
	}
	refresh_field("items");
};

cur_frm.fields_dict["items"].grid.get_field("project").get_query = function (doc, cdt, cdn) {
	return {
		filters: [["Project", "status", "not in", "Completed, Cancelled"]],
	};
};

frappe.ui.form.on("Purchase Invoice", {
	setup: function (frm) {
		frm.custom_make_buttons = {
			"Purchase Invoice": "Return / Debit Note",
			"Payment Entry": "Payment",
		};

		if (frm.doc.update_stock) {
			frm.custom_make_buttons["Landed Cost Voucher"] = "Landed Cost Voucher";
		}

		frm.set_query("additional_discount_account", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
					report_type: "Profit and Loss",
				},
			};
		});

		frm.fields_dict["items"].grid.get_field("deferred_expense_account").get_query = function (doc) {
			return {
				filters: {
					root_type: "Asset",
					company: doc.company,
					is_group: 0,
				},
			};
		};

		frm.fields_dict["items"].grid.get_field("discount_account").get_query = function (doc) {
			return {
				filters: {
					report_type: "Profit and Loss",
					company: doc.company,
					is_group: 0,
				},
			};
		};
	},

	refresh: function (frm) {
		frm.events.add_custom_buttons(frm);
	},

	mode_of_payment: function (frm) {
		erpnext.accounts.pos.get_payment_mode_account(frm, frm.doc.mode_of_payment, function (account) {
			frm.set_value("cash_bank_account", account);
		});
	},

	add_custom_buttons: function (frm) {
		if (frm.doc.docstatus == 1 && frm.doc.per_received < 100) {
			frm.add_custom_button(
				__("Purchase Receipt"),
				() => {
					frm.events.make_purchase_receipt(frm);
				},
				__("Create")
			);
		}

		if (frm.doc.docstatus == 1 && frm.doc.per_received > 0) {
			frm.add_custom_button(
				__("Purchase Receipt"),
				() => {
					frappe.route_options = {
						purchase_invoice: frm.doc.name,
					};

					frappe.set_route("List", "Purchase Receipt", "List");
				},
				__("View")
			);
		}

		if (frm.doc.docstatus === 1 && frm.doc.update_stock) {
			frm.add_custom_button(
				__("Landed Cost Voucher"),
				() => {
					frm.events.make_lcv(frm);
				},
				__("Create")
			);
		}
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

	onload: function (frm) {
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

		if (frm.is_new()) {
			frm.clear_table("tax_withheld_vouchers");
		}
	},

	is_subcontracted: function (frm) {
		if (frm.doc.is_old_subcontracting_flow) {
			erpnext.buying.get_default_bom(frm);
		}

		frm.toggle_reqd("supplier_warehouse", frm.doc.is_subcontracted);
	},

	update_stock: function (frm) {
		hide_fields(frm.doc);
		frm.fields_dict.items.grid.toggle_reqd("item_code", frm.doc.update_stock ? true : false);
	},

	make_purchase_receipt: function (frm) {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.purchase_invoice.purchase_invoice.make_purchase_receipt",
			frm: frm,
			freeze_message: __("Creating Purchase Receipt ..."),
		});
	},

	company: function (frm) {
		erpnext.accounts.dimensions.update_dimension(frm, frm.doctype);

		if (frm.doc.company) {
			frappe.call({
				method: "erpnext.accounts.party.get_party_account",
				args: {
					party_type: "Supplier",
					party: frm.doc.supplier,
					company: frm.doc.company,
				},
				callback: (response) => {
					if (response) frm.set_value("credit_to", response.message);
				},
			});
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Billed Items To Be Received` | Script Report | Accounts |
| `Supplier Ledger Summary` | Script Report | Accounts |
| `Tax Withholding Details` | Script Report | Accounts |
| `TDS Computation Summary` | Script Report | Accounts |
| `Accounts Payable Summary` | Script Report | Accounts |
| `Received Items To Be Billed` | Script Report | Accounts |
| `Purchase Invoice Trends` | Script Report | Accounts |
| `Item-wise Purchase Register` | Script Report | Accounts |
| `Purchase Register` | Script Report | Accounts |
| `Accounts Payable` | Script Report | Accounts |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Incoming Bills (Purchase Invoice)` | Incoming Bills (Purchase Invoice) | Sum | Accounts |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Incoming Bills` | Total Incoming Bills | Sum | Accounts |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
