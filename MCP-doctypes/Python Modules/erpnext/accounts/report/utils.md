# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/report/utils.py`

## Classes

No classes found in this file.


## Functions

### `get_currency`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns a dictionary containing currency information. The keys of the dict are
- company: The company for which we are fetching currency information. if no
company is specified, it will fallback to the default company.
- company currency: The functional currency of the said company.
- presentation currency: The presentation currency to use. Only currencies that
have been used for transactions will be allowed.
- report date: The report date.
:param filters: Report filters
:type filters: dict

:return: str - Currency
```
### `convert`
**Arguments:** `value, from_, to, date`
**Decorators:** ``

**Docstring:**
```
convert `value` from `from_` to `to` on `date`
:param value: Amount to be converted
:param from_: Currency of `value`
:param to: Currency to convert to
:param date: exchange rate as at this date
:return: Result of converting `value`
```
### `get_rate_as_at`
**Arguments:** `date, from_currency, to_currency`
**Decorators:** ``

**Docstring:**
```
Gets exchange rate as at `date` for `from_currency` - `to_currency` exchange rate.
This calls `get_exchange_rate` so that we can get the correct exchange rate as per
the user's Accounts Settings.
It is made efficient by memoising results to `__exchange_rates`
:param date: exchange rate as at this date
:param from_currency: Base currency
:param to_currency: Quote currency
:return: Retrieved exchange rate
```
### `convert_to_presentation_currency`
**Arguments:** `gl_entries, currency_info`
**Decorators:** ``

**Docstring:**
```
Take a list of GL Entries and change the 'debit' and 'credit' values to currencies
in `currency_info`.
:param gl_entries:
:param currency_info:
:return:
```
### `get_appropriate_company`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoiced_item_gross_margin`
**Arguments:** `sales_invoice, item_code, company, with_item_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_query_columns`
**Arguments:** `report_columns`
**Decorators:** ``

**Docstring:**
```

```
### `get_values_for_columns`
**Arguments:** `report_columns, report_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_details`
**Arguments:** `party_type, party_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes_query`
**Arguments:** `invoice_list, doctype, parenttype`
**Decorators:** ``

**Docstring:**
```

```
### `get_journal_entries`
**Arguments:** `filters, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_entries`
**Arguments:** `filters, args`
**Decorators:** ``

**Docstring:**
```

```
### `apply_common_conditions`
**Arguments:** `filters, query, doctype, child_doctype, payments`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_taxes_and_charges`
**Arguments:** `invoice_list`
**Decorators:** ``

**Docstring:**
```

```
### `filter_invoices_based_on_dimensions`
**Arguments:** `filters, query, parent_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_opening_row`
**Arguments:** `party_type, party, from_date, company`
**Decorators:** ``

**Docstring:**
```

```

