# Master Control Plan: `Sales Invoice`

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
| Accounts User | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| All | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `customer_section` | None | Section Break | fa fa-user |  |  |  | None | None |
| `naming_series` | Series | Select | ACC-SINV-.YYYY.-
ACC-SINV-RET-.YYYY.- | ✅ |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `customer_name` | Customer Name | Small Text | None |  |  | ✅ | None | None |
| `tax_id` | Tax Id | Data | None |  |  | ✅ | None | None |
| `company` | Company | Link | Company | ✅ |  |  | None | None |
| `company_tax_id` | Company Tax ID | Data | None |  |  | ✅ | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `posting_date` | Date | Date | None | ✅ |  |  | Today | None |
| `posting_time` | Posting Time | Time | None |  |  |  | None | None |
| `set_posting_time` | Edit Posting Date and Time | Check | None |  |  |  | 0 | None |
| `due_date` | Payment Due Date | Date | None |  |  |  | None | None |
| `column_break_14` | None | Column Break | None |  |  |  | None | None |
| `is_pos` | Include Payment (POS) | Check | None |  |  |  | 0 | None |
| `pos_profile` | POS Profile | Link | POS Profile |  |  |  | None | None |
| `is_consolidated` | Is Consolidated | Check | None |  |  | ✅ | 0 | None |
| `is_return` | Is Return (Credit Note) | Check | None |  |  |  | 0 | None |
| `return_against` | Return Against | Link | Sales Invoice |  |  |  | None | None |
| `update_outstanding_for_self` | Update Outstanding for Self | Check | None |  |  |  | 1 | Credit Note will update it's own outstanding amount, even if 'Return Against' is specified. |
| `update_billed_amount_in_sales_order` | Update Billed Amount in Sales Order | Check | None |  |  |  | 0 | None |
| `update_billed_amount_in_delivery_note` | Update Billed Amount in Delivery Note | Check | None |  |  |  | 1 | None |
| `is_debit_note` | Is Rate Adjustment Entry (Debit Note) | Check | None |  |  |  | 0 | Issue a debit note with 0 qty against an existing Sales Invoice |
| `amended_from` | Amended From | Link | Sales Invoice |  |  | ✅ | None | None |
| `is_created_using_pos` | Is created using POS | Check | None |  | ✅ |  | 0 | None |
| `pos_closing_entry` | POS Closing Entry | Link | POS Closing Entry |  | ✅ |  | None | None |
| `accounting_dimensions_section` | Accounting Dimensions | Section Break | None |  |  |  | None | None |
| `cost_center` | Cost Center | Link | Cost Center |  |  |  | None | None |
| `dimension_col_break` | None | Column Break | None |  |  |  | None | None |
| `project` | Project | Link | Project |  |  |  | None | None |
| `currency_and_price_list` | Currency and Price List | Section Break | None |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `conversion_rate` | Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Customer Currency is converted to customer's base currency |
| `column_break2` | None | Column Break | None |  |  |  | None | None |
| `selling_price_list` | Price List | Link | Price List | ✅ |  |  | None | None |
| `price_list_currency` | Price List Currency | Link | Currency | ✅ |  | ✅ | None | None |
| `plc_conversion_rate` | Price List Exchange Rate | Float | None | ✅ |  |  | None | Rate at which Price list currency is converted to customer's base currency |
| `ignore_pricing_rule` | Ignore Pricing Rule | Check | None |  |  |  | 0 | None |
| `items_section` | Items | Section Break | fa fa-shopping-cart |  |  |  | None | None |
| `scan_barcode` | Scan Barcode | Data | Barcode |  |  |  | None | None |
| `update_stock` | Update Stock | Check | None |  |  |  | 0 | None |
| `column_break_39` | None | Column Break | None |  |  |  | None | None |
| `set_warehouse` | Source Warehouse | Link | Warehouse |  |  |  | None | None |
| `set_target_warehouse` | Set Target Warehouse | Link | Warehouse |  |  |  | None | None |
| `section_break_42` | None | Section Break | None |  |  |  | None | None |
| `items` | Items | Table | Sales Invoice Item | ✅ |  |  | None | None |
| `section_break_30` | None | Section Break | None |  |  |  | None | None |
| `total_qty` | Total Quantity | Float | None |  |  | ✅ | None | None |
| `total_net_weight` | Total Net Weight | Float | None |  |  | ✅ | None | None |
| `column_break_32` | None | Column Break | None |  |  |  | None | None |
| `base_total` | Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_net_total` | Net Total (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `column_break_52` | None | Column Break | None |  |  |  | None | None |
| `total` | Total | Currency | currency |  |  | ✅ | None | None |
| `net_total` | Net Total | Currency | currency |  |  | ✅ | None | None |
| `taxes_section` | Taxes and Charges | Section Break | fa fa-money |  |  |  | None | None |
| `tax_category` | Tax Category | Link | Tax Category |  |  |  | None | None |
| `taxes_and_charges` | Sales Taxes and Charges Template | Link | Sales Taxes and Charges Template |  |  |  | None | None |
| `column_break_38` | None | Column Break | None |  |  |  | None | None |
| `shipping_rule` | Shipping Rule | Link | Shipping Rule |  |  |  | None | None |
| `column_break_55` | None | Column Break | None |  |  |  | None | None |
| `incoterm` | Incoterm | Link | Incoterm |  |  |  | None | None |
| `named_place` | Named Place | Data | None |  |  |  | None | None |
| `section_break_40` | None | Section Break | None |  |  |  | None | None |
| `taxes` | Sales Taxes and Charges | Table | Sales Taxes and Charges |  |  |  | None | None |
| `section_break_43` | None | Section Break | None |  |  |  | None | None |
| `base_total_taxes_and_charges` | Total Taxes and Charges (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_47` | None | Column Break | None |  |  |  | None | None |
| `total_taxes_and_charges` | Total Taxes and Charges | Currency | currency |  |  | ✅ | None | None |
| `totals` | Totals | Section Break | fa fa-money |  |  |  | None | None |
| `base_grand_total` | Grand Total (Company Currency) | Currency | Company:company:default_currency | ✅ |  | ✅ | None | None |
| `base_rounding_adjustment` | Rounding Adjustment (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_rounded_total` | Rounded Total (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `base_in_words` | In Words (Company Currency) | Small Text | None |  |  | ✅ | None | In Words will be visible once you save the Sales Invoice. |
| `column_break5` | None | Column Break | None |  |  |  | None | None |
| `grand_total` | Grand Total | Currency | currency | ✅ |  | ✅ | None | None |
| `rounding_adjustment` | Rounding Adjustment | Currency | currency |  |  | ✅ | None | None |
| `use_company_roundoff_cost_center` | Use Company default Cost Center for Round off | Check | None |  |  |  | 0 | None |
| `rounded_total` | Rounded Total | Currency | currency |  |  | ✅ | None | None |
| `in_words` | In Words | Small Text | None |  |  | ✅ | None | None |
| `total_advance` | Total Advance | Currency | party_account_currency |  |  | ✅ | None | None |
| `outstanding_amount` | Outstanding Amount | Currency | party_account_currency |  |  | ✅ | None | None |
| `disable_rounded_total` | Disable Rounded Total | Check | None |  |  |  | 0 | None |
| `section_break_49` | Additional Discount | Section Break | None |  |  |  | None | None |
| `apply_discount_on` | Apply Additional Discount On | Select | 
Grand Total
Net Total |  |  |  | Grand Total | None |
| `base_discount_amount` | Additional Discount Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `coupon_code` | Coupon Code | Link | Coupon Code |  |  |  | None | None |
| `is_cash_or_non_trade_discount` | Is Cash or Non Trade Discount | Check | None |  |  |  | 0 | None |
| `additional_discount_account` | Discount Account | Link | Account |  | ✅ |  | None | None |
| `column_break_51` | None | Column Break | None |  |  |  | None | None |
| `additional_discount_percentage` | Additional Discount Percentage | Float | None |  |  |  | None | None |
| `discount_amount` | Additional Discount Amount | Currency | currency |  |  |  | None | None |
| `sec_tax_breakup` | Tax Breakup | Section Break | None |  |  |  | None | None |
| `other_charges_calculation` | Taxes and Charges Calculation | Text Editor | None |  |  | ✅ | None | None |
| `pricing_rule_details` | Pricing Rules | Section Break | None |  |  |  | None | None |
| `pricing_rules` | Pricing Rule Detail | Table | Pricing Rule Detail |  |  | ✅ | None | None |
| `packing_list` | Packing List | Section Break | fa fa-suitcase |  |  |  | None | None |
| `packed_items` | Packed Items | Table | Packed Item |  |  |  | None | None |
| `product_bundle_help` | Product Bundle Help | HTML | None |  |  |  | None | None |
| `time_sheet_list` | Time Sheet List | Section Break | None |  |  |  | None | None |
| `timesheets` | Time Sheets | Table | Sales Invoice Timesheet |  |  |  | None | None |
| `section_break_104` | None | Section Break | None |  |  |  | None | None |
| `total_billing_hours` | Total Billing Hours | Float | None |  |  | ✅ | None | None |
| `column_break_106` | None | Column Break | None |  |  |  | None | None |
| `total_billing_amount` | Total Billing Amount | Currency | currency |  |  | ✅ | 0 | None |
| `payments_tab` | Payments | Tab Break | None |  |  |  | None | None |
| `payments_section` | Payments | Section Break | fa fa-money |  |  |  | None | None |
| `cash_bank_account` | Cash/Bank Account | Link | Account |  | ✅ |  | None | None |
| `payments` | Sales Invoice Payment | Table | Sales Invoice Payment |  |  |  | None | None |
| `section_break_84` | None | Section Break | None |  |  |  | None | None |
| `base_paid_amount` | Paid Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_86` | None | Column Break | None |  |  |  | None | None |
| `paid_amount` | Paid Amount | Currency | currency |  |  | ✅ | None | None |
| `section_break_88` | Changes | Section Break | None |  |  |  | None | None |
| `base_change_amount` | Base Change Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_90` | None | Column Break | None |  |  |  | None | None |
| `change_amount` | Change Amount | Currency | currency |  |  |  | None | None |
| `account_for_change_amount` | Account for Change Amount | Link | Account |  |  |  | None | None |
| `advances_section` | Advance Payments | Section Break | fa fa-money |  |  |  | None | None |
| `allocate_advances_automatically` | Allocate Advances Automatically (FIFO) | Check | None |  |  |  | 0 | None |
| `only_include_allocated_payments` | Only Include Allocated Payments | Check | None |  |  |  | 0 | Advance payments allocated against orders will only be fetched |
| `get_advances` | Get Advances Received | Button | set_advances |  |  |  | None | None |
| `advances` | Advances | Table | Sales Invoice Advance |  |  |  | None | None |
| `write_off_section` | Write Off | Section Break | None |  |  |  | None | None |
| `write_off_amount` | Write Off Amount | Currency | currency |  |  |  | None | None |
| `base_write_off_amount` | Write Off Amount (Company Currency) | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `write_off_outstanding_amount_automatically` | Write Off Outstanding Amount | Check | None |  |  |  | 0 | None |
| `column_break_74` | None | Column Break | None |  |  |  | None | None |
| `write_off_account` | Write Off Account | Link | Account |  |  |  | None | None |
| `write_off_cost_center` | Write Off Cost Center | Link | Cost Center |  |  |  | None | None |
| `loyalty_points_redemption` | Loyalty Points Redemption | Section Break | None |  |  |  | None | None |
| `redeem_loyalty_points` | Redeem Loyalty Points | Check | None |  |  |  | 0 | None |
| `loyalty_points` | Loyalty Points | Int | None |  |  |  | None | None |
| `loyalty_amount` | Loyalty Amount | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break_77` | None | Column Break | None |  |  |  | None | None |
| `loyalty_program` | Loyalty Program | Link | Loyalty Program |  |  |  | None | None |
| `dont_create_loyalty_points` | Don't Create Loyalty Points | Check | None |  |  |  | 0 | None |
| `loyalty_redemption_account` | Redemption Account | Link | Account |  |  |  | None | None |
| `loyalty_redemption_cost_center` | Redemption Cost Center | Link | Cost Center |  |  |  | None | None |
| `contact_and_address_tab` | Address & Contact | Tab Break | None |  |  |  | None | None |
| `address_and_contact` | Billing Address | Section Break | None |  |  |  | None | None |
| `customer_address` | Customer Address | Link | Address |  |  |  | None | None |
| `address_display` | Address | Text Editor | None |  |  | ✅ | None | None |
| `col_break4` | None | Column Break | None |  |  |  | None | None |
| `contact_person` | Contact Person | Link | Contact |  |  |  | None | None |
| `contact_display` | Contact | Small Text | None |  |  | ✅ | None | None |
| `contact_mobile` | Mobile No | Small Text | Phone |  | ✅ | ✅ | None | None |
| `contact_email` | Contact Email | Data | Email |  | ✅ | ✅ | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `shipping_address_section` | Shipping Address | Section Break | None |  |  |  | None | None |
| `shipping_address_name` | Shipping Address Name | Link | Address |  |  |  | None | None |
| `shipping_address` | Shipping Address | Text Editor | None |  |  | ✅ | None | None |
| `shipping_addr_col_break` | None | Column Break | None |  |  |  | None | None |
| `dispatch_address_name` | Dispatch Address Name | Link | Address |  |  |  | None | None |
| `dispatch_address` | Dispatch Address | Text Editor | None |  |  | ✅ | None | None |
| `company_address_section` | Company Address | Section Break | None |  |  |  | None | None |
| `company_address` | Company Address Name | Link | Address |  |  |  | None | None |
| `company_address_display` | Company Address | Text Editor | None |  |  | ✅ | None | None |
| `company_addr_col_break` | None | Column Break | None |  |  |  | None | None |
| `company_contact_person` | Company Contact Person | Link | Contact |  |  |  | None | None |
| `terms_tab` | Terms | Tab Break | None |  |  |  | None | None |
| `payment_schedule_section` | Payment Terms | Section Break | None |  |  |  | None | None |
| `ignore_default_payment_terms_template` | Ignore Default Payment Terms Template | Check | None |  | ✅ | ✅ | 0 | None |
| `payment_terms_template` | Payment Terms Template | Link | Payment Terms Template |  |  |  | None | None |
| `payment_schedule` | Payment Schedule | Table | Payment Schedule |  |  |  | None | None |
| `terms_section_break` | Terms and Conditions | Section Break | None |  |  |  | None | None |
| `tc_name` | Terms | Link | Terms and Conditions |  |  |  | None | None |
| `terms` | Terms and Conditions Details | Text Editor | None |  |  |  | None | None |
| `more_info_tab` | More Info | Tab Break | None |  |  |  | None | None |
| `customer_po_details` | Customer PO Details | Section Break | None |  |  |  | None | None |
| `po_no` | Customer's Purchase Order | Data | None |  |  |  | None | None |
| `column_break_23` | None | Column Break | None |  |  |  | None | None |
| `po_date` | Customer's Purchase Order Date | Date | None |  |  |  | None | None |
| `more_info` | Accounting Details | Section Break | fa fa-file-text |  |  |  | None | None |
| `debit_to` | Debit To | Link | Account | ✅ |  |  | None | None |
| `party_account_currency` | Party Account Currency | Link | Currency |  | ✅ | ✅ | None | None |
| `is_opening` | Is Opening Entry | Select | No
Yes |  |  |  | No | None |
| `column_break8` | None | Column Break | None |  |  |  | None | None |
| `unrealized_profit_loss_account` | Unrealized Profit / Loss Account | Link | Account |  |  |  | None | Unrealized Profit / Loss account for intra-company transfers |
| `against_income_account` | Against Income Account | Small Text | None |  | ✅ |  | None | None |
| `sales_team_section_break` | Commission | Section Break | fa fa-group |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `amount_eligible_for_commission` | Amount Eligible for Commission | Currency | Company:company:default_currency |  |  | ✅ | None | None |
| `column_break10` | None | Column Break | None |  |  |  | None | None |
| `commission_rate` | Commission Rate (%) | Float | None |  |  |  | None | None |
| `total_commission` | Total Commission | Currency | Company:company:default_currency |  |  |  | None | None |
| `section_break2` | Sales Team | Section Break | None |  |  |  | None | None |
| `sales_team` | Sales Contributions and Incentives | Table | Sales Team |  |  |  | None | None |
| `edit_printing_settings` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |
| `group_same_items` | Group same items | Check | None |  |  |  | 0 | None |
| `column_break_84` | None | Column Break | None |  |  |  | None | None |
| `select_print_heading` | Print Heading | Link | Print Heading |  |  |  | None | None |
| `language` | Print Language | Link | Language |  |  | ✅ | None | None |
| `subscription_section` | Subscription | Section Break | None |  |  |  | None | None |
| `subscription` | Subscription | Link | Subscription |  |  |  | None | None |
| `from_date` | From Date | Date | None |  |  |  | None | None |
| `auto_repeat` | Auto Repeat | Link | Auto Repeat |  |  | ✅ | None | None |
| `column_break_140` | None | Column Break | None |  |  |  | None | None |
| `to_date` | To Date | Date | None |  |  |  | None | None |
| `update_auto_repeat_reference` | Update Auto Repeat Reference | Button | None |  |  |  | None | None |
| `more_information` | Additional Info | Section Break | None |  |  |  | None | None |
| `status` | Status | Select | 
Draft
Return
Credit Note Issued
Submitted
Paid
Partly Paid
Unpaid
Unpaid and Discounted
Partly Paid and Discounted
Overdue and Discounted
Overdue
Cancelled
Internal Transfer |  |  | ✅ | Draft | None |
| `inter_company_invoice_reference` | Inter Company Invoice Reference | Link | Purchase Invoice |  |  | ✅ | None | None |
| `represents_company` | Represents Company | Link | Company |  |  | ✅ | None | Company which internal customer represents |
| `customer_group` | Customer Group | Link | Customer Group |  | ✅ |  | None | None |
| `column_break_imbx` | None | Column Break | None |  |  |  | None | None |
| `utm_source` | Source | Link | UTM Source |  |  |  | None | None |
| `utm_campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `utm_medium` | Medium | Link | UTM Medium |  |  |  | None | None |
| `utm_content` | Content | Data | None |  |  |  | None | None |
| `col_break23` | None | Column Break | None |  |  |  | None | None |
| `is_internal_customer` | Is Internal Customer | Check | None |  |  | ✅ | 0 | None |
| `is_discounted` | Is Discounted | Check | None |  |  | ✅ | 0 | None |
| `remarks` | Remarks | Small Text | None |  |  |  | None | None |
| `connections_tab` | Connections | Tab Break | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 50
- **Dynamic Link Fields:** 0
- **Table Fields:** 9

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/sales_invoice/sales_invoice.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.provide("erpnext.accounts");

cur_frm.cscript.tax_table = "Sales Taxes and Charges";

erpnext.accounts.taxes.setup_tax_validations("Sales Invoice");
erpnext.accounts.payment_triggers.setup("Sales Invoice");
erpnext.accounts.pos.setup("Sales Invoice");
erpnext.accounts.taxes.setup_tax_filters("Sales Taxes and Charges");
erpnext.sales_common.setup_selling_controller();
erpnext.accounts.SalesInvoiceController = class SalesInvoiceController extends (
	erpnext.selling.SellingController
) {
	setup(doc) {
		this.setup_posting_date_time_check();
		super.setup(doc);
		this.frm.make_methods = {
			Dunning: this.make_dunning.bind(this),
			"Invoice Discounting": this.make_invoice_discounting.bind(this),
		};
	}
	company() {
		super.company();
		erpnext.accounts.dimensions.update_dimension(this.frm, this.frm.doctype);
	}
	onload() {
		var me = this;
		super.onload();

		this.frm.ignore_doctypes_on_cancel_all = [
			"POS Invoice",
			"Timesheet",
			"POS Invoice Merge Log",
			"POS Closing Entry",
			"Journal Entry",
			"Payment Entry",
			"Repost Payment Ledger",
			"Repost Accounting Ledger",
			"Unreconcile Payment",
			"Unreconcile Payment Entries",
			"Serial and Batch Bundle",
			"Bank Transaction",
		];

		if (!this.frm.doc.__islocal && !this.frm.doc.customer && this.frm.doc.debit_to) {
			// show debit_to in print format
			this.frm.set_df_property("debit_to", "print_hide", 0);
		}

		erpnext.queries.setup_queries(this.frm, "Warehouse", function () {
			return erpnext.queries.warehouse(me.frm.doc);
		});

		if (this.frm.doc.__islocal && this.frm.doc.is_pos) {
			//Load pos profile data on the invoice if the default value of Is POS is 1

			me.frm.script_manager.trigger("is_pos");
			me.frm.refresh_fields();
		}
		erpnext.queries.setup_warehouse_query(this.frm);
	}

	refresh(doc, dt, dn) {
		const me = this;
		super.refresh();
		if (this.frm?.msgbox && this.frm.msgbox.$wrapper.is(":visible")) {
			// hide new msgbox
			this.frm.msgbox.hide();
		}

		this.frm.toggle_reqd("due_date", !this.frm.doc.is_return);

		if (this.frm.doc.is_return) {
			this.frm.return_print_format = "Sales Invoice Return";
		}

		this.show_general_ledger();
		erpnext.accounts.ledger_preview.show_accounting_ledger_preview(this.frm);

		if (doc.update_stock) {
			this.show_stock_ledger();
			erpnext.accounts.ledger_preview.show_stock_ledger_preview(this.frm);
		}

		if (doc.docstatus == 1 && doc.outstanding_amount != 0) {
			this.frm.add_custom_button(__("Payment"), () => this.make_payment_entry(), __("Create"));
			this.frm.page.set_inner_btn_group_as_primary(__("Create"));
		}

		if (doc.docstatus == 1 && !doc.is_return) {
			var is_delivered_by_supplier = false;

			is_delivered_by_supplier = this.frm.doc.items.some(function (item) {
				return item.is_delivered_by_supplier ? true : false;
			});

			if (doc.outstanding_amount >= 0 || Math.abs(flt(doc.outstanding_amount)) < flt(doc.grand_total)) {
				this.frm.add_custom_button(
					__("Return / Credit Note"),
					this.make_sales_return.bind(this),
					__("Create")
				);
				this.frm.page.set_inner_btn_group_as_primary(__("Create"));
			}

			if (cint(doc.update_stock) != 1) {
				// show Make Delivery Note button only if Sales Invoice is not created from Delivery Note
				var from_delivery_note = false;
				from_delivery_note = this.frm.doc.items.some(function (item) {
					return item.delivery_note ? true : false;
				});

				if (!from_delivery_note && !is_delivered_by_supplier) {
					this.frm.add_custom_button(
						__("Delivery"),
						this.frm.cscript["Make Delivery Note"],
						__("Create")
					);
				}
			}

			if (doc.outstanding_amount > 0) {
				this.frm.add_custom_button(
					__("Payment Request"),
					function () {
						me.make_payment_request();
					},
					__("Create")
				);
				this.frm.add_custom_button(
					__("Invoice Discounting"),
					this.make_invoice_discounting.bind(this),
					__("Create")
				);

				const payment_is_overdue = doc.payment_schedule
					.map((row) => Date.parse(row.due_date) < Date.now())
					.reduce((prev, current) => prev || current, false);

				if (payment_is_overdue) {
					this.frm.add_custom_button(__("Dunning"), this.make_dunning.bind(this), __("Create"));
				}
			}

			if (doc.docstatus === 1) {
				this.frm.add_custom_button(
					__("Maintenance Schedule"),
					this.make_maintenance_schedule.bind(this),
					__("Create")
				);
			}
		}

		// Show buttons only when pos view is active
		if (cint(doc.docstatus == 0) && this.frm.page.current_view_name !== "pos" && !doc.is_return) {
			this.frm.cscript.sales_order_btn();
			this.frm.cscript.delivery_note_btn();
			this.frm.cscript.quotation_btn();
		}

		this.set_default_print_format();
		if (doc.docstatus == 1 && !doc.inter_company_invoice_reference) {
			let internal = me.frm.doc.is_internal_customer;
			if (internal) {
				let button_label =
					me.frm.doc.company === me.frm.doc.represents_company
						? "Internal Purchase Invoice"
						: "Inter Company Purchase Invoice";

				me.frm.add_custom_button(
					button_label,
					function () {
						me.make_inter_company_invoice();
					},
					__("Create")
				);
			}
		}

		erpnext.accounts.unreconcile_payment.add_unreconcile_btn(me.frm);

		if (this.frm.doc.is_created_using_pos && !this.frm.doc.is_return) {
			erpnext.accounts.dimensions.update_dimension(this.frm, this.frm.doctype);
		}
	}

	make_invoice_discounting() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.create_invoice_discounting",
			frm: this.frm,
		});
	}

	make_dunning() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.create_dunning",
			frm: this.frm,
		});
	}

	make_maintenance_schedule() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.make_maintenance_schedule",
			frm: this.frm,
		});
	}

	on_submit(doc, dt, dn) {
		var me = this;

		super.on_submit();
		if (frappe.get_route()[0] != "Form") {
			return;
		}

		doc.items.forEach((row) => {
			if (row.delivery_note) frappe.model.clear_doc("Delivery Note", row.delivery_note);
		});
	}

	set_default_print_format() {
		// set default print format to POS type or Credit Note
		if (this.frm.doc.is_pos) {
			if (this.frm.pos_print_format) {
				this.frm.meta._default_print_format = this.frm.meta.default_print_format;
				this.frm.meta.default_print_format = this.frm.pos_print_format;
			}
		} else if (this.frm.doc.is_return && !this.frm.meta.default_print_format) {
			if (this.frm.return_print_format) {
				this.frm.meta._default_print_format = this.frm.meta.default_print_format;
				this.frm.meta.default_print_format = this.frm.return_print_format;
			}
		} else {
			if (this.frm.meta._default_print_format) {
				this.frm.meta.default_print_format = this.frm.meta._default_print_format;
				this.frm.meta._default_print_format = null;
			} else if (
				[this.frm.pos_print_format, this.frm.return_print_format].includes(
					this.frm.meta.default_print_format
				)
			) {
				this.frm.meta.default_print_format = null;
				this.frm.meta._default_print_format = null;
			}
		}
	}

	sales_order_btn() {
		var me = this;
		this.$sales_order_btn = this.frm.add_custom_button(
			__("Sales Order"),
			function () {
				erpnext.utils.map_current_doc({
					method: "erpnext.selling.doctype.sales_order.sales_order.make_sales_invoice",
					source_doctype: "Sales Order",
					target: me.frm,
					setters: {
						customer: me.frm.doc.customer || undefined,
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
	}

	quotation_btn() {
		var me = this;
		this.$quotation_btn = this.frm.add_custom_button(
			__("Quotation"),
			function () {
				erpnext.utils.map_current_doc({
					method: "erpnext.selling.doctype.quotation.quotation.make_sales_invoice",
					source_doctype: "Quotation",
					target: me.frm,
					setters: [
						{
							fieldtype: "Link",
							label: __("Customer"),
							options: "Customer",
							fieldname: "party_name",
							default: me.frm.doc.customer,
						},
					],
					get_query_filters: {
						docstatus: 1,
						status: ["!=", "Lost"],
						company: me.frm.doc.company,
					},
				});
			},
			__("Get Items From")
		);
	}

	delivery_note_btn() {
		var me = this;
		this.$delivery_note_btn = this.frm.add_custom_button(
			__("Delivery Note"),
			function () {
				erpnext.utils.map_current_doc({
					method: "erpnext.stock.doctype.delivery_note.delivery_note.make_sales_invoice",
					source_doctype: "Delivery Note",
					target: me.frm,
					date_field: "posting_date",
					setters: {
						customer: me.frm.doc.customer || undefined,
					},
					get_query: function () {
						var filters = {
							docstatus: 1,
							company: me.frm.doc.company,
							is_return: 0,
						};
						if (me.frm.doc.customer) filters["customer"] = me.frm.doc.customer;
						return {
							query: "erpnext.controllers.queries.get_delivery_notes_to_be_billed",
							filters: filters,
						};
					},
				});
			},
			__("Get Items From")
		);
	}

	tc_name() {
		this.get_terms();
	}
	customer() {
		if (this.frm.doc.is_pos) {
			var pos_profile = this.frm.doc.pos_profile;
		}
		var me = this;
		if (this.frm.updating_party_details) return;

		if (this.frm.doc.__onload && this.frm.doc.__onload.load_after_mapping) return;

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
				fetch_payment_terms_template: cint(
					(this.frm.doc.is_return == 0) & !this.frm.doc.ignore_default_payment_terms_template
				),
			},
			function () {
				me.apply_pricing_rule();
			}
		);

		if (this.frm.doc.customer) {
			frappe.call({
				method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.get_loyalty_programs",
				args: {
					customer: this.frm.doc.customer,
				},
				callback: function (r) {
					if (r.message && r.message.length > 1) {
						select_loyalty_program(me.frm, r.message);
					}
				},
			});
		}
	}

	make_inter_company_invoice() {
		let me = this;
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.make_inter_company_purchase_invoice",
			frm: me.frm,
		});
	}

	debit_to() {
		var me = this;
		if (this.frm.doc.debit_to) {
			me.frm.call({
				method: "frappe.client.get_value",
				args: {
					doctype: "Account",
					fieldname: "account_currency",
					filters: { name: me.frm.doc.debit_to },
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

	allocated_amount() {
		this.calculate_total_advance();
		this.frm.refresh_fields();
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

	write_off_amount() {
		this.set_in_company_currency(this.frm.doc, ["write_off_amount"]);
		this.write_off_outstanding_amount_automatically();
	}

	items_add(doc, cdt, cdn) {
		var row = frappe.get_doc(cdt, cdn);
		this.frm.script_manager.copy_from_first_row("items", row, [
			"income_account",
			"discount_account",
			"cost_center",
		]);
	}

	set_dynamic_labels() {
		super.set_dynamic_labels();
		this.frm.events.hide_fields(this.frm);
	}

	items_on_form_rendered() {
		erpnext.setup_serial_or_batch_no();
	}

	packed_items_on_form_rendered(doc, grid_row) {
		erpnext.setup_serial_or_batch_no();
	}

	make_sales_return() {
		frappe.model.open_mapped_doc({
			method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.make_sales_return",
			frm: this.frm,
		});
	}

	asset(frm, cdt, cdn) {
		var row = locals[cdt][cdn];
		if (row.asset) {
			frappe.call({
				method: erpnext.assets.doctype.asset.depreciation.get_disposal_account_and_cost_center,
				args: {
					company: frm.doc.company,
				},
				callback: function (r, rt) {
					frappe.model.set_value(cdt, cdn, "income_account", r.message[0]);
					frappe.model.set_value(cdt, cdn, "cost_center", r.message[1]);
				},
			});
		}
	}

	is_pos(frm) {
		this.set_pos_data();
	}

	pos_profile() {
		this.frm.doc.taxes = [];
		this.set_pos_data();
	}

	set_pos_data() {
		if (this.frm.doc.is_pos) {
			this.frm.set_value("allocate_advances_automatically", 0);
			if (!this.frm.doc.company) {
				this.frm.set_value("is_pos", 0);
				frappe.msgprint(__("Please specify Company to proceed"));
			} else {
				var me = this;
				const for_validate = me.frm.doc.is_return ? true : false;
				return this.frm.call({
					doc: me.frm.doc,
					method: "set_missing_values",
					args: {
						for_validate: for_validate,
					},
					callback: function (r) {
						if (!r.exc) {
							if (r.message && r.message.print_format) {
								me.frm.pos_print_format = r.message.print_format;
							}
							me.frm.trigger("update_stock");
							if (me.frm.doc.taxes_and_charges) {
								me.frm.script_manager.trigger("taxes_and_charges");
							}

							frappe.model.set_default_values(me.frm.doc);
							me.set_dynamic_labels();
							me.calculate_taxes_and_totals();
						}
					},
				});
			}
		} else this.frm.trigger("refresh");
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

	currency() {
		var me = this;
		super.currency();
		if (this.frm.doc.timesheets) {
			this.frm.doc.timesheets.forEach((d) => {
				let row = frappe.get_doc(d.doctype, d.name);
				set_timesheet_detail_rate(row.doctype, row.name, me.frm.doc.currency, row.timesheet_detail);
			});
			this.frm.trigger("calculate_timesheet_totals");
		}
	}

	is_cash_or_non_trade_discount() {
		this.frm.set_df_property(
			"additional_discount_account",
			"hidden",
			1 - this.frm.doc.is_cash_or_non_trade_discount
		);
		this.frm.set_df_property(
			"additional_discount_account",
			"reqd",
			this.frm.doc.is_cash_or_non_trade_discount
		);

		if (!this.frm.doc.is_cash_or_non_trade_discount) {
			this.frm.set_value("additional_discount_account", "");
		}

		this.calculate_taxes_and_totals();
	}
};

// for backward compatibility: combine new and previous states
extend_cscript(cur_frm.cscript, new erpnext.accounts.SalesInvoiceController({ frm: cur_frm }));

cur_frm.cscript["Make Delivery Note"] = function () {
	frappe.model.open_mapped_doc({
		method: "erpnext.accounts.doctype.sales_invoice.sales_invoice.make_delivery_note",
		frm: cur_frm,
	});
};

cur_frm.cscript.income_account = function (doc, cdt, cdn) {
	erpnext.utils.copy_value_in_all_rows(doc, cdt, cdn, "items", "income_account");
};

cur_frm.cscript.expense_account = function (doc, cdt, cdn) {
	erpnext.utils.copy_value_in_all_rows(doc, cdt, cdn, "items", "expense_account");
};

cur_frm.cscript.cost_center = function (doc, cdt, cdn) {
	erpnext.utils.copy_value_in_all_rows(doc, cdt, cdn, "items", "cost_center");
};

frappe.ui.form.on("Sales Invoice", {
	setup: function (frm) {
		frm.add_fetch("customer", "tax_id", "tax_id");
		frm.add_fetch("payment_term", "invoice_portion", "invoice_portion");
		frm.add_fetch("payment_term", "description", "description");

		frm.set_df_property("packed_items", "cannot_add_rows", true);
		frm.set_df_property("packed_items", "cannot_delete_rows", true);

		frm.set_query("cash_bank_account", function (doc) {
			return {
				filters: [
					["Account", "account_type", "in", ["Cash", "Bank"]],
					["Account", "root_type", "=", "Asset"],
					["Account", "is_group", "=", 0],
					["Account", "company", "=", doc.company],
				],
			};
		});

		frm.set_query("write_off_account", function (doc) {
			return {
				filters: {
					report_type: "Profit and Loss",
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("write_off_cost_center", function (doc) {
			return {
				filters: {
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("cost_center", "items", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("debit_to", function (doc) {
			return {
				filters: {
					account_type: "Receivable",
					is_group: 0,
					company: doc.company,
				},
			};
		});

		frm.set_query("asset", "items", function (doc, cdt, cdn) {
			const row = locals[cdt][cdn];
			return {
				filters: [
					["Asset", "item_code", "=", row.item_code],
					["Asset", "docstatus", "=", 1],
					["Asset", "status", "in", ["Submitted", "Partially Depreciated", "Fully Depreciated"]],
					["Asset", "company", "=", doc.company],
				],
			};
		});

		frm.set_query("account_for_change_amount", function (doc) {
			return {
				filters: {
					account_type: ["in", ["Cash", "Bank"]],
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("unrealized_profit_loss_account", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
					root_type: "Liability",
				},
			};
		});

		frm.set_query("adjustment_against", function (doc) {
			return {
				filters: {
					company: doc.company,
					customer: doc.customer,
					docstatus: 1,
				},
			};
		});

		frm.set_query("additional_discount_account", function (doc) {
			return {
				filters: {
					company: doc.company,
					is_group: 0,
					report_type: "Profit and Loss",
				},
			};
		});

		frm.set_query("income_account", "items", function (doc) {
			return {
				query: "erpnext.controllers.queries.get_income_account",
				filters: {
					company: doc.company,
					disabled: 0,
				},
			};
		});

		frm.custom_make_buttons = {
			"Delivery Note": "Delivery",
			"Sales Invoice": "Return / Credit Note",
			"Payment Request": "Payment Request",
			"Payment Entry": "Payment",
		};

		frm.set_query("time_sheet", "timesheets", function (doc, cdt, cdn) {
			return {
				query: "erpnext.projects.doctype.timesheet.timesheet.get_timesheet",
				filters: { project: doc.project },
			};
		});

		frm.set_query("discount_account", "items", function (doc) {
			return {
				filters: {
					report_type: "Profit and Loss",
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("deferred_revenue_account", "items", function (doc) {
			return {
				filters: {
					root_type: "Liability",
					company: doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("pos_profile", function (doc) {
			if (!doc.company) {
				frappe.throw(__("Please set Company"));
			}

			return {
				query: "erpnext.accounts.doctype.pos_profile.pos_profile.pos_profile_query",
				filters: {
					company: doc.company,
				},
			};
		});

		frm.set_query("loyalty_redemption_account", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});

		frm.set_query("loyalty_redemption_cost_center", function () {
			return {
				filters: {
					company: frm.doc.company,
					is_group: 0,
				},
			};
		});
	},
	onload: function (frm) {
		frm.redemption_conversion_factor = null;
	},

	update_stock: function (frm, dt, dn) {
		frm.events.hide_fields(frm);
		frm.trigger("reset_posting_time");
	},

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

	hide_fields: function (frm) {
		let doc = frm.doc;
		var parent_fields = [
			"project",
			"due_date",
			"is_opening",
			"utm_source",
			"utm_campaign",
			"utm_medium",
			"total_advance",
			"get_advances",
			"advances",
			"from_date",
			"to_date",
		];

		if (cint(doc.is_pos) == 1) {
			hide_field(parent_fields);
		} else {
			for (var i in parent_fields) {
				var docfield = frappe.meta.docfield_map[doc.doctype][parent_fields[i]];
				if (!docfield.hidden) unhide_field(parent_fields[i]);
			}
		}

		frm.refresh_fields();
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

	project: function (frm) {
		if (frm.doc.project) {
			frappe.call({
				method: "is_auto_fetch_timesheet_enabled",
				doc: frm.doc,
				callback: function (r) {
					if (cint(r.message)) {
						frm.events.add_timesheet_data(frm, {
							project: frm.doc.project,
						});
					}
				},
			});
		}
	},

	async add_timesheet_data(frm, kwargs) {
		if (kwargs === "Sales Invoice") {
			// called via frm.trigger()
			kwargs = Object();
		}

		if (!Object.prototype.hasOwnProperty.call(kwargs, "project") && frm.doc.project) {
			kwargs.project = frm.doc.project;
		}

		const timesheets = await frm.events.get_timesheet_data(frm, kwargs);

		if (kwargs.item_code) {
			frm.events.add_timesheet_item(frm, kwargs.item_code, timesheets);
		}

		return frm.events.set_timesheet_data(frm, timesheets);
	},

	add_timesheet_item: function (frm, item_code, timesheets) {
		const row = frm.add_child("items");
		frappe.model.set_value(row.doctype, row.name, "item_code", item_code);
		frappe.model.set_value(
			row.doctype,
			row.name,
			"qty",
			timesheets.reduce((a, b) => a + (b["billing_hours"] || 0.0), 0.0)
		);
	},

	async get_timesheet_data(frm, kwargs) {
		return frappe
			.call({
				method: "erpnext.projects.doctype.timesheet.timesheet.get_projectwise_timesheet_data",
				args: kwargs,
			})
			.then((r) => {
				if (!r.exc && r.message.length > 0) {
					return r.message;
				} else {
					return [];
				}
			});
	},

	set_timesheet_data: function (frm, timesheets) {
		frm.clear_table("timesheets");
		timesheets.forEach(async (timesheet) => {
			if (frm.doc.currency != timesheet.currency) {
				const exchange_rate = await frm.events.get_exchange_rate(
					frm,
					timesheet.currency,
					frm.doc.currency
				);
				frm.events.append_time_log(frm, timesheet, exchange_rate);
			} else {
				frm.events.append_time_log(frm, timesheet, 1.0);
			}
		});
		frm.trigger("calculate_timesheet_totals");
		frm.refresh();
	},

	async get_exchange_rate(frm, from_currency, to_currency) {
		if (
			frm.exchange_rates &&
			frm.exchange_rates[from_currency] &&
			frm.exchange_rates[from_currency][to_currency]
		) {
			return frm.exchange_rates[from_currency][to_currency];
		}

		return frappe.call({
			method: "erpnext.setup.utils.get_exchange_rate",
			args: {
				from_currency,
				to_currency,
			},
			callback: function (r) {
				if (r.message) {
					// cache exchange rates
					frm.exchange_rates = frm.exchange_rates || {};
					frm.exchange_rates[from_currency] = frm.exchange_rates[from_currency] || {};
					frm.exchange_rates[from_currency][to_currency] = r.message;
				}
			},
		});
	},

	append_time_log: function (frm, time_log, exchange_rate) {
		const row = frm.add_child("timesheets");
		row.activity_type = time_log.activity_type;
		row.description = time_log.description;
		row.time_sheet = time_log.time_sheet;
		row.from_time = time_log.from_time;
		row.to_time = time_log.to_time;
		row.billing_hours = time_log.billing_hours;
		row.billing_amount = flt(time_log.billing_amount) * flt(exchange_rate);
		row.timesheet_detail = time_log.name;
		row.project_name = time_log.project_name;
	},

	calculate_timesheet_totals: function (frm) {
		frm.set_value(
			"total_billing_amount",
			frm.doc.timesheets.reduce((a, b) => a + (b["billing_amount"] || 0.0), 0.0)
		);
		frm.set_value(
			"total_billing_hours",
			frm.doc.timesheets.reduce((a, b) => a + (b["billing_hours"] || 0.0), 0.0)
		);
	},

	refresh: function (frm) {
		if (frm.doc.docstatus === 0 && !frm.doc.is_return) {
			frm.add_custom_button(
				__("Timesheet"),
				function () {
					let d = new frappe.ui.Dialog({
						title: __("Fetch Timesheet"),
						fields: [
							{
								label: __("From"),
								fieldname: "from_time",
								fieldtype: "Date",
								reqd: 1,
							},
							{
								label: __("Item Code"),
								fieldname: "item_code",
								fieldtype: "Link",
								options: "Item",
								get_query: () => {
									return {
										query: "erpnext.controllers.queries.item_query",
										filters: {
											is_sales_item: 1,
											customer: frm.doc.customer,
											has_variants: 0,
										},
									};
								},
							},
							{
								fieldtype: "Column Break",
								fieldname: "col_break_1",
							},
							{
								label: __("To"),
								fieldname: "to_time",
								fieldtype: "Date",
								reqd: 1,
							},
							{
								label: __("Project"),
								fieldname: "project",
								fieldtype: "Link",
								options: "Project",
								default: frm.doc.project,
							},
						],
						primary_action: function () {
							const data = d.get_values();
							frm.events.add_timesheet_data(frm, {
								from_time: data.from_time,
								to_time: data.to_time,
								project: data.project,
								item_code: data.item_code,
							});
							d.hide();
						},
						primary_action_label: __("Get Timesheets"),
					});
					d.show();
				},
				__("Get Items From")
			);
		}

		if (frm.doc.is_debit_note) {
			frm.set_df_property("return_against", "label", __("Adjustment Against"));
		}
	},
});

frappe.ui.form.on("Sales Invoice Timesheet", {
	timesheets_remove(frm) {
		frm.trigger("calculate_timesheet_totals");
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

var set_timesheet_detail_rate = function (cdt, cdn, currency, timelog) {
	frappe.call({
		method: "erpnext.projects.doctype.timesheet.timesheet.get_timesheet_detail_rate",
		args: {
			timelog: timelog,
			currency: currency,
		},
		callback: function (r) {
			if (!r.exc && r.message) {
				frappe.model.set_value(cdt, cdn, "billing_amount", r.message);
			}
		},
	});
};

var select_loyalty_program = function (frm, loyalty_programs) {
	var dialog = new frappe.ui.Dialog({
		title: __("Select Loyalty Program"),
		fields: [
			{
				label: __("Loyalty Program"),
				fieldname: "loyalty_program",
				fieldtype: "Select",
				options: loyalty_programs,
				default: loyalty_programs[0],
			},
		],
	});

	dialog.set_primary_action(__("Set Loyalty Program"), function () {
		dialog.hide();
		return frappe.call({
			method: "frappe.client.set_value",
			args: {
				doctype: "Customer",
				name: frm.doc.customer,
				fieldname: "loyalty_program",
				value: dialog.get_value("loyalty_program"),
			},
			callback: function (r) {},
		});
	});

	dialog.show();
};

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Inactive Sales Items` | Script Report | Accounts |
| `Electronic Invoice Register` | Script Report | Regional |
| `Customer Ledger Summary` | Script Report | Accounts |
| `Customers Without Any Sales Transactions` | Query Report | Selling |
| `Sales Payment Summary` | Script Report | Accounts |
| `Accounts Receivable Summary` | Script Report | Accounts |
| `Delivered Items To Be Billed` | Script Report | Accounts |
| `Sales Invoice Trends` | Script Report | Accounts |
| `Item-wise Sales Register` | Script Report | Accounts |
| `Sales Partners Commission` | Query Report | Accounts |
| `Sales Register` | Script Report | Accounts |
| `Accounts Receivable` | Script Report | Accounts |
| `Gross Profit` | Script Report | Accounts |



### Dashboard Charts
| Name | Chart Name | Type | Module |
|---|---|---|---|
| `Outgoing Bills (Sales Invoice)` | Outgoing Bills (Sales Invoice) | Sum | Accounts |



### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Total Outgoing Bills` | Total Outgoing Bills | Sum | Accounts |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
