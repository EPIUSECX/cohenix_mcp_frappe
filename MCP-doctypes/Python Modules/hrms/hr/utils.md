# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/utils.py`

## Classes

### `DuplicateDeclarationError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `set_employee_name`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_employee_work_history`
**Arguments:** `employee, details, date, cancel`
**Decorators:** ``

**Docstring:**
```

```
### `get_formatted_value`
**Arguments:** `value, fieldtype`
**Decorators:** ``

**Docstring:**
```
Since the fields in Internal Work History table are `Data` fields
format them as per relevant field types
```
### `delete_employee_work_history`
**Arguments:** `details, employee, date`
**Decorators:** ``

**Docstring:**
```

```
### `update_to_date_in_work_history`
**Arguments:** `employee, cancel`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_field_property`
**Arguments:** `employee, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `validate_dates`
**Arguments:** `doc, from_date, to_date, restrict_future_dates`
**Decorators:** ``

**Docstring:**
```

```
### `validate_overlap`
**Arguments:** `doc, from_date, to_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_condition`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `throw_overlap_error`
**Arguments:** `doc, exists_for, overlap_doc, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `validate_duplicate_exemption_for_payroll_period`
**Arguments:** `doctype, docname, payroll_period, employee`
**Decorators:** ``

**Docstring:**
```

```
### `validate_tax_declaration`
**Arguments:** `declarations`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_exemption_amount`
**Arguments:** `declarations`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_period`
**Arguments:** `from_date, to_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `generate_leave_encashment`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Generates a draft leave encashment on allocation expiry
```
### `allocate_earned_leaves`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Allocate earned leaves to Employees
```
### `update_previous_leave_allocation`
**Arguments:** `allocation, annual_allocation, e_leave_type, date_of_joining`
**Decorators:** ``

**Docstring:**
```

```
### `get_monthly_earned_leave`
**Arguments:** `date_of_joining, annual_leaves, frequency, rounding, period_start_date, period_end_date, pro_rated`
**Decorators:** ``

**Docstring:**
```

```
### `round_earned_leaves`
**Arguments:** `earned_leaves, rounding`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_allocations`
**Arguments:** `date, leave_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_earned_leaves`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_additional_leave_ledger_entry`
**Arguments:** `allocation, leaves, date`
**Decorators:** ``

**Docstring:**
```
Create leave ledger entry for leave types
```
### `check_effective_date`
**Arguments:** `from_date, today, frequency, allocate_on_day`
**Decorators:** ``

**Docstring:**
```

```
### `get_salary_assignments`
**Arguments:** `employee, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `get_sal_slip_total_benefit_given`
**Arguments:** `employee, payroll_period, component`
**Decorators:** ``

**Docstring:**
```

```
### `get_holiday_dates_for_employee`
**Arguments:** `employee, start_date, end_date`
**Decorators:** ``

**Docstring:**
```
return a list of holiday dates for the given employee between start_date and end_date
```
### `get_holidays_for_employee`
**Arguments:** `employee, start_date, end_date, raise_exception, only_non_weekly`
**Decorators:** ``

**Docstring:**
```
Get Holidays for a given employee

`employee` (str)
`start_date` (str or datetime)
`end_date` (str or datetime)
`raise_exception` (bool)
`only_non_weekly` (bool)

return: list of dicts with `holiday_date` and `description`
```
### `calculate_annual_eligible_hra_exemption`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_hra_exemption_for_period`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_tax_with_marginal_relief`
**Arguments:** `tax_slab, tax_amount, annual_taxable_earning`
**Decorators:** ``

**Docstring:**
```

```
### `get_previous_claimed_amount`
**Arguments:** `employee, payroll_period, non_pro_rata, component`
**Decorators:** ``

**Docstring:**
```

```
### `share_doc_with_approver`
**Arguments:** `doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `validate_active_employee`
**Arguments:** `employee, method`
**Decorators:** ``

**Docstring:**
```

```
### `validate_loan_repay_from_salary`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `get_matching_queries`
**Arguments:** `bank_account, company, transaction, document_types, exact_match, account_from_to, from_date, to_date, filter_by_reference_date, from_reference_date, to_reference_date, common_filters`
**Decorators:** ``

**Docstring:**
```
Returns matching queries for Bank Reconciliation
```
### `get_ec_matching_query`
**Arguments:** `bank_account, company, exact_match, from_date, to_date, common_filters`
**Decorators:** ``

**Docstring:**
```

```
### `validate_bulk_tool_fields`
**Arguments:** `self, fields, employees, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `notify_bulk_action_status`
**Arguments:** `doctype, failure, success`
**Decorators:** ``

**Docstring:**
```

```
### `set_geolocation_from_coordinates`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_distance_between_coordinates`
**Arguments:** `lat1, long1, lat2, long2`
**Decorators:** ``

**Docstring:**
```

```
### `check_app_permission`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Check if user has permission to access the app (for showing the app on app screen)
```
### `get_exact_month_diff`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in months.
```

