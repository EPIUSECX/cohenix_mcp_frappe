# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/period_closing_voucher/period_closing_voucher.py`

## Classes

### `PeriodClosingVoucher`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_start_and_end_date` | `self` | `` |  |
| `check_if_previous_year_closed` | `self` | `` |  |
| `block_if_future_closing_voucher_exists` | `self` | `` |  |
| `get_future_closing_voucher` | `self` | `` |  |
| `check_closing_account_type` | `self` | `` |  |
| `check_closing_account_currency` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `make_gl_entries` | `self` | `` |  |
| `get_pcv_gl_entries` | `self` | `` |  |
| `get_gle_for_pl_account` | `self, acc, balances, dimensions` | `` |  |
| `get_gle_for_closing_account` | `self, dimension_balance, dimensions` | `` |  |
| `update_default_dimensions` | `self, gl_entry, dimensions` | `` |  |
| `get_account_balances_based_on_dimensions` | `self, report_type` | `` | Get balance for dimension-wise pl accounts |
| `get_accounting_dimension_fields` | `self` | `` |  |
| `get_gl_entries_for_current_period` | `self, report_type, only_opening_entries, as_iterator` | `` |  |
| `set_account_balance_dict` | `self, gle, acc_bal_dict` | `` |  |
| `get_key` | `self, gle` | `` |  |
| `get_account_closing_balances` | `self` | `` |  |
| `get_closing_entries_for_pl_accounts` | `self` | `` |  |
| `get_closing_entries_for_balance_sheet_accounts` | `self` | `` |  |
| `get_closing_entry` | `self, account, balances, dimensions` | `` |  |
| `get_closing_entries_for_closing_account` | `self` | `` |  |
| `is_first_period_closing_voucher` | `self` | `` |  |
| `cancel_gl_entries` | `self` | `` |  |
| `get_gle_count_against_current_pcv` | `self` | `` |  |





## Functions

### `process_gl_and_closing_entries`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `process_cancellation`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `delete_closing_entries`
**Arguments:** `voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_period_start_end_date`
**Arguments:** `fiscal_year, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_previous_closed_period_in_current_year`
**Arguments:** `fiscal_year, company`
**Decorators:** ``

**Docstring:**
```

```

