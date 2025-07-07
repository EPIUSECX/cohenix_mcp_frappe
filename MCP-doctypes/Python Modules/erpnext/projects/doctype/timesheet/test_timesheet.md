# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/timesheet/test_timesheet.py`

## Classes

### `TestTimesheet`
**Inherits:** `ERPNextTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `test_timesheet_billing_amount` | `self` | `` |  |
| `test_timesheet_billing_amount_not_billable` | `self` | `` |  |
| `test_sales_invoice_from_timesheet` | `self` | `` |  |
| `test_timesheet_billing_based_on_project` | `self` | `` |  |
| `test_timesheet_time_overlap` | `self` | `` |  |
| `test_timesheet_not_overlapping_with_continuous_timelogs` | `self` | `` |  |
| `test_to_time` | `self` | `` |  |
| `test_per_billed_hours` | `self` | `` | If amounts are 0, per_billed should be calculated based on hours. |
| `test_per_billed_amount` | `self` | `` | If amounts are > 0, per_billed should be calculated based on amounts, regardless of hours. |





## Functions

### `make_timesheet`
**Arguments:** `employee, simulate, is_billable, activity_type, project, task, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_activity_type`
**Arguments:** `activity_type`
**Decorators:** ``

**Docstring:**
```

```

