# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/utils.py`

## Classes

### `FiscalYearError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PaymentEntryUnlinkError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QueryPaymentLedger`


**Docstring:**
```
Helper Class for Querying Payment Ledger Entry
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `reset` | `self` | `` |  |
| `query_for_outstanding` | `self` | `` | Database query to fetch voucher amount and voucher outstanding using Common Table Expression |
| `get_voucher_outstandings` | `self, vouchers, common_filter, posting_date, min_outstanding, max_outstanding, get_payments, get_invoices, accounting_dimensions, limit, voucher_no` | `` | Fetch voucher amount and outstanding amount from Payment Ledger using Database CTE

vouchers - dict of vouchers to get
common_filter - array of criterions
min_outstanding - filter on minimum total outstanding amount
max_outstanding - filter on maximum total  outstanding amount
get_invoices - only fetch vouchers(ledger entries with +ve outstanding)
get_payments - only fetch payments(ledger entries with -ve outstanding) |





## Functions

### `get_fiscal_year`
**Arguments:** `date, fiscal_year, label, verbose, company, as_dict, boolean, raise_on_missing`
**Decorators:** ``

**Docstring:**
```

```
### `get_fiscal_years`
**Arguments:** `transaction_date, fiscal_year, label, verbose, company, as_dict, boolean, raise_on_missing`
**Decorators:** ``

**Docstring:**
```

```
### `_get_fiscal_years`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_fiscal_year_filter_field`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `validate_fiscal_year`
**Arguments:** `date, fiscal_year, company, label, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_balance_on`
**Arguments:** `account, date, party_type, party, company, in_account_currency, cost_center, ignore_account_permission, account_type, start_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_count_on`
**Arguments:** `account, fieldname, date`
**Decorators:** ``

**Docstring:**
```

```
### `add_ac`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `add_cc`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `_build_dimensions_dict_for_exc_gain_loss`
**Arguments:** `entry, active_dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `reconcile_against_document`
**Arguments:** `args, skip_ref_details_update_for_pe, active_dimensions`
**Decorators:** ``

**Docstring:**
```
Cancel PE or JV, Update against document, split if required and resubmit
```
### `check_if_advance_entry_modified`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
check if there is already a voucher reference
check if amount is same
check if jv is submitted
```
### `validate_allocated_amount`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `update_reference_in_journal_entry`
**Arguments:** `d, journal_entry, do_not_save`
**Decorators:** ``

**Docstring:**
```
Updates against document, if partial amount splits into rows
```
### `update_reference_in_payment_entry`
**Arguments:** `d, payment_entry, do_not_save, skip_ref_details_update_for_pe, dimensions_dict`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_exchange_gain_loss_journal`
**Arguments:** `parent_doc, referenced_dt, referenced_dn`
**Decorators:** ``

**Docstring:**
```
Cancel Exchange Gain/Loss for Sales/Purchase Invoice, if they have any.
```
### `delete_exchange_gain_loss_journal`
**Arguments:** `parent_doc, referenced_dt, referenced_dn`
**Decorators:** ``

**Docstring:**
```
Delete Exchange Gain/Loss for Sales/Purchase Invoice, if they have any.
```
### `get_linked_exchange_gain_loss_journal`
**Arguments:** `referenced_dt, referenced_dn, je_docstatus`
**Decorators:** ``

**Docstring:**
```
Get all the linked exchange gain/loss journal entries for a given document.
```
### `cancel_common_party_journal`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `update_accounting_ledgers_after_reference_removal`
**Arguments:** `ref_type, ref_no, payment_name`
**Decorators:** ``

**Docstring:**
```

```
### `remove_ref_from_advance_section`
**Arguments:** `ref_doc`
**Decorators:** ``

**Docstring:**
```

```
### `unlink_ref_doc_from_payment_entries`
**Arguments:** `ref_doc, payment_name`
**Decorators:** ``

**Docstring:**
```

```
### `remove_ref_doc_link_from_jv`
**Arguments:** `ref_type, ref_no, payment_name`
**Decorators:** ``

**Docstring:**
```

```
### `convert_to_list`
**Arguments:** `result`
**Decorators:** ``

**Docstring:**
```
Convert tuple to list
```
### `remove_ref_doc_link_from_pe`
**Arguments:** `ref_type, ref_no, payment_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_default`
**Arguments:** `company, fieldname, ignore_validation`
**Decorators:** ``

**Docstring:**
```

