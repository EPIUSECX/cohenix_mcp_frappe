# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/company/company.py`

## Classes

### `Company`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `check_if_transactions_exist` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_abbr` | `self` | `` |  |
| `create_default_tax_template` | `self` | `` |  |
| `validate_default_accounts` | `self` | `` |  |
| `validate_advance_account_currency` | `self` | `` |  |
| `validate_currency` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `create_default_warehouses` | `self` | `` |  |
| `create_default_accounts` | `self` | `` |  |
| `create_default_departments` | `self` | `` |  |
| `validate_coa_input` | `self` | `` |  |
| `validate_perpetual_inventory` | `self` | `` |  |
| `validate_provisional_account_for_non_stock_items` | `self` | `` |  |
| `check_country_change` | `self` | `` |  |
| `set_chart_of_accounts` | `self` | `` | If parent company is set, chart of accounts will be based on that company |
| `validate_parent_company` | `self` | `` |  |
| `set_default_accounts` | `self` | `` |  |
| `_set_default_account` | `self, fieldname, account_type` | `` |  |
| `set_mode_of_payment_account` | `self` | `` |  |
| `create_default_cost_center` | `self` | `` |  |
| `after_rename` | `self, olddn, newdn, merge` | `` |  |
| `abbreviate` | `self` | `` |  |
| `on_trash` | `self` | `` | Trash accounts and cost centers for this company if no gl entry exists |
| `check_parent_changed` | `self` | `` |  |





## Functions

### `get_name_with_abbr`
**Arguments:** `name, company`
**Decorators:** ``

**Docstring:**
```

```
### `install_country_fixtures`
**Arguments:** `company, country`
**Decorators:** ``

**Docstring:**
```

```
### `update_company_current_month_sales`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `update_company_monthly_sales`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Cache past year monthly sales of every company based on sales invoices
```
### `update_transactions_annual_history`
**Arguments:** `company, commit`
**Decorators:** ``

**Docstring:**
```

```
### `cache_companies_monthly_sales_history`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_children`
**Arguments:** `doctype, parent, company, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `add_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_all_transactions_annual_history`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_timeline_data`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
returns timeline data based on linked records in dashboard
```
### `get_default_company_address`
**Arguments:** `name, sort_key, existing_address`
**Decorators:** ``

**Docstring:**
```

```
### `get_billing_shipping_address`
**Arguments:** `name, billing_address, shipping_address`
**Decorators:** ``

**Docstring:**
```

```
### `create_transaction_deletion_request`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```

