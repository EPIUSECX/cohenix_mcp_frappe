# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/financial_statements.py`

## Classes

No classes found in this file.


## Functions

### `get_period_list`
**Arguments:** `from_fiscal_year, to_fiscal_year, period_start_date, period_end_date, filter_based_on, periodicity, accumulated_values, company, reset_period_on_fy_change, ignore_fiscal_year`
**Decorators:** ``

**Docstring:**
```
Get a list of dict {"from_date": from_date, "to_date": to_date, "key": key, "label": label}
Periodicity can be (Yearly, Quarterly, Monthly)
```
### `get_fiscal_year_data`
**Arguments:** `from_fiscal_year, to_fiscal_year`
**Decorators:** ``

**Docstring:**
```

```
### `validate_fiscal_year`
**Arguments:** `fiscal_year, from_fiscal_year, to_fiscal_year`
**Decorators:** ``

**Docstring:**
```

```
### `validate_dates`
**Arguments:** `from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_months`
**Arguments:** `start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_label`
**Arguments:** `periodicity, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_data`
**Arguments:** `company, root_type, balance_must_be, period_list, filters, accumulated_values, only_current_fiscal_year, ignore_closing_entries, ignore_accumulated_values_for_fy, total`
**Decorators:** ``

**Docstring:**
```

```
### `get_appropriate_currency`
**Arguments:** `company, filters`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_values`
**Arguments:** `accounts_by_name, gl_entries_by_account, period_list, accumulated_values, ignore_accumulated_values_for_fy`
**Decorators:** ``

**Docstring:**
```

```
### `accumulate_values_into_parents`
**Arguments:** `accounts, accounts_by_name, period_list`
**Decorators:** ``

**Docstring:**
```
accumulate children's values in parent accounts
```
### `prepare_data`
**Arguments:** `accounts, balance_must_be, period_list, company_currency, accumulated_values`
**Decorators:** ``

**Docstring:**
```

```
### `filter_out_zero_value_rows`
**Arguments:** `data, parent_children_map, show_zero_values`
**Decorators:** ``

**Docstring:**
```

```
### `add_total_row`
**Arguments:** `out, root_type, balance_must_be, period_list, company_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_accounts`
**Arguments:** `company, root_type`
**Decorators:** ``

**Docstring:**
```

```
### `filter_accounts`
**Arguments:** `accounts, depth`
**Decorators:** ``

**Docstring:**
```

```
### `sort_accounts`
**Arguments:** `accounts, is_root, key`
**Decorators:** ``

**Docstring:**
```
Sort root types as Asset, Liability, Equity, Income, Expense
```
### `set_gl_entries_by_account`
**Arguments:** `company, from_date, to_date, filters, gl_entries_by_account, root_lft, root_rgt, root_type, ignore_closing_entries, ignore_opening_entries, group_by_account`
**Decorators:** ``

**Docstring:**
```
Returns a dict like { "account": [gl entries], ... }
```
### `get_accounting_entries`
**Arguments:** `doctype, from_date, to_date, filters, root_lft, root_rgt, root_type, ignore_closing_entries, period_closing_voucher, ignore_opening_entries, group_by_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_filter_query`
**Arguments:** `root_lft, root_rgt, root_type, gl_entry`
**Decorators:** ``

**Docstring:**
```

```
### `apply_additional_conditions`
**Arguments:** `doctype, query, from_date, ignore_closing_entries, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_cost_centers_with_children`
**Arguments:** `cost_centers`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `periodicity, period_list, accumulated_values, company, cash_flow`
**Decorators:** ``

**Docstring:**
```

```
### `get_filtered_list_for_consolidated_report`
**Arguments:** `filters, period_list`
**Decorators:** ``

**Docstring:**
```

```
### `compute_growth_view_data`
**Arguments:** `data, columns`
**Decorators:** ``

**Docstring:**
```

```
### `compute_margin_view_data`
**Arguments:** `data, columns, accumulated_values`
**Decorators:** ``

**Docstring:**
```

```

