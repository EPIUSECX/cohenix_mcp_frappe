# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/consolidated_financial_statement/consolidated_financial_statement.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_balance_sheet_data`
**Arguments:** `fiscal_year, companies, columns, filters`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_companywise_opening_balance`
**Arguments:** `asset_data, liability_data, equity_data, companies`
**Decorators:** ``

**Docstring:**
```

```
### `get_opening_balance`
**Arguments:** `account_name, data, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_root_account_name`
**Arguments:** `root_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_profit_loss_data`
**Arguments:** `fiscal_year, companies, columns, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_income_expense_data`
**Arguments:** `companies, fiscal_year, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_cash_flow_data`
**Arguments:** `fiscal_year, companies, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_type_based_data`
**Arguments:** `account_type, companies, fiscal_year, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `companies, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_data`
**Arguments:** `companies, root_type, balance_must_be, fiscal_year, filters, ignore_closing_entries`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_currency`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_values`
**Arguments:** `accounts_by_name, gl_entries_by_account, companies, filters, fiscal_year`
**Decorators:** ``

**Docstring:**
```

```
### `accumulate_values_into_parents`
**Arguments:** `accounts, accounts_by_name, companies`
**Decorators:** ``

**Docstring:**
```
accumulate children's values in parent accounts
```
### `get_account_heads`
**Arguments:** `root_type, companies, filters`
**Decorators:** ``

**Docstring:**
```

```
### `update_parent_account_names`
**Arguments:** `accounts`
**Decorators:** ``

**Docstring:**
```
Update parent_account_name in accounts list.

parent_name is `name` of parent account which could have other prefix
of account_number and suffix of company abbr. This function adds key called
`parent_account_name` which does not have such prefix/suffix.
```
### `get_companies`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_subsidiary_companies`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_accounts`
**Arguments:** `root_type, companies`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_data`
**Arguments:** `accounts, start_date, end_date, balance_must_be, companies, company_currency, filters`
**Decorators:** ``

**Docstring:**
```

```
### `set_gl_entries_by_account`
**Arguments:** `from_date, to_date, root_lft, root_rgt, filters, gl_entries_by_account, accounts_by_name, accounts, ignore_closing_entries, root_type`
**Decorators:** ``

**Docstring:**
```
Returns a dict like { "account": [gl entries], ... }
```
### `get_account_details`
**Arguments:** `account`
**Decorators:** ``

**Docstring:**
```

```
### `validate_entries`
**Arguments:** `key, entry, accounts_by_name, accounts`
**Decorators:** ``

**Docstring:**
```

```
### `get_additional_conditions`
**Arguments:** `from_date, ignore_closing_entries, filters, d`
**Decorators:** ``

**Docstring:**
```

```
### `add_total_row`
**Arguments:** `out, root_type, balance_must_be, companies, company_currency`
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

