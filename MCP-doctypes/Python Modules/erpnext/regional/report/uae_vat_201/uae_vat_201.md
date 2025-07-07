# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/regional/report/uae_vat_201/uae_vat_201.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Creates a list of dictionaries that are used to generate column headers of the data table.
```
### `get_data`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the list of dictionaries. Each dictionary is a row in the datatable and chart data.
```
### `append_vat_on_sales`
**Arguments:** `data, filters`
**Decorators:** ``

**Docstring:**
```
Appends Sales and All Other Outputs.
```
### `standard_rated_expenses_emiratewise`
**Arguments:** `data, filters`
**Decorators:** ``

**Docstring:**
```
Append emiratewise standard rated expenses and vat.
```
### `append_emiratewise_expenses`
**Arguments:** `data, emirates, amounts_by_emirate`
**Decorators:** ``

**Docstring:**
```
Append emiratewise standard rated expenses and vat.
```
### `append_vat_on_expenses`
**Arguments:** `data, filters`
**Decorators:** ``

**Docstring:**
```
Appends Expenses and All Other Inputs.
```
### `append_data`
**Arguments:** `data, no, legend, amount, vat_amount`
**Decorators:** ``

**Docstring:**
```
Returns data with appended value.
```
### `get_total_emiratewise`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns Emiratewise Amount and Taxes.
```
### `get_emirates`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Returns a List of emirates in the order that they are to be displayed.
```
### `get_filters`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
The conditions to be used to filter data to calculate the total sale.
```
### `get_reverse_charge_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the total of each Purchase invoice made.
```
### `get_reverse_charge_tax`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the tax of each Purchase invoice made.
```
### `get_reverse_charge_recoverable_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the total of each Purchase invoice made with recoverable reverse charge.
```
### `get_reverse_charge_recoverable_tax`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the tax of each Purchase invoice made.
```
### `get_conditions_join`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
The conditions to be used to filter data to calculate the total vat.
```
### `get_standard_rated_expenses_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the total of each Purchase invoice made with recoverable reverse charge.
```
### `get_standard_rated_expenses_tax`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the tax of each Purchase invoice made.
```
### `get_tourist_tax_return_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the total of each Sales invoice with non zero tourist_tax_return.
```
### `get_tourist_tax_return_tax`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of the tax of each Sales invoice with non zero tourist_tax_return.
```
### `get_zero_rated_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of each Sales Invoice Item Amount which is zero rated.
```
### `get_exempt_total`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
Returns the sum of each Sales Invoice Item Amount which is Vat Exempt.
```
### `get_conditions`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
The conditions to be used to filter data to calculate the total sale.
```

