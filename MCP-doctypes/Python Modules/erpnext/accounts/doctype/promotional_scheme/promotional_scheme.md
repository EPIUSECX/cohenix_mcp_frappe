# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/promotional_scheme/promotional_scheme.py`

## Classes

### `TransactionExists`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PromotionalScheme`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_applicable_for` | `self` | `` |  |
| `validate_pricing_rules` | `self` | `` |  |
| `get_invalid_pricing_rules` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_mixed_with_recursion` | `self` | `` |  |
| `update_pricing_rules` | `self, pricing_rules` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

### `raise_for_transaction_exists`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_pricing_rules`
**Arguments:** `doc, rules`
**Decorators:** ``

**Docstring:**
```

```
### `_get_pricing_rules`
**Arguments:** `doc, child_doc, discount_fields, rules`
**Decorators:** ``

**Docstring:**
```

```
### `get_pricing_rule_docname`
**Arguments:** `row, applicable_for, applicable_for_value`
**Decorators:** ``

**Docstring:**
```

```
### `prepare_pricing_rule`
**Arguments:** `args, doc, child_doc, discount_fields, d, docname, applicable_for, value`
**Decorators:** ``

**Docstring:**
```

```
### `set_args`
**Arguments:** `args, pr, doc, child_doc, discount_fields, child_doc_fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_args_for_pricing_rule`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

