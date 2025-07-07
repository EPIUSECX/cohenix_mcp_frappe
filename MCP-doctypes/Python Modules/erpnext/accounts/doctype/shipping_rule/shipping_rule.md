# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/shipping_rule/shipping_rule.py`

## Classes

### `OverlappingConditionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FromGreaterThanToError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ManyBlankToValuesError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ShippingRule`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_from_to_values` | `self` | `` |  |
| `apply` | `self, doc` | `` | Apply shipping rule on given doc. Called from accounts controller |
| `get_shipping_amount_from_rules` | `self, value` | `` |  |
| `validate_countries` | `self, doc` | `` |  |
| `add_shipping_rule_to_tax_table` | `self, doc, shipping_amount` | `` |  |
| `sort_shipping_rule_conditions` | `self` | `` | Sort Shipping Rule Conditions based on increasing From Value |
| `validate_overlapping_shipping_rule_conditions` | `self` | `` |  |





## Functions

No top-level functions found in this file.
