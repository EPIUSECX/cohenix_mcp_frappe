# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/dunning/dunning.py`

## Classes

### `Dunning`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_same_currency` | `self` | `` | Throw an error if invoice currency differs from dunning currency. |
| `validate_overdue_payments` | `self` | `` |  |
| `validate_totals` | `self` | `` |  |
| `set_party_details` | `self` | `` |  |
| `set_dunning_level` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `resolve_dunning`
**Arguments:** `doc, state`
**Decorators:** ``

**Docstring:**
```
Check if all payments have been made and resolve dunning, if yes. Called
when a Payment Entry is submitted.
```
### `get_linked_dunnings_as_per_state`
**Arguments:** `sales_invoice, state`
**Decorators:** ``

**Docstring:**
```

```
### `get_dunning_letter_text`
**Arguments:** `dunning_type, doc, language`
**Decorators:** ``

**Docstring:**
```

```