```
### `fix_total_debit_credit`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_currency_precision`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_held_invoices`
**Arguments:** `party_type, party`
**Decorators:** ``

**Docstring:**
```
Returns a list of names Purchase Invoices for the given party that are on hold
```
### `get_outstanding_invoices`
**Arguments:** `party_type, party, account, common_filter, posting_date, min_outstanding, max_outstanding, accounting_dimensions, vouchers, limit, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_name`
**Arguments:** `account_type, root_type, is_group, account_currency, company`
**Decorators:** ``

**Docstring:**
```
return account based on matching conditions
```
### `get_companies`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
get a list of companies based on permission
```
### `get_children`
**Arguments:** `doctype, parent, company, is_root, include_disabled`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_balances`
**Arguments:** `accounts, company`
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_gateway_account`
**Arguments:** `gateway, payment_channel, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_cost_center`
**Arguments:** `docname, cost_center_name, cost_center_number, company, merge`
**Decorators:** ``

**Docstring:**
```
Renames the document by adding the number as a prefix to the current name and updates
all transaction where it was present.
```
### `validate_field_number`
**Arguments:** `doctype_name, docname, number_value, company, field_name`
**Decorators:** ``

**Docstring:**
```
Validate if the number entered isn't already assigned to some other document.
```
### `get_autoname_with_number`
**Arguments:** `number_value, doc_title, company`
**Decorators:** ``

**Docstring:**
```
append title with prefix as number and suffix as company's abbreviation separated by '-'
```
### `parse_naming_series_variable`
**Arguments:** `doc, variable`
**Decorators:** ``

**Docstring:**
```

```
### `get_coa`
**Arguments:** `doctype, parent, is_root, chart`
**Decorators:** ``

**Docstring:**
```

```
### `update_gl_entries_after`
**Arguments:** `posting_date, posting_time, for_warehouses, for_items, warehouse_account, company`
**Decorators:** ``

**Docstring:**
```

```
### `repost_gle_for_stock_vouchers`
**Arguments:** `stock_vouchers, posting_date, company, warehouse_account, repost_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_delete_pl_entries`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `_delete_gl_entries`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `_delete_accounting_ledger_entries`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```
Remove entries from both General and Payment Ledger for specified Voucher
```
### `sort_stock_vouchers_by_posting_date`
**Arguments:** `stock_vouchers, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_future_stock_vouchers`
**Arguments:** `posting_date, posting_time, for_warehouses, for_items, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_voucherwise_gl_entries`
**Arguments:** `future_stock_vouchers, posting_date`
**Decorators:** ``

**Docstring:**
```
Get voucherwise list of GL entries.

Only fetches GLE fields required for comparing with new GLE.
Check compare_existing_and_expected_gle function below.

returns:
        Dict[Tuple[voucher_type, voucher_no], List[GL Entries]]
```
### `compare_existing_and_expected_gle`
**Arguments:** `existing_gle, expected_gle, precision`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_accounts`
**Arguments:** `company, voucher_type, voucher_no, accounts`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_and_account_balance`
**Arguments:** `account, posting_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_journal_entry`
**Arguments:** `account, stock_adjustment_account, amount`
**Decorators:** ``

**Docstring:**
```

```
### `check_and_delete_linked_reports`
**Arguments:** `report`
**Decorators:** ``

**Docstring:**
```
Check if reports are referenced in Desktop Icon
```
### `create_err_and_its_journals`
**Arguments:** `companies`
**Decorators:** ``

**Docstring:**
```

```
### `auto_create_exchange_rate_revaluation_daily`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Executed by background job
```
### `auto_create_exchange_rate_revaluation_weekly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Executed by background job
```
### `auto_create_exchange_rate_revaluation_monthly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Executed by background job
```
### `get_payment_ledger_entries`
**Arguments:** `gl_entries, cancel`
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_ledger_entry`
**Arguments:** `gl_entries, cancel, adv_adj, update_outstanding, from_repost, partial_cancel`
**Decorators:** ``

**Docstring:**
```

```
### `update_voucher_outstanding`
**Arguments:** `voucher_type, voucher_no, account, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `delink_original_entry`
**Arguments:** `pl_entry, partial_cancel`
**Decorators:** ``

**Docstring:**
```

```
### `create_gain_loss_journal`
**Arguments:** `company, posting_date, party_type, party, party_account, gain_loss_account, exc_gain_loss, dr_or_cr, reverse_dr_or_cr, ref1_dt, ref1_dn, ref1_detail_no, ref2_dt, ref2_dn, ref2_detail_no, cost_center, dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_types_from_account_type`
**Arguments:** `account_type`
**Decorators:** ``

**Docstring:**
```

```
### `run_ledger_health_checks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `sync_auto_reconcile_config`
**Arguments:** `auto_reconciliation_job_trigger`
**Decorators:** ``

**Docstring:**
```

```

