# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/journal_entry/journal_entry.py`

## Classes

### `StockAccountInvalidTransaction`


**Docstring:**
```

```

**Methods:**
No methods found.

### `JournalEntry`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_advance_accounts` | `self` | `` |  |
| `validate_for_repost` | `self` | `` |  |
| `submit` | `self` | `` |  |
| `cancel` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `get_balance_for_periodic_accounting` | `self` | `` |  |
| `validate_company_for_periodic_accounting` | `self` | `` |  |
| `get_stock_accounts_for_periodic_accounting` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `get_title` | `self` | `` |  |
| `update_advance_paid` | `self` | `` |  |
| `validate_inter_company_accounts` | `self` | `` |  |
| `validate_depr_account_and_depr_entry_voucher_type` | `self` | `` |  |
| `validate_stock_accounts` | `self` | `` |  |
| `apply_tax_withholding` | `self` | `` |  |
| `update_asset_value` | `self` | `` |  |
| `update_asset_on_depreciation` | `self` | `` |  |
| `update_value_after_depreciation` | `self, asset, depr_amount` | `` |  |
| `update_journal_entry_link_on_depr_schedule` | `self, asset, je_row` | `` |  |
| `update_asset_on_disposal` | `self` | `` |  |
| `update_inter_company_jv` | `self` | `` |  |
| `update_invoice_discounting` | `self` | `` |  |
| `unlink_advance_entry_reference` | `self` | `` |  |
| `unlink_asset_reference` | `self` | `` |  |
| `unlink_inter_company_jv` | `self` | `` |  |
| `unlink_asset_adjustment_entry` | `self` | `` |  |
| `validate_party` | `self` | `` |  |
| `check_credit_limit` | `self` | `` |  |
| `validate_cheque_info` | `self` | `` |  |
| `validate_entries_for_advance` | `self` | `` |  |
| `system_generated_gain_loss` | `self` | `` |  |
| `validate_against_jv` | `self` | `` |  |
| `validate_reference_doc` | `self` | `` | Validates reference document |
| `validate_orders` | `self` | `` | Validate totals, closed and docstatus for orders |
| `validate_invoices` | `self` | `` | Validate totals and docstatus for invoices |
| `set_against_account` | `self` | `` |  |
| `validate_debit_credit_amount` | `self` | `` |  |
| `validate_total_debit_and_credit` | `self` | `` |  |
| `set_total_debit_credit` | `self` | `` |  |
| `validate_multi_currency` | `self` | `` |  |
| `set_amounts_in_company_currency` | `self` | `` |  |
| `set_exchange_rate` | `self` | `` |  |
| `create_remarks` | `self` | `` |  |
| `set_print_format_fields` | `self` | `` |  |
| `set_total_amount` | `self, amt, currency` | `` |  |
| `build_gl_map` | `self` | `` |  |
| `make_gl_entries` | `self, cancel, adv_adj` | `` |  |
| `get_balance` | `self, difference_account` | `` |  |
| `get_outstanding_invoices` | `self` | `` |  |
| `get_values` | `self` | `` |  |
| `validate_credit_debit_note` | `self` | `` |  |
| `validate_empty_accounts_table` | `self` | `` |  |





## Functions

### `get_default_bank_cash_account`
**Arguments:** `company, account_type, mode_of_payment, account`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entry_against_order`
**Arguments:** `dt, dn, amount, debit_in_account_currency, journal_entry, bank_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entry_against_invoice`
**Arguments:** `dt, dn, amount, debit_in_account_currency, journal_entry, bank_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entry`
**Arguments:** `ref_doc, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_against_jv`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_outstanding`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_account_and_currency`
**Arguments:** `company, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_details_and_party_type`
**Arguments:** `account, date, company, debit, credit, exchange_rate`
**Decorators:** ``

**Docstring:**
```
Returns dict of account details and party type to be set in Journal Entry on selection of account.
```
### `get_exchange_rate`
**Arguments:** `posting_date, account, account_currency, company, reference_type, reference_name, debit, credit, exchange_rate`
**Decorators:** ``

**Docstring:**
```

```
### `get_average_exchange_rate`
**Arguments:** `account`
**Decorators:** ``

**Docstring:**
```

```
### `make_inter_company_journal_entry`
**Arguments:** `name, voucher_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_reverse_journal_entry`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```

