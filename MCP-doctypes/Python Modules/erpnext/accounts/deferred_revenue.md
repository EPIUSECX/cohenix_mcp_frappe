# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/deferred_revenue.py`

## Classes

No classes found in this file.


## Functions

### `validate_service_stop_date`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Validates service_stop_date for Purchase Invoice and Sales Invoice
```
### `build_conditions`
**Arguments:** `process_type, account, company`
**Decorators:** ``

**Docstring:**
```

```
### `convert_deferred_expense_to_expense`
**Arguments:** `deferred_process, start_date, end_date, conditions`
**Decorators:** ``

**Docstring:**
```

```
### `convert_deferred_revenue_to_income`
**Arguments:** `deferred_process, start_date, end_date, conditions`
**Decorators:** ``

**Docstring:**
```

```
### `get_booking_dates`
**Arguments:** `doc, item, posting_date, prev_posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_monthly_amount`
**Arguments:** `doc, item, last_gl_entry, start_date, end_date, total_days, total_booking_days, account_currency`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_amount`
**Arguments:** `doc, item, last_gl_entry, total_days, total_booking_days, account_currency`
**Decorators:** ``

**Docstring:**
```

```
### `get_already_booked_amount`
**Arguments:** `doc, item`
**Decorators:** ``

**Docstring:**
```

```
### `book_deferred_income_or_expense`
**Arguments:** `doc, deferred_process, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `process_deferred_accounting`
**Arguments:** `posting_date`
**Decorators:** ``

**Docstring:**
```
Converts deferred income/expense into income/expense
Executed via background jobs on every month end
```
### `make_gl_entries`
**Arguments:** `doc, credit_account, debit_account, against, amount, base_amount, posting_date, project, account_currency, cost_center, item, deferred_process`
**Decorators:** ``

**Docstring:**
```

```
### `send_mail`
**Arguments:** `deferred_process`
**Decorators:** ``

**Docstring:**
```

```
### `book_revenue_via_journal_entry`
**Arguments:** `doc, credit_account, debit_account, amount, base_amount, posting_date, project, account_currency, cost_center, item, deferred_process, submit`
**Decorators:** ``

**Docstring:**
```

```
### `get_deferred_booking_accounts`
**Arguments:** `doctype, voucher_detail_no, dr_or_cr`
**Decorators:** ``

**Docstring:**
```

```

