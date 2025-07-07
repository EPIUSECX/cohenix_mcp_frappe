# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/manufacturing/doctype/workstation/workstation.py`

## Classes

### `WorkstationHolidayError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NotInWorkingHoursError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `OverlapError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Workstation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_save` | `self` | `` |  |
| `disabled_workstation` | `self` | `` |  |
| `set_total_working_hours` | `self` | `` |  |
| `validate_working_hours` | `self, row` | `` |  |
| `set_hour_rate` | `self` | `` |  |
| `set_data_based_on_workstation_type` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `publish_workstation_status` | `self` | `` |  |
| `validate_overlap_for_operation_timings` | `self` | `` | Check if there is no overlap in setting Workstation Operating Hours |
| `update_bom_operation` | `self` | `` |  |
| `validate_workstation_holiday` | `self, schedule_date, skip_holiday_list_check` | `` |  |
| `start_job` | `self, job_card, from_time, employee` | `` |  |
| `complete_job` | `self, job_card, qty, to_time` | `` |  |





## Functions

### `get_job_cards`
**Arguments:** `workstation, job_card`
**Decorators:** ``

**Docstring:**
```

```
### `get_status_color`
**Arguments:** `status`
**Decorators:** ``

**Docstring:**
```

```
### `get_raw_materials`
**Arguments:** `job_card`
**Decorators:** ``

**Docstring:**
```

```
### `get_time_logs`
**Arguments:** `job_cards`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_holiday_list`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_if_within_operating_hours`
**Arguments:** `workstation, operation, from_datetime, to_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `is_within_operating_hours`
**Arguments:** `workstation, operation, from_datetime, to_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `check_workstation_for_holiday`
**Arguments:** `workstation, from_datetime, to_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `get_workstations`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_color_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_job_card`
**Arguments:** `job_card, method`
**Decorators:** ``

**Docstring:**
```

```
### `validate_job_card`
**Arguments:** `job_card, status`
**Decorators:** ``

**Docstring:**
```

```

