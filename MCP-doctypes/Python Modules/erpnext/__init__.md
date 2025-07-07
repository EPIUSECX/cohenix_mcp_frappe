# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/__init__.py`

## Classes

No classes found in this file.


## Functions

### `get_default_company`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Get default company for user
```
### `get_default_currency`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Returns the currency of the default company
```
### `get_default_cost_center`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Returns the default cost center of the company
```
### `get_company_currency`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Returns the default company currency
```
### `set_perpetual_inventory`
**Arguments:** `enable, company`
**Decorators:** ``

**Docstring:**
```

```
### `encode_company_abbr`
**Arguments:** `name, company, abbr`
**Decorators:** ``

**Docstring:**
```
Returns name encoded with company abbreviation
```
### `is_perpetual_inventory_enabled`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_finance_book`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_account_type`
**Arguments:** `party_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_region`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Return the default country based on flag, company or global settings

You can also set global company flag in `frappe.flags.company`
```
### `allow_regional`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Decorator to make a function regionally overridable

Example:
@erpnext.allow_regional
def myfunction():
  pass
```
### `check_app_permission`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `normalize_ctx_input`
**Arguments:** `T`
**Decorators:** ``

**Docstring:**
```
Normalizes the first argument (ctx) of the decorated function by:
- Converting Document objects to dictionaries
- Parsing JSON strings
- Casting the result to the specified type T
```

