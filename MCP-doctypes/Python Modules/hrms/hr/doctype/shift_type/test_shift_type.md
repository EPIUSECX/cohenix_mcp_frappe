# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/shift_type/test_shift_type.py`

## Classes

### `TestShiftType`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_auto_update_last_sync_of_checkin_for_single_day_shift` | `self` | `` |  |
| `test_auto_update_last_sync_of_checkin_for_shifts_spanning_two_days_due_to_buffer` | `self` | `` |  |
| `test_auto_update_last_sync_of_checkin_for_two_day_shift` | `self` | `` |  |
| `test_auto_update_last_sync_of_checkin_when_when_job_runs_on_the_next_day` | `self` | `` |  |
| `test_mark_attendance` | `self` | `` |  |
| `test_mark_attendance_with_different_shift_start_time` | `self` | `` | Tests whether attendance is marked correctly if shift configuration is changed midway |
| `test_attendance_date_for_different_start_and_actual_start_date` | `self` | `` |  |
| `test_entry_and_exit_grace` | `self` | `` |  |
| `test_working_hours_threshold_for_half_day` | `self` | `` |  |
| `test_working_hours_threshold_for_absent` | `self` | `` |  |
| `test_working_hours_threshold_for_absent_and_half_day_1` | `self` | `` |  |
| `test_working_hours_threshold_for_absent_and_half_day_2` | `self` | `` |  |
| `test_mark_auto_attendance_on_holiday_enabled` | `self` | `` |  |
| `test_mark_auto_attendance_on_holiday_disabled` | `self` | `` |  |
| `test_mark_absent_for_dates_with_no_attendance` | `self` | `` |  |
| `test_mark_absent_for_dates_with_no_attendance_for_midnight_shift` | `self` | `` |  |
| `test_do_not_mark_absent_before_shift_actual_end_time` | `self` | `` |  |
| `test_do_not_mark_absent_before_shift_actual_end_time_for_midnight_shift` | `self` | `` | Tests employee is not marked absent for a shift spanning 2 days
before its actual end time |
| `test_skip_marking_absent_on_a_holiday` | `self` | `` |  |
| `test_skip_absent_marking_for_a_fallback_default_shift` | `self` | `` | Tests if an employee is not marked absent for default shift
when they have a valid shift assignment of another type.
Assigned shift takes precedence over default shift |
| `test_skip_absent_marking_for_inactive_employee` | `self` | `` |  |
| `test_get_start_and_end_dates` | `self` | `` |  |
| `test_skip_auto_attendance_for_duplicate_record` | `self` | `` |  |
| `test_skip_auto_attendance_for_overlapping_shift` | `self` | `` |  |
| `test_mark_attendance_for_default_shift_when_shift_assignment_is_not_overlapping` | `self` | `` |  |
| `test_validation_for_unlinked_logs_before_changing_important_shift_configuration` | `self` | `` |  |
| `test_circular_shift_times` | `self` | `` |  |





## Functions

### `setup_shift_type`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_shift_assignment`
**Arguments:** `shift_type, employee, start_date, end_date, do_not_submit, shift_location`
**Decorators:** ``

**Docstring:**
```

```

