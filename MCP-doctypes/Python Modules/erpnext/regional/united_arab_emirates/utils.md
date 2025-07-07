# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/regional/united_arab_emirates/utils.py`

## Classes

No classes found in this file.


## Functions

### `update_itemised_tax_data`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_currency`
**Arguments:** `account`
**Decorators:** ``

**Docstring:**
```
Helper function to get account currency.
```
### `get_tax_accounts`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Get the list of tax accounts for a specific company.
```
### `update_grand_total_for_rcm`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
If the Reverse Charge is Applicable subtract the tax amount from the grand total and update in the form.
```
### `update_totals`
**Arguments:** `vat_tax, base_vat_tax, doc`
**Decorators:** ``

**Docstring:**
```
Update the grand total values in the form.
```
### `make_regional_gl_entries`
**Arguments:** `gl_entries, doc`
**Decorators:** ``

**Docstring:**
```
Hooked to make_regional_gl_entries in Purchase Invoice.It appends the region specific general ledger entries to the list of GL Entries.
```
### `make_gl_entry`
**Arguments:** `tax, gl_entries, doc, tax_accounts`
**Decorators:** ``

**Docstring:**
```

```
### `validate_returns`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Standard Rated expenses should not be set when Reverse Charge Applicable is set.
```

