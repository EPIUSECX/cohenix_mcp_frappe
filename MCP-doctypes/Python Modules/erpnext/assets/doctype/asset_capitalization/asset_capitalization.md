# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_capitalization/asset_capitalization.py`

## Classes

### `AssetCapitalization`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `set_title` | `self` | `` |  |
| `set_missing_values` | `self, for_validate` | `` |  |
| `validate_target_item` | `self` | `` |  |
| `validate_target_asset` | `self` | `` |  |
| `validate_consumed_stock_item` | `self` | `` |  |
| `validate_consumed_asset_item` | `self` | `` |  |
| `validate_service_item` | `self` | `` |  |
| `validate_source_mandatory` | `self` | `` |  |
| `validate_item` | `self, item` | `` |  |
| `get_asset_for_validation` | `self, asset` | `` |  |
| `set_warehouse_details` | `self` | `` |  |
| `set_asset_values` | `self` | `` |  |
| `get_args_for_incoming_rate` | `self, item` | `` |  |
| `calculate_totals` | `self` | `` |  |
| `update_stock_ledger` | `self` | `` |  |
| `make_gl_entries` | `self, gl_entries, from_repost` | `` |  |
| `get_gl_entries` | `self, warehouse_account, default_expense_account, default_cost_center` | `` |  |
| `get_target_account` | `self` | `` |  |
| `get_gl_entries_for_consumed_stock_items` | `self, gl_entries, target_account, target_against, precision` | `` |  |
| `get_gl_entries_for_consumed_asset_items` | `self, gl_entries, target_account, target_against, precision` | `` |  |
| `get_gl_entries_for_consumed_service_items` | `self, gl_entries, target_account, target_against, precision` | `` |  |
| `get_composite_component_value` | `self` | `` |  |
| `get_gl_entries_for_target_item` | `self, gl_entries, target_account, target_against, precision, composite_component_value` | `` |  |
| `update_target_asset` | `self` | `` |  |
| `restore_consumed_asset_items` | `self` | `` |  |
| `set_consumed_asset_status` | `self, asset` | `` |  |





## Functions

### `get_target_item_details`
**Arguments:** `item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_target_asset_details`
**Arguments:** `asset, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_consumed_stock_item_details`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_warehouse_details`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_consumed_asset_details`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_service_item_details`
**Arguments:** `ctx`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_tagged_to_wip_composite_asset`
**Arguments:** `params`
**Decorators:** ``

**Docstring:**
```

```
### `process_stock_item`
**Arguments:** `d`
**Decorators:** ``

**Docstring:**
```

```
### `process_fixed_asset`
**Arguments:** `d`
**Decorators:** ``

**Docstring:**
```

```

