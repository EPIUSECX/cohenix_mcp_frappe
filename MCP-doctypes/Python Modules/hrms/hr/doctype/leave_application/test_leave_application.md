# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_application/test_leave_application.py`

## Classes

### `TestLeaveApplication`
**Inherits:** `HRMSTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `make_leave_applications` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `_clear_roles` | `self` | `` |  |
| `_clear_applications` | `self` | `` |  |
| `get_application` | `self, doc` | `` |  |
| `test_validate_application_across_allocations` | `self` | `` |  |
| `test_insufficient_leave_balance_validation` | `self` | `` |  |
| `test_separate_leave_ledger_entry_for_boundary_applications` | `self` | `` |  |
| `test_overwrite_attendance` | `self` | `` | check attendance is automatically created on leave approval |
| `test_overwrite_half_day_attendance` | `self` | `` |  |
| `test_attendance_for_include_holidays` | `self` | `` |  |
| `test_attendance_update_for_exclude_holidays` | `self` | `` |  |
| `test_block_list` | `self` | `` |  |
| `test_overlap` | `self` | `` |  |
| `test_overlap_with_half_day_1` | `self` | `` |  |
| `test_overlap_with_half_day_2` | `self` | `` |  |
| `test_overlap_with_half_day_3` | `self` | `` |  |
| `test_optional_leave` | `self` | `` |  |
| `test_leaves_allowed` | `self` | `` |  |
| `test_applicable_after` | `self` | `` |  |
| `test_max_continuous_leaves` | `self` | `` |  |
| `test_max_consecutive_leaves_across_leave_applications` | `self` | `` |  |
| `test_leave_balance_near_allocaton_expiry` | `self` | `` |  |
| `test_current_leave_on_submit` | `self` | `` |  |
| `test_creation_of_leave_ledger_entry_on_submit` | `self` | `` |  |
| `test_ledger_entry_creation_on_intermediate_allocation_expiry` | `self` | `` |  |
| `test_leave_application_creation_after_expiry` | `self` | `` |  |
| `test_leave_approver_perms` | `self` | `` |  |
| `test_self_leave_approval_allowed` | `self` | `` |  |
| `test_self_leave_approval_not_allowed` | `self` | `` |  |
| `test_get_leave_details_for_dashboard` | `self` | `` |  |
| `test_leave_details_with_expired_cf_leaves` | `self` | `` | Tests leave details:
Case 1: All leaves available before cf leave expiry
Case 2: Remaining Leaves after cf leave expiry |
| `test_leave_details_with_application_across_cf_expiry` | `self` | `` | Tests leave details with leave application across cf expiry, such that:
cf leaves are partially expired and partially consumed |
| `test_leave_details_with_application_across_cf_expiry_2` | `self` | `` | Tests the same case as above but with leave days greater than cf leaves allocated |
| `test_leave_details_with_application_after_cf_expiry` | `self` | `` | Tests leave details with leave application after cf expiry, such that:
cf leaves are completely expired and only newly allocated leaves are consumed |
| `test_get_leave_allocation_records` | `self` | `` | Tests if total leaves allocated before and after carry forwarded leave expiry is same |
| `test_filtered_old_cf_entries_in_get_leave_allocation_records` | `self` | `` | Tests whether old cf entries are ignored while fetching current allocation records |
| `test_modifying_attendance_when_half_day_exists_from_checkins` | `self` | `` |  |
| `test_modifying_attendance_from_absent_to_half_day` | `self` | `` |  |
| `test_half_day_status_for_two_half_leaves` | `self` | `` |  |





## Functions

### `create_carry_forwarded_allocation`
**Arguments:** `employee, leave_type, date`
**Decorators:** ``

**Docstring:**
```

```
### `make_allocation_record`
**Arguments:** `employee, leave_type, from_date, to_date, carry_forward, leaves`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_period`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `allocate_leaves`
**Arguments:** `employee, leave_period, leave_type, new_leaves_allocated, eligible_leaves`
**Decorators:** ``

**Docstring:**
```

```

