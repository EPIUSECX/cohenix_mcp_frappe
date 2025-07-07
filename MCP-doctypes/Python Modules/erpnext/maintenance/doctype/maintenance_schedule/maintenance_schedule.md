# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/maintenance/doctype/maintenance_schedule/maintenance_schedule.py`

## Classes

### `MaintenanceSchedule`
**Inherits:** `TransactionBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `generate_schedule` | `self` | `` |  |
| `validate_end_date_visits` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `create_schedule_list` | `self, start_date, end_date, no_of_visit, sales_person` | `` |  |
| `validate_schedule_date_for_holiday_list` | `self, schedule_date, sales_person` | `` |  |
| `validate_dates_with_periodicity` | `self` | `` |  |
| `validate_maintenance_detail` | `self` | `` |  |
| `validate_sales_order` | `self` | `` |  |
| `validate_items_table_change` | `self` | `` |  |
| `validate_no_of_visits` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_serial_no_bundle` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `update_amc_date` | `self, serial_nos, amc_expiry_date` | `` |  |
| `validate_serial_no` | `self, item_code, serial_nos, amc_start_date` | `` |  |
| `validate_schedule` | `self` | `` |  |
| `check_serial_no_added` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `get_pending_data` | `self, data_type, s_date, item_name` | `` |  |





## Functions

### `get_serial_nos_from_schedule`
**Arguments:** `item_code, schedule`
**Decorators:** ``

**Docstring:**
```

```
### `make_maintenance_visit`
**Arguments:** `source_name, target_doc, item_name, s_id`
**Decorators:** ``

**Docstring:**
```

```

