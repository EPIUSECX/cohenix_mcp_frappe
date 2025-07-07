# Master Control Plan: `Accounts Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Sales User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `invoice_and_billing_tab` | Invoice and Billing | Tab Break | None |  |  |  | None | None |
| `enable_features_section` | Invoice Cancellation | Section Break | None |  |  |  | None | None |
| `unlink_payment_on_cancellation_of_invoice` | Unlink Payment on Cancellation of Invoice | Check | None |  |  |  | 1 | None |
| `unlink_advance_payment_on_cancelation_of_order` | Unlink Advance Payment on Cancellation of Order | Check | None |  |  |  | 1 | None |
| `column_break_13` | None | Column Break | None |  |  |  | None | None |
| `delete_linked_ledger_entries` | Delete Accounting and Stock Ledger Entries on deletion of Transaction | Check | None |  |  |  | 0 | None |
| `enable_immutable_ledger` | Enable Immutable Ledger | Check | None |  |  |  | 0 | On enabling this cancellation entries will be posted on the actual cancellation date and reports will consider cancelled entries as well |
| `invoicing_features_section` | Invoicing Features | Section Break | None |  |  |  | None | None |
| `check_supplier_invoice_uniqueness` | Check Supplier Invoice Number Uniqueness | Check | None |  |  |  | 0 | Enabling this ensures each Purchase Invoice has a unique value in Supplier Invoice No. field within a particular fiscal year |
| `automatically_fetch_payment_terms` | Automatically Fetch Payment Terms from Order | Check | None |  |  |  | 0 | Payment Terms from orders will be fetched into the invoices as is |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `enable_common_party_accounting` | Enable Common Party Accounting | Check | None |  |  |  | 0 | Learn about <a href="https://docs.erpnext.com/docs/v13/user/manual/en/accounts/articles/common_party_accounting#:~:text=Common%20Party%20Accounting%20in%20ERPNext,Invoice%20against%20a%20primary%20Supplier.">Common Party</a> |
| `allow_multi_currency_invoices_against_single_party_account` | Allow multi-currency invoices against single party account  | Check | None |  |  |  | 0 | Enabling this will allow creation of multi-currency invoices against single party account in company currency |
| `confirm_before_resetting_posting_date` | Confirm before resetting posting date | Check | None |  |  |  | 1 | If enabled, user will be alerted before resetting posting date to current date in relevant transactions |
| `journals_section` | Journals | Section Break | None |  |  |  | None | None |
| `merge_similar_account_heads` | Merge Similar Account Heads | Check | None |  |  |  | 0 | Rows with Same Account heads will be merged on Ledger |
| `deferred_accounting_settings_section` | Deferred Accounting Settings | Section Break | None |  |  |  | None | None |
| `book_deferred_entries_based_on` | Book Deferred Entries Based On | Select | Days
Months |  |  |  | Days | If "Months" is selected, a fixed amount will be booked as deferred revenue or expense for each month irrespective of the number of days in a month. It will be prorated if deferred revenue or expense is not booked for an entire month |
| `column_break_18` | None | Column Break | None |  |  |  | None | None |
| `automatically_process_deferred_accounting_entry` | Automatically Process Deferred Accounting Entry | Check | None |  |  |  | 1 | None |
| `book_deferred_entries_via_journal_entry` | Book Deferred Entries Via Journal Entry | Check | None |  |  |  | 0 | If this is unchecked, direct GL entries will be created to book deferred revenue or expense |
| `submit_journal_entries` | Submit Journal Entries | Check | None |  |  |  | 0 | If this is unchecked Journal Entries will be saved in a Draft state and will have to be submitted manually |
| `tax_settings_section` | Tax Settings | Section Break | None |  |  |  | None | None |
| `determine_address_tax_category_from` | Determine Address Tax Category From | Select | Billing Address
Shipping Address |  |  |  | Billing Address | Address used to determine Tax Category in transactions |
| `column_break_19` | None | Column Break | None |  |  |  | None | None |
| `add_taxes_from_item_tax_template` | Automatically Add Taxes and Charges from Item Tax Template | Check | None |  |  |  | 1 | None |
| `add_taxes_from_taxes_and_charges_template` | Automatically Add Taxes from Taxes and Charges Template | Check | None |  |  |  | 0 | If no taxes are set, and Taxes and Charges Template is selected, the system will automatically apply the taxes from the chosen template. |
| `book_tax_discount_loss` | Book Tax Loss on Early Payment Discount | Check | None |  |  |  | 0 | Split Early Payment Discount Loss into Income and Tax Loss |
| `round_row_wise_tax` | Round Tax Amount Row-wise | Check | None |  |  |  | 0 | Tax Amount will be rounded on a row(items) level |
| `print_settings` | Print Settings | Section Break | None |  |  |  | None | None |
| `show_inclusive_tax_in_print` | Show Inclusive Tax in Print | Check | None |  |  |  | 0 | None |
| `show_taxes_as_table_in_print` | Show Taxes as Table in Print | Check | None |  |  |  | 0 | None |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `show_payment_schedule_in_print` | Show Payment Schedule in Print | Check | None |  |  |  | 0 | None |
| `item_price_settings_section` | Item Price Settings | Section Break | None |  |  |  | None | None |
| `maintain_same_internal_transaction_rate` | Maintain Same Rate Throughout Internal Transaction | Check | None |  |  |  | 0 | None |
| `column_break_feyo` | None | Column Break | None |  |  |  | None | None |
| `maintain_same_rate_action` | Action if Same Rate is Not Maintained Throughout  Internal Transaction | Select | Stop
Warn |  |  |  | Stop | None |
| `role_to_override_stop_action` | Role Allowed to Override Stop Action | Link | Role |  |  |  | None | None |
| `currency_exchange_section` | Currency Exchange Settings | Section Break | None |  |  |  | None | None |
| `allow_stale` | Allow Stale Exchange Rates | Check | None |  |  |  | 1 | None |
| `allow_pegged_currencies_exchange_rates` | Allow Implicit Pegged Currency Conversion | Check | None |  |  |  | 0 | System will do an implicit conversion using the pegged currency. <br>
Ex: Instead of AED -&gt; INR, system will do AED -&gt; USD -&gt; INR using the pegged exchange rate of AED against USD. |
| `column_break_yuug` | None | Column Break | None |  |  |  | None | None |
| `stale_days` | Stale Days | Int | None |  |  |  | 1 | None |
| `section_break_jpd0` | Payment Reconciliation Settings | Section Break | None |  |  |  | None | None |
| `auto_reconcile_payments` | Auto Reconcile Payments | Check | None |  |  |  | 0 | None |
| `auto_reconciliation_job_trigger` | Auto Reconciliation Job Trigger | Int | None |  |  |  | 15 | Interval should be between 1 to 59 MInutes |
| `reconciliation_queue_size` | Reconciliation Queue Size | Int | None |  |  |  | 5 | Documents Processed on each trigger. Queue Size should be between 5 and 100 |
| `column_break_resa` | None | Column Break | None |  |  |  | None | None |
| `exchange_gain_loss_posting_date` | Posting Date Inheritance for Exchange Gain / Loss | Select | Invoice
Payment
Reconciliation Date |  |  |  | Payment | Only applies for Normal Payments |
| `invoicing_settings_tab` | Credit Limits | Tab Break | None |  |  |  | None | None |
| `accounts_transactions_settings_section` | Credit Limit Settings | Section Break | None |  |  |  | None | None |
| `over_billing_allowance` | Over Billing Allowance (%) | Currency | None |  |  |  | None | The percentage you are allowed to bill more against the amount ordered. For example, if the order value is $100 for an item and tolerance is set as 10%, then you are allowed to bill up to $110  |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `role_allowed_to_over_bill` | Role Allowed to Over Bill  | Link | Role |  |  |  | None | Users with this role are allowed to over bill above the allowance percentage |
| `credit_controller` | Role allowed to bypass Credit Limit | Link | Role |  |  |  | None | None |
| `make_payment_via_journal_entry` | Make Payment via Journal Entry | Check | None |  | ✅ |  | 0 | None |
| `pos_tab` | POS | Tab Break | None |  |  |  | None | None |
| `pos_setting_section` | POS Setting | Section Break | None |  |  |  | None | None |
| `post_change_gl_entries` | Create Ledger Entries for Change Amount | Check | None |  |  |  | 1 | If enabled, ledger entries will be posted for change amount in POS transactions |
| `column_break_xrnd` | None | Column Break | None |  |  |  | None | None |
| `assets_tab` | Assets | Tab Break | None |  |  |  | None | None |
| `asset_settings_section` | Asset Settings | Section Break | None |  |  |  | None | None |
| `calculate_depr_using_total_days` | Calculate daily depreciation using total days in depreciation period | Check | None |  |  |  | 0 | Enable this option to calculate daily depreciation by considering the total number of days in the entire depreciation period, (including leap years) while using daily pro-rata based depreciation |
| `column_break_gjcc` | None | Column Break | None |  |  |  | None | None |
| `book_asset_depreciation_entry_automatically` | Book Asset Depreciation Entry Automatically | Check | None |  |  |  | 1 | None |
| `closing_settings_tab` | Accounts Closing | Tab Break | None |  |  |  | None | None |
| `period_closing_settings_section` | Period Closing Settings | Section Break | None |  |  |  | None | None |
| `acc_frozen_upto` | Accounts Frozen Till Date | Date | None |  |  |  | None | Accounting entries are frozen up to this date. Nobody can create or modify entries except users with the role specified below |
| `ignore_account_closing_balance` | Ignore Account Closing Balance | Check | None |  |  |  | 0 | Financial reports will be generated using GL Entry doctypes (should be enabled if Period Closing Voucher is not posted for all years sequentially or missing)  |
| `column_break_25` | None | Column Break | None |  |  |  | None | None |
| `frozen_accounts_modifier` | Role Allowed to Set Frozen Accounts and Edit Frozen Entries | Link | Role |  |  |  | None | Users with this role are allowed to set frozen accounts and create / modify accounting entries against frozen accounts |
| `tab_break_dpet` | Chart Of Accounts | Tab Break | None |  |  |  | None | None |
| `show_balance_in_coa` | Show Balances in Chart Of Accounts | Check | None |  |  |  | 1 | None |
| `banking_tab` | Banking | Tab Break | None |  |  |  | None | None |
| `enable_party_matching` | Enable Automatic Party Matching | Check | None |  |  |  | 0 | Auto match and set the Party in Bank Transactions |
| `enable_fuzzy_matching` | Enable Fuzzy Matching | Check | None |  |  |  | 0 | Approximately match the description/party name against parties |
| `reports_tab` | Reports | Tab Break | None |  |  |  | None | None |
| `remarks_section` | Remarks Column Length | Section Break | None |  |  |  | None | None |
| `general_ledger_remarks_length` | General Ledger | Int | None |  |  |  | 0 | Truncates 'Remarks' column to set character length |
| `column_break_lvjk` | None | Column Break | None |  |  |  | None | None |
| `receivable_payable_remarks_length` | Accounts Receivable/Payable | Int | None |  |  |  | 0 | Truncates 'Remarks' column to set character length |
| `accounts_receivable_payable_tuning_section` | Accounts Receivable / Payable Tuning | Section Break | None |  |  |  | None | None |
| `receivable_payable_fetch_method` | Data Fetch Method | Select | Buffered Cursor
UnBuffered Cursor |  |  |  | Buffered Cursor | None |
| `legacy_section` | Legacy Fields | Section Break | None |  |  |  | None | None |
| `ignore_is_opening_check_for_reporting` | Ignore Is Opening check for reporting | Check | None |  |  |  | 0 | Ignores legacy Is Opening field in GL Entry that allows adding opening balance post the system is in use while generating reports |
| `payment_request_settings` | Payment Request | Tab Break | None |  |  |  | None | Payment Request created from Sales Order or Purchase Order will be in Draft status. When disabled document will be in unsaved state. |
| `create_pr_in_draft_status` | Create in Draft Status | Check | None |  |  |  | 1 | None |
| `budget_settings` | Budget | Tab Break | None |  |  |  | None | None |
| `use_new_budget_controller` | Use New Budget Controller | Check | None |  |  |  | 1 | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/accounts_settings/accounts_settings.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Accounts Settings", {
	refresh: function (frm) {},
	enable_immutable_ledger: function (frm) {
		if (!frm.doc.enable_immutable_ledger) {
			return;
		}

		let msg = __("Enabling this will change the way how cancelled transactions are handled.");
		msg += " ";
		msg += __("Please enable only if the understand the effects of enabling this.");
		msg += "<br>";
		msg += __("Do you still want to enable immutable ledger?");

		frappe.confirm(
			msg,
			() => {},
			() => {
				frm.set_value("enable_immutable_ledger", 0);
			}
		);
	},

	add_taxes_from_taxes_and_charges_template(frm) {
		toggle_tax_settings(frm, "add_taxes_from_taxes_and_charges_template");
	},
	add_taxes_from_item_tax_template(frm) {
		toggle_tax_settings(frm, "add_taxes_from_item_tax_template");
	},
});

function toggle_tax_settings(frm, field_name) {
	if (frm.doc[field_name]) {
		const other_field =
			field_name === "add_taxes_from_item_tax_template"
				? "add_taxes_from_taxes_and_charges_template"
				: "add_taxes_from_item_tax_template";
		frm.set_value(other_field, 0);
	}
}

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
