# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/setup_wizard/operations/taxes_setup.py`

## Classes

No classes found in this file.


## Functions

### `setup_taxes_and_charges`
**Arguments:** `company_name, country`
**Decorators:** ``

**Docstring:**
```

```
### `simple_to_detailed`
**Arguments:** `templates`
**Decorators:** ``

**Docstring:**
```
Convert a simple taxes object into a more detailed data structure.

Example input:

{
        "France VAT 20%": {
                "account_name": "VAT 20%",
                "tax_rate": 20,
                "default": 1
        },
        "France VAT 10%": {
                "account_name": "VAT 10%",
                "tax_rate": 10
        }
}
```
### `from_detailed_data`
**Arguments:** `company_name, data`
**Decorators:** ``

**Docstring:**
```
Create Taxes and Charges Templates from detailed data.
```
### `update_regional_tax_settings`
**Arguments:** `country, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_taxes_and_charges_template`
**Arguments:** `company_name, doctype, template`
**Decorators:** ``

**Docstring:**
```

```
### `make_item_tax_template`
**Arguments:** `company_name, template`
**Decorators:** ``

**Docstring:**
```
Create an Item Tax Template.

This requires a separate method because Item Tax Template is structured
differently from Sales and Purchase Tax Templates.
```
### `get_or_create_account`
**Arguments:** `company_name, account`
**Decorators:** ``

**Docstring:**
```
Check if account already exists. If not, create it.
Return a tax account or None.
```
### `get_or_create_tax_group`
**Arguments:** `company_name, root_type`
**Decorators:** ``

**Docstring:**
```

```
### `make_tax_category`
**Arguments:** `tax_category`
**Decorators:** ``

**Docstring:**
```

```

