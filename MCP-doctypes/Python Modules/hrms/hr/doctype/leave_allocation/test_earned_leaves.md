# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_allocation/test_earned_leaves.py`

## Classes

### `TestLeaveAllocation`
**Inherits:** `HRMSTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `test_earned_leave_allocation` | `self` | `` | Tests if Earned Leave allocation is 0 initially as it happens via scheduler |
| `test_earned_leave_update_after_submission` | `self` | `` | Tests if validation error is raised when updating Earned Leave allocation after submission |
| `test_alloc_based_on_leave_period` | `self` | `` | Case 1: Tests if assignment created one month after the leave period
allocates 1 leave for past month |
| `test_alloc_on_month_end_based_on_leave_period` | `self` | `` | Case 2: Tests if assignment created on the last day of the leave period's latter month
allocates 1 leave for the current month even though the month has not ended
since the daily job might have already executed (12:00:00 AM) |
| `test_alloc_based_on_leave_period_with_cf_leaves` | `self` | `` | Case 3: Tests assignment created on the leave period's latter month with carry forwarding |
| `test_alloc_based_on_joining_date` | `self` | `` | Tests if DOJ-based assignment created 2 months after the DOJ
allocates 3 leaves for the past 2 months |
| `test_alloc_on_doj_based_on_leave_period` | `self` | `` | Tests assignment with 'Allocate On=Date of Joining' based on Leave Period |
| `test_alloc_on_doj_based_on_joining_date` | `self` | `` | Tests assignment with 'Allocate On=Date of Joining' based on Joining Date |
| `test_earned_leaves_creation` | `self` | `` |  |
| `test_overallocation` | `self` | `` | Tests earned leave allocation does not exceed annual allocation |
| `test_over_allocation_during_assignment_creation` | `self` | `` | Tests backdated earned leave allocation does not exceed annual allocation |
| `test_overallocation_with_carry_forwarding` | `self` | `` | Tests earned leave allocation with cf leaves does not exceed annual allocation |
| `test_allocate_on_first_day` | `self` | `` | Tests assignment with 'Allocate On=First Day' |
| `test_allocate_on_last_day` | `self` | `` | Tests assignment with 'Allocate On=Last Day' |
| `test_allocate_on_date_of_joining` | `self` | `` | Tests assignment with 'Allocate On=Date of Joining' |
| `test_backdated_pro_rated_allocation` | `self` | `` |  |
| `test_no_pro_rated_leaves_allocated_before_effective_date` | `self` | `` |  |
| `test_pro_rated_allocation_via_scheduler` | `self` | `` |  |
| `test_get_earned_leave_details_for_dashboard` | `self` | `` |  |
| `test_allocate_leaves_manually` | `self` | `` |  |
| `tearDown` | `self` | `` |  |





## Functions

### `create_earned_leave_type`
**Arguments:** `leave_type, allocate_on_day, rounding`
**Decorators:** ``

**Docstring:**
```

```
### `create_leave_period`
**Arguments:** `name, start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `make_policy_assignment`
**Arguments:** `employee, allocate_on_day, rounding, earned_leave_frequency, start_date, end_date, annual_allocation, carry_forward, assignment_based_on`
**Decorators:** ``

**Docstring:**
```

```
### `get_allocated_leaves`
**Arguments:** `assignment`
**Decorators:** ``

**Docstring:**
```

```
### `allocate_earned_leaves_for_months`
**Arguments:** `months`
**Decorators:** ``

**Docstring:**
```

```

