# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/warehouse/warehouse.py`

## Classes

### `Warehouse`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `onload` | `self` | `` | load account name for General Ledger Report |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `update_nsm_model` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `warn_about_multiple_warehouse_account` | `self` | `` | If Warehouse value is split across multiple accounts, warn. |
| `check_if_sle_exists` | `self` | `` |  |
| `check_if_child_exists` | `self` | `` |  |
| `convert_to_group_or_ledger` | `self` | `` |  |
| `convert_to_ledger` | `self` | `` |  |
| `convert_to_group` | `self` | `` |  |
| `unlink_from_items` | `self` | `` |  |





## Functions

### `get_children`
**Arguments:** `doctype, parent, company, is_root, include_disabled`
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
### `convert_to_group_or_ledger`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_child_warehouses`
**Arguments:** `warehouse`
**Decorators:** `request_cache`

**Docstring:**
```

```
### `get_warehouses_based_on_account`
**Arguments:** `account, company`
**Decorators:** ``

**Docstring:**
```

```
### `apply_warehouse_filter`
**Arguments:** `query, sle, filters`
**Decorators:** ``

**Docstring:**
```

```

