# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/salary_slip/test_salary_slip.py`

## Classes

### `TestSalarySlip`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_leave_details` | `self` | `` |  |
| `test_employee_status_inactive` | `self` | `` |  |
| `test_payment_days_based_on_attendance` | `self` | `` |  |
| `test_payment_days_considering_half_days_unmarked_as_absent` | `self` | `` |  |
| `test_payment_days_considering_half_days_unmarked_as_present` | `self` | `` |  |
| `test_payment_days_for_mid_joinee_including_holidays` | `self` | `` |  |
| `test_payment_days_for_mid_joinee_including_holidays_and_unmarked_days` | `self` | `` |  |
| `test_payment_days_for_mid_joinee_excluding_holidays` | `self` | `` |  |
| `test_payment_days_based_on_leave_application` | `self` | `` |  |
| `test_payment_days_calculation_for_lwp_on_month_boundaries` | `self` | `` | Tests LWP calculation leave applications created on month boundaries |
| `test_payment_days_in_salary_slip_based_on_timesheet` | `self` | `` |  |
| `test_component_amount_dependent_on_another_payment_days_based_component` | `self` | `` |  |
| `test_salary_slip_with_holidays_included` | `self` | `` |  |
| `test_salary_slip_with_holidays_excluded` | `self` | `` |  |
| `test_consider_marked_attendance_on_holidays` | `self` | `` |  |
| `test_consider_marked_attendance_on_holidays_with_unmarked_attendance` | `self` | `` |  |
| `test_consider_marked_attendance_on_holidays_with_half_day_on_holiday` | `self` | `` |  |
| `test_payment_days` | `self` | `` |  |
| `test_employee_salary_slip_read_permission` | `self` | `` |  |
| `test_email_salary_slip` | `self` | `` |  |
| `test_email_salary_slip_with_email_template` | `self` | `` |  |
| `test_loan_repayment_salary_slip` | `self` | `if_lending_app_installed` |  |
| `test_payroll_frequency` | `self` | `` |  |
| `test_loan_write_off_salary_slip` | `self` | `if_lending_app_installed` |  |
| `test_multi_currency_salary_slip` | `self` | `` |  |
| `test_year_to_date_computation` | `self` | `` |  |
| `test_component_wise_year_to_date_computation` | `self` | `` |  |
| `test_tax_for_payroll_period` | `self` | `` |  |
| `test_default_amount` | `self` | `` |  |
| `test_tax_for_recurring_additional_salary` | `self` | `` |  |
| `test_salary_slip_from_timesheet` | `self` | `` |  |
| `test_do_not_show_statistical_component_in_slip` | `self` | `` |  |
| `test_statistical_component_based_on_payment_days` | `self` | `` | Tests whether component using statistical component in the formula
gets the updated value based on payment days |
| `make_activity_for_employee` | `self` | `` |  |
| `test_salary_slip_generation_against_opening_entries_in_ssa` | `self` | `` |  |
| `test_income_tax_breakup_fields` | `self` | `` |  |
| `test_consistent_future_earnings_irrespective_of_payment_days` | `self` | `` | For CTC calculation, verifies that future non taxable earnings remain
consistent irrespective of the payment days of current month |
| `test_tax_period_for_mid_month_payroll_period` | `self` | `` |  |
| `test_lwp_calculation_based_on_relieving_date` | `self` | `` |  |
| `test_zero_value_component` | `self` | `` |  |
| `test_component_default_amount_against_statistical_component` | `self` | `` |  |
| `test_variable_tax_component` | `self` | `` |  |
| `test_opening_balances_excluded_from_tax_calculation` | `self` | `` | tests if opening balances in salary structure assignment are excluded from tax when assignment date is before payroll period |
| `test_tax_payable_with_tax_relief_and_marginal_relief_limits` | `self` | `` |  |


### `TestSalarySlipSafeEval`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_safe_eval_for_salary_slip` | `self` | `` |  |





## Functions

### `make_income_tax_components`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_no_of_days`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_employee_salary_slip`
**Arguments:** `emp_id, payroll_frequency, salary_structure, posting_date, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_component`
**Arguments:** `salary_components, test_tax, company_list`
**Decorators:** ``

**Docstring:**
```

```
### `set_salary_component_account`
**Arguments:** `sal_comp, company_list`
**Decorators:** ``

**Docstring:**
```

```
### `create_account`
**Arguments:** `account_name, company, parent_account, account_type`
**Decorators:** ``

**Docstring:**
```

```
### `make_earning_salary_component`
**Arguments:** `setup, test_tax, company_list, include_flexi_benefits, test_statistical_comp`
**Decorators:** ``

**Docstring:**
```

```
### `make_deduction_salary_component`
**Arguments:** `setup, test_tax, company_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_tax_paid_in_period`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `create_exemption_declaration`
**Arguments:** `employee, payroll_period`
**Decorators:** ``

**Docstring:**
```

```
### `create_proof_submission`
**Arguments:** `employee, payroll_period, amount`
**Decorators:** ``

**Docstring:**
```

```
### `create_benefit_claim`
**Arguments:** `employee, payroll_period, amount, component`
**Decorators:** ``

**Docstring:**
```

```
### `create_tax_slab`
**Arguments:** `payroll_period, effective_date, allow_tax_exemption, dont_submit, currency, company, apply_tax_relief`
**Decorators:** ``

**Docstring:**
```

```
### `create_salary_slips_for_payroll_period`
**Arguments:** `employee, salary_structure, payroll_period, deduct_random, num`
**Decorators:** ``

**Docstring:**
```

```
### `create_additional_salary`
**Arguments:** `employee, payroll_period, amount`
**Decorators:** ``

**Docstring:**
```

```
### `make_leave_application`
**Arguments:** `employee, from_date, to_date, leave_type, company, half_day, half_day_date, submit`
**Decorators:** ``

**Docstring:**
```

```
### `setup_test`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_payroll_period`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_holiday_list`
**Arguments:** `list_name, from_date, to_date, add_weekly_offs, weekly_off_days`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_structure_for_payment_days_based_component_dependency`
**Arguments:** `test_statistical_comp`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_slip_for_payment_days_dependency_test`
**Arguments:** `employee, salary_structure`
**Decorators:** ``

**Docstring:**
```

```
### `create_recurring_additional_salary`
**Arguments:** `employee, salary_component, amount, from_date, to_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_structure_for_timesheet`
**Arguments:** `employee, company`
**Decorators:** ``

**Docstring:**
```

```
### `create_employee_other_income`
**Arguments:** `employee, payroll_period, company`
**Decorators:** ``

**Docstring:**
```

```
### `create_additional_salary_for_non_taxable_component`
**Arguments:** `employee, payroll_period, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_structure_for_statistical_component`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `make_salary_slip_with_non_taxable_component`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `mark_attendance`
**Arguments:** `employee, attendance_date, status, shift, ignore_validate, leave_type, late_entry, early_exit, half_day_status`
**Decorators:** ``

**Docstring:**
```

```
### `create_ss_email_template`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

