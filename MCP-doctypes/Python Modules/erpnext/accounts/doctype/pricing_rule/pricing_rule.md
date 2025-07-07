# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pricing_rule/pricing_rule.py`

## Classes

### `PricingRule`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_duplicate_apply_on` | `self` | `` |  |
| `validate_mandatory` | `self` | `` |  |
| `validate_applicable_for_selling_or_buying` | `self` | `` |  |
| `validate_min_max_qty` | `self` | `` |  |
| `validate_min_max_amt` | `self` | `` |  |
| `validate_recursion` | `self` | `` |  |
| `cleanup_fields_value` | `self` | `` |  |
| `validate_rate_or_discount` | `self` | `` |  |
| `validate_max_discount` | `self` | `` |  |
| `validate_price_list_with_currency` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `validate_condition` | `self` | `` |  |
| `validate_mixed_with_recursion` | `self` | `` |  |





## Functions

### `apply_pricing_rule`
**Arguments:** `args, doc`
**Decorators:** ``

**Docstring:**
```
args = {
        "items": [{"doctype": "", "name": "", "item_code": "", "brand": "", "item_group": ""}, ...],
        "customer": "something",
        "customer_group": "something",
        "territory": "something",
        "supplier": "something",
        "supplier_group": "something",
        "currency": "something",
        "conversion_rate": "something",
        "price_list": "something",
        "plc_conversion_rate": "something",
        "company": "something",
        "transaction_date": "something",
        "campaign": "something",
        "sales_partner": "something",
        "ignore_pricing_rule": "something"
}
```
### `update_pricing_rule_uom`
**Arguments:** `pricing_rule, args`
**Decorators:** ``

**Docstring:**
```

```
### `get_pricing_rule_for_item`
**Arguments:** `args, doc, for_validate`
**Decorators:** ``

**Docstring:**
```

```
### `update_args_for_pricing_rule`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_pricing_rule_details`
**Arguments:** `args, pricing_rule`
**Decorators:** ``

**Docstring:**
```

```
### `apply_price_discount_rule`
**Arguments:** `pricing_rule, item_details, args`
**Decorators:** ``

**Docstring:**
```

```
### `remove_pricing_rule_for_item`
**Arguments:** `pricing_rules, item_details, item_code, rate`
**Decorators:** ``

**Docstring:**
```

```
### `remove_pricing_rules`
**Arguments:** `item_list`
**Decorators:** ``

**Docstring:**
```

```
### `set_transaction_type`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `make_pricing_rule`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_uoms`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

