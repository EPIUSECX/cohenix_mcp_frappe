# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/employee_checkin/test_employee_checkin.py`

## Classes

### `TestEmployeeCheckin`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_geolocation_tracking` | `self` | `` |  |
| `test_add_log_based_on_employee_field` | `self` | `` |  |
| `test_mark_attendance_and_link_log` | `self` | `` |  |
| `test_unlink_attendance_on_cancellation` | `self` | `` |  |
| `test_calculate_working_hours` | `self` | `` |  |
| `test_fetch_shift` | `self` | `` |  |
| `test_fetch_shift_for_assignment_with_end_date` | `self` | `` |  |
| `test_shift_start_and_end_timings` | `self` | `` |  |
| `test_fetch_shift_based_on_default_shift` | `self` | `` |  |
| `test_fetch_night_shift_for_assignment_without_end_date` | `self` | `` | Tests if shift is correctly fetched in logs when assignment has no end date |
| `test_fetch_night_shift_on_assignment_boundary` | `self` | `` | Tests if shift is correctly fetched in logs when assignment starts and ends on the same day |
| `test_night_shift_not_fetched_outside_assignment_boundary_for_diff_start_date` | `self` | `` |  |
| `test_night_shift_not_fetched_outside_assignment_boundary_for_diff_end_date` | `self` | `` |  |
| `test_night_shift_not_fetched_outside_before_shift_margin` | `self` | `` |  |
| `test_night_shift_not_fetched_outside_after_shift_margin` | `self` | `` |  |
| `test_fetch_night_shift_in_margin_period_after_shift` | `self` | `` | Tests if shift is correctly fetched in logs if the actual end time exceeds a day
i.e: shift is from 15:00 to 23:00 (starts & ends on the same day)
but shift margin = 2 hours, so the actual shift goes to 1:00 of the next day |
| `test_fetch_night_shift_in_margin_period_before_shift` | `self` | `` | Tests if shift is correctly fetched in logs if the actual end time exceeds a day
i.e: shift is from 00:30 to 10:00 (starts & ends on the same day)
but shift margin = 1 hour, so the actual shift start goes to 23:30:00 of the prev day |
| `test_consecutive_shift_assignments_overlapping_within_grace_period` | `self` | `` |  |
| `test_geofencing` | `self` | `` |  |
| `test_bulk_fetch_shift` | `self` | `` |  |
| `test_bulk_fetch_shift_if_shift_settings_change_for_the_same_shift` | `self` | `` |  |
| `test_if_logs_are_marked_invalid` | `self` | `` |  |
| `test_if_logs_are_marked_valid_again` | `self` | `` |  |
| `test_validate_time_change` | `self` | `` |  |
| `test_modifying_half_attendance_created_from_leave` | `self` | `` |  |
| `test_modifying_half_day_attendance_when_checkins_are_absent` | `self` | `` |  |
| `test_half_day_attendance_when_checkins_exists_but_threshold_is_unmet` | `self` | `` |  |
| `test_half_day_attendance_when_employee_checkins_exists_and_attendance_is_full_day` | `self` | `` |  |





## Functions

### `make_n_checkins`
**Arguments:** `employee, n, hours_to_reverse`
**Decorators:** ``

**Docstring:**
```

```
### `make_checkin`
**Arguments:** `employee, time, latitude, longitude`
**Decorators:** ``

**Docstring:**
```

```
### `make_shift_location`
**Arguments:** `location_name, latitude, longitude, checkin_radius`
**Decorators:** ``

**Docstring:**
```

```
### `create_leave_allocation`
**Arguments:** `employee, leave_type, from_date, to_date, new_leaves_allocated`
**Decorators:** ``

**Docstring:**
```

```

