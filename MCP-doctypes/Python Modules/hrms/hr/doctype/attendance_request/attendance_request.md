# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/attendance_request/attendance_request.py`

## Classes

### `OverlappingAttendanceRequestError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AttendanceRequest`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_half_day` | `self` | `` |  |
| `validate_no_attendance_to_create` | `self` | `` |  |
| `validate_request_overlap` | `self` | `` |  |
| `throw_overlap_error` | `self, overlapping_request` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `create_attendance_records` | `self` | `` |  |
| `create_or_update_attendance` | `self, date` | `` |  |
| `should_mark_attendance` | `self, attendance_date` | `` |  |
| `has_leave_record` | `self, attendance_date` | `` |  |
| `get_attendance_doc` | `self, attendance_date` | `` |  |
| `get_attendance_status` | `self, attendance_date` | `` |  |
| `status_unchanged` | `self, attendance_date` | `` |  |
| `on_update` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `publish_update` | `self` | `` |  |
| `get_attendance_warnings` | `self` | `` |  |





## Functions

No top-level functions found in this file.
