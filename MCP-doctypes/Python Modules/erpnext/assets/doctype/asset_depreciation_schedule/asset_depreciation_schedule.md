# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_depreciation_schedule/asset_depreciation_schedule.py`

## Classes

### `AssetDepreciationSchedule`
**Inherits:** `DepreciationScheduleController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_another_asset_depr_schedule_does_not_exist` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `cancel_depreciation_entries` | `self` | `` |  |
| `update_shift_depr_schedule` | `self` | `` |  |
| `get_finance_book_row` | `self, fb_row` | `` |  |
| `fetch_asset_details` | `self` | `` |  |





## Functions

### `make_draft_asset_depr_schedule`
**Arguments:** `asset_doc, row`
**Decorators:** ``

**Docstring:**
```

```
### `convert_draft_asset_depr_schedules_into_active`
**Arguments:** `asset_doc`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_asset_depr_schedules`
**Arguments:** `asset_doc`
**Decorators:** ``

**Docstring:**
```

```
### `reschedule_depreciation`
**Arguments:** `asset_doc, notes, disposal_date`
**Decorators:** ``

**Docstring:**
```

```
### `set_modified_depreciation_rate`
**Arguments:** `asset_doc, row, new_schedule`
**Decorators:** ``

**Docstring:**
```

```
### `get_temp_depr_schedule_doc`
**Arguments:** `asset_doc, fb_row, disposal_date, updated_depr_schedule`
**Decorators:** ``

**Docstring:**
```

```
### `get_current_asset_depr`
**Arguments:** `asset_doc, row`
**Decorators:** ``

**Docstring:**
```

```
### `modify_depreciation_dchedule`
**Arguments:** `temp_schedule_doc, updated_depr_schedule`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_shift_factors_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_depr_schedule`
**Arguments:** `asset_name, status, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_depr_schedule_doc`
**Arguments:** `asset_name, status, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_depr_schedule_name`
**Arguments:** `asset_name, status, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `is_first_day_of_the_month`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```

