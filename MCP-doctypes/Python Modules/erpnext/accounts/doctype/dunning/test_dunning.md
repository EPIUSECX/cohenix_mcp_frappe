# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/dunning/test_dunning.py`

## Classes

### `TestDunning`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_dunning_without_fees` | `self` | `` |  |
| `test_dunning_with_fees_and_interest` | `self` | `` |  |
| `test_dunning_with_payment_entry` | `self` | `` |  |
| `test_fetch_overdue_payments` | `self` | `` | Create SI with overdue payment. Check if overdue payment is fetched in Dunning. |
| `test_dunning_and_payment_against_partially_due_invoice` | `self` | `` | Create SI with first installment overdue. Check impact of Dunning and Payment Entry. |





## Functions

### `create_dunning`
**Arguments:** `overdue_days, dunning_type_name`
**Decorators:** ``

**Docstring:**
```

```
### `create_dunning_type`
**Arguments:** `title, fee, interest, is_default`
**Decorators:** ``

**Docstring:**
```

```
### `get_income_account`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_terms_template_for_dunning`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

