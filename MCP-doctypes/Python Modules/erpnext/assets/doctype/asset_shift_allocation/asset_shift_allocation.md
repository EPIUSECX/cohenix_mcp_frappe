# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_shift_allocation/asset_shift_allocation.py`

## Classes

### `AssetShiftAllocation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_invalid_shift_change` | `self` | `` |  |
| `update_depr_schedule` | `self` | `` |  |
| `adjust_depr_shifts` | `self` | `` | Adjust the shifts in the depreciation schedule based on the new shifts |
| `calculate_shift_factor_diff` | `self, shift_factors_map` | `` |  |
| `reduce_depr_shifts` | `self, factor_diff, shift_factors_map, reverse_shift_factors_map` | `` |  |
| `add_depr_shifts` | `self, factor_diff, shift_factors_map, reverse_shift_factors_map` | `` |  |
| `add_schedule_row` | `self, factor, reverse_shift_factors_map` | `` |  |
| `get_finance_book_row` | `self, asset_doc` | `` |  |
| `modify_depr_schedule` | `self, temp_depr_schedule` | `` |  |
| `fetch_and_set_depr_schedule` | `self` | `` |  |
| `create_new_asset_depr_schedule` | `self` | `` |  |





## Functions

No top-level functions found in this file.
