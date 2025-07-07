# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_depreciation_schedule/depreciation_methods.py`

## Classes

### `StraightLineMethod`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_straight_line_depr_amount` | `self, row_idx` | `` |  |
| `get_fixed_depr_amount` | `self` | `` |  |
| `get_daily_prorata_based_depr_amount` | `self, row_idx` | `` |  |
| `get_daily_depr_amount` | `self` | `` |  |
| `get_shift_depr_amount` | `self, row_idx` | `` |  |
| `get_asset_shift_factors_map` | `self` | `` |  |


### `WDVMethod`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_wdv_or_dd_depr_amount` | `self, row_idx` | `` |  |
| `calculate_wdv_or_dd_based_depreciation_amount` | `self, row_idx` | `staticmethod` |  |
| `get_wdv_depr_amount` | `self` | `` |  |
| `is_fiscal_year_changed` | `self` | `` |  |
| `get_daily_prorata_based_wdv_depr_amount` | `self, row_idx` | `` |  |
| `get_daily_wdv_depr_amount` | `self` | `` |  |





## Functions

No top-level functions found in this file.
