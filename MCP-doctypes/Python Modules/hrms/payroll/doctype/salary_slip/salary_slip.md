# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_slip/salary_slip.py`

## Classes

### `SalarySlip`
**Inherits:** `TransactionBase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `joining_date` | `self` | `property` |  |
| `relieving_date` | `self` | `property` |  |
| `payroll_period` | `self` | `property` |  |
| `actual_start_date` | `self` | `property` |  |
| `actual_end_date` | `self` | `property` |  |
| `validate` | `self` | `` |  |
| `check_salary_withholding` | `self` | `` |  |
| `set_net_total_in_words` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `update_payment_status_for_gratuity_and_leave_encashment` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `publish_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `get_status` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `is_rounding_total_disabled` | `self` | `` |  |
| `check_existing` | `self` | `` |  |
| `get_date_details` | `self` | `` |  |
| `get_emp_and_working_day_details` | `self` | `` | First time, load all the components from salary structure |
| `set_time_sheet` | `self` | `` |  |
| `check_sal_struct` | `self` | `` |  |
| `pull_sal_struct` | `self` | `` |  |
| `get_working_days_details` | `self, lwp, for_preview` | `` |  |
| `get_unmarked_days` | `self, include_holidays_in_total_working_days, holidays` | `` | Calculates the number of unmarked days for an employee within a date range |
| `get_half_absent_days` | `self, include_holidays_in_total_working_days, consider_marked_attendance_on_holidays, holidays` | `` | Calculates the number of half absent days for an employee within a date range |
| `_get_days_outside_period` | `self, include_holidays_in_total_working_days, holidays` | `` | Returns days before DOJ or after relieving date |
| `_get_number_of_holidays` | `self, holidays` | `` |  |
| `_get_marked_attendance_days` | `self, holidays` | `` |  |
| `get_payment_days` | `self, include_holidays_in_total_working_days` | `` |  |
| `get_holidays_for_employee` | `self, start_date, end_date` | `` |  |
| `calculate_lwp_or_ppl_based_on_leave_application` | `self, holidays, working_days_list, daily_wages_fraction_for_half_day` | `` |  |
| `get_leave_type_map` | `self` | `` | Returns (partially paid leaves/leave without pay) leave types by name |
| `get_employee_attendance` | `self, start_date, end_date` | `` |  |
| `calculate_lwp_ppl_and_absent_days_based_on_attendance` | `self, holidays, daily_wages_fraction_for_half_day, consider_marked_attendance_on_holidays` | `` |  |
| `add_earning_for_hourly_wages` | `self, doc, salary_component, amount` | `` |  |
| `set_salary_structure_assignment` | `self` | `` |  |
| `calculate_net_pay` | `self, skip_tax_breakup_computation` | `` |  |
| `set_net_pay` | `self` | `` |  |
| `compute_taxable_earnings_for_year` | `self` | `` |  |
| `compute_current_and_future_taxable_earnings` | `self` | `` |  |
| `compute_income_tax_breakup` | `self` | `` |  |
| `compute_ctc` | `self` | `` |  |
| `compute_non_taxable_earnings` | `self` | `` |  |
| `get_future_period_non_taxable_earnings` | `self` | `` |  |
| `get_non_taxable_earnings_for_current_period` | `self` | `` |  |
| `compute_annual_deductions_before_tax_calculation` | `self` | `` |  |
| `get_amount_from_formula` | `self, struct_row, sub_period` | `` |  |
| `get_income_tax_deducted_till_date` | `self` | `` |  |
| `calculate_component_amounts` | `self, component_type` | `` |  |
| `set_salary_structure_doc` | `self` | `` |  |
| `add_structure_components` | `self, component_type` | `` |  |
| `add_structure_component` | `self, struct_row, component_type` | `` |  |
| `get_data_for_eval` | `self` | `` | Returns data for evaluating formula |
| `get_component_abbr_map` | `self` | `` |  |
| `eval_condition_and_formula` | `self, struct_row, data` | `` |  |
| `add_employee_benefits` | `self` | `` |  |
| `adjust_benefits_in_last_payroll_period` | `self, payroll_period` | `` |  |
| `add_additional_salary_components` | `self, component_type` | `` |  |
| `add_tax_components` | `self` | `` |  |
| `get_tax_components` | `self` | `` | Returns:
        list: A list of tax components specific to the company.
        If no tax components are defined for the company,
        it returns the default tax components. |
| `_fetch_tax_components_by_company` | `self` | `` | Returns:
    dict: A dictionary containing tax components grouped by company.

