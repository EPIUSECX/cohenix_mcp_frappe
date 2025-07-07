# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/taxes_and_totals.py`

## Classes

### `calculate_taxes_and_totals`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc` | `` |  |
| `filter_rows` | `self` | `` | Exclude rows, that do not fulfill the filter criteria, from totals computation. |
| `calculate` | `self` | `` |  |
| `_calculate` | `self` | `` |  |
| `calculate_tax_withholding_net_total` | `self` | `` |  |
| `validate_item_tax_template` | `self` | `` |  |
| `update_item_tax_map` | `self` | `` |  |
| `validate_conversion_rate` | `self` | `` |  |
| `calculate_item_values` | `self` | `` |  |
| `_set_in_company_currency` | `self, doc, fields` | `` | set values in base currency |
| `initialize_taxes` | `self` | `` |  |
| `determine_exclusive_rate` | `self` | `` |  |
| `_load_item_tax_rate` | `self, item_tax_rate` | `` |  |
| `get_current_tax_fraction` | `self, tax, item_tax_map` | `` | Get tax fraction for calculating tax exclusive amount
from tax inclusive amount |
| `_get_tax_rate` | `self, tax, item_tax_map` | `` |  |
| `calculate_net_total` | `self` | `` |  |
| `calculate_shipping_charges` | `self` | `` |  |
| `calculate_taxes` | `self` | `` |  |
| `get_tax_amount_if_for_valuation_or_deduction` | `self, tax_amount, tax` | `` |  |
| `set_cumulative_total` | `self, row_idx, tax` | `` |  |
| `get_current_tax_and_net_amount` | `self, item, tax, item_tax_map` | `` |  |
| `set_item_wise_tax` | `self, item, tax, tax_rate, current_tax_amount, current_net_amount` | `` |  |
| `round_off_totals` | `self, tax` | `` |  |
| `round_off_base_values` | `self, tax` | `` |  |
| `manipulate_grand_total_for_inclusive_tax` | `self` | `` |  |
| `adjust_grand_total_for_inclusive_tax` | `self` | `` |  |
| `calculate_totals` | `self` | `` |  |
| `calculate_total_net_weight` | `self` | `` |  |
| `set_rounded_total` | `self` | `` |  |
| `_cleanup` | `self` | `` |  |
| `set_discount_amount` | `self` | `` |  |
| `apply_discount_amount` | `self` | `` |  |
| `get_total_for_discount_amount` | `self` | `` |  |
| `calculate_total_advance` | `self` | `` |  |
| `is_internal_invoice` | `self` | `` | Checks if its an internal transfer invoice
and decides if to calculate any out standing amount or not |
| `calculate_outstanding_amount` | `self` | `` |  |
| `calculate_paid_amount` | `self` | `` |  |
| `calculate_change_amount` | `self` | `` |  |
| `calculate_write_off_amount` | `self` | `` |  |
| `calculate_margin` | `self, item` | `` |  |
| `set_item_wise_tax_breakup` | `self` | `` |  |
| `set_total_amount_to_default_mop` | `self, total_amount_to_pay` | `` |  |


### `init_landed_taxes_and_totals`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doc` | `` |  |
| `set_account_currency` | `self` | `` |  |
| `set_exchange_rate` | `self` | `` |  |
| `set_amounts_in_company_currency` | `self` | `` |  |





## Functions

### `get_itemised_tax_breakup_html`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_round_off_applicable_accounts`
**Arguments:** `company, account_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_regional_round_off_accounts`
**Arguments:** `company, account_list`
**Decorators:** ``

**Docstring:**
```

```
### `update_itemised_tax_data`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_itemised_tax_breakup_header`
**Arguments:** `item_doctype, tax_accounts`
**Decorators:** ``

**Docstring:**
```

```
### `get_itemised_tax_breakup_data`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_itemised_tax`
**Arguments:** `taxes, with_tax_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_rounded_tax_amount`
**Arguments:** `itemised_tax, precision`
**Decorators:** ``

**Docstring:**
```

```
### `get_rounding_tax_settings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