Raises:
    None |
| `handle_additional_salary_tax_component` | `self` | `` |  |
| `update_component_row` | `self, component_data, amount, component_type, additional_salary, is_recurring, data, default_amount, remove_if_zero_valued` | `` |  |
| `update_component_amount_based_on_payment_days` | `self, component_row, remove_if_zero_valued` | `` |  |
| `set_precision_for_component_amounts` | `self` | `` |  |
| `calculate_variable_based_on_taxable_salary` | `self, tax_component` | `` |  |
| `calculate_variable_tax` | `self, tax_component` | `` |  |
| `get_income_tax_slabs` | `self` | `` |  |
| `get_taxable_earnings_for_prev_period` | `self, start_date, end_date, allow_tax_exemption` | `` |  |
| `get_opening_for` | `self, field_to_select, start_date, end_date` | `` |  |
| `get_salary_slip_details` | `self, start_date, end_date, parentfield, salary_component, is_tax_applicable, is_flexible_benefit, exempted_from_income_tax, variable_based_on_taxable_salary, field_to_select` | `` |  |
| `get_tax_paid_in_period` | `self, start_date, end_date, tax_component` | `` |  |
| `get_taxable_earnings` | `self, allow_tax_exemption, based_on_payment_days` | `` |  |
| `get_future_recurring_period` | `self, additional_salary` | `` |  |
| `get_future_recurring_additional_amount` | `self, additional_salary, monthly_additional_amount` | `` |  |
| `get_amount_based_on_payment_days` | `self, row` | `` |  |
| `calculate_unclaimed_taxable_benefits` | `self` | `` |  |
| `get_total_exemption_amount` | `self` | `` |  |
| `get_income_form_other_sources` | `self` | `` |  |
| `get_component_totals` | `self, component_type, depends_on_payment_days` | `` |  |
| `email_salary_slip` | `self` | `` |  |
| `update_status` | `self, salary_slip` | `` |  |
| `set_status` | `self, status` | `` | Get and update status |
| `process_salary_structure` | `self, for_preview` | `` | Calculate salary after salary structure details have been updated |
| `pull_emp_details` | `self` | `` |  |
| `process_salary_based_on_working_days` | `self` | `` |  |
| `set_totals` | `self` | `` |  |
| `set_base_totals` | `self` | `` |  |
| `calculate_total_for_salary_slip_based_on_timesheet` | `self` | `` |  |
| `compute_year_to_date` | `self` | `` |  |
| `compute_month_to_date` | `self` | `` |  |
| `compute_component_wise_year_to_date` | `self` | `` |  |
| `get_year_to_date_period` | `self` | `` |  |
| `add_leave_balances` | `self` | `` |  |





## Functions

### `unlink_ref_doc_from_salary_slip`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Unlinks accrual Journal Entry from Salary Slips on cancellation
```
### `generate_password_for_pdf`
**Arguments:** `policy_template, employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_salary_component_data`
**Arguments:** `component`
**Decorators:** ``

**Docstring:**
```

```
### `get_payroll_payable_account`
**Arguments:** `company, payroll_entry`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_tax_by_tax_slab`
**Arguments:** `annual_taxable_earning, tax_slab, eval_globals, eval_locals`
**Decorators:** ``

**Docstring:**
```

```
### `eval_tax_slab_condition`
**Arguments:** `condition, eval_globals, eval_locals`
**Decorators:** ``

**Docstring:**
```

```
### `get_lwp_or_ppl_for_date_range`
**Arguments:** `employee, start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_slip_from_timesheet`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_missing_values`
**Arguments:** `time_sheet, target`
**Decorators:** ``

**Docstring:**
```

```
### `throw_error_message`
**Arguments:** `row, error, title, description`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_safe_eval`
**Arguments:** `code, eval_globals, eval_locals`
**Decorators:** ``

**Docstring:**
```
Old version of safe_eval from framework.

Note: current frappe.safe_eval transforms code so if you have nested
iterations with too much depth then it can hit recursion limit of python.
There's no workaround for this and people need large formulas in some
countries so this is alternate implementation for that.

WARNING: DO NOT use this function anywhere else outside of this file.
```
### `_check_attributes`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_email_salary_slips`
**Arguments:** `names`
**Decorators:** ``

**Docstring:**
```
enqueue bulk emailing salary slips
```
### `email_salary_slips`
**Arguments:** `names`
**Decorators:** ``

**Docstring:**
```

```

