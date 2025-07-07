# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/payroll_entry/payroll_entry.py`

## Classes

### `PayrollEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_status` | `self, status, update` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_existing_salary_slips` | `self` | `` |  |
| `validate_payroll_payable_account` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `cancel` | `self` | `` |  |
| `delete_linked_salary_slips` | `self` | `` |  |
| `cancel_linked_journal_entries` | `self` | `` |  |
| `get_linked_salary_slips` | `self` | `` |  |
| `make_filters` | `self` | `` |  |
| `fill_employee_details` | `self` | `` |  |
| `update_employees_with_withheld_salaries` | `self` | `` |  |
| `create_salary_slips` | `self` | `` | Creates salary slip for selected employees if already not created |
| `get_sal_slip_list` | `self, ss_status, as_dict` | `` | Returns list of salary slips based on selected criteria |
| `submit_salary_slips` | `self` | `` |  |
| `email_salary_slip` | `self, submitted_ss` | `` |  |
| `get_salary_component_account` | `self, salary_component` | `` |  |
| `get_salary_components` | `self, component_type` | `` |  |
| `get_salary_component_total` | `self, component_type, employee_wise_accounting_enabled` | `` |  |
| `should_add_component_to_accrual_jv` | `self, component_type, item` | `` |  |
| `get_advance_deduction` | `self, component_type, item` | `` |  |
| `add_advance_deduction_entry` | `self, item, amount, cost_center, employee_advance` | `` |  |
| `set_accounting_entries_for_advance_deductions` | `self, accounts, currencies, company_currency, accounting_dimensions, precision, payable_amount` | `` |  |
| `set_employee_based_payroll_payable_entries` | `self, component_type, employee, amount, salary_structure` | `` |  |
| `get_payroll_cost_centers_for_employee` | `self, employee, salary_structure` | `` |  |
| `get_account` | `self, component_dict` | `` |  |
| `make_accrual_jv_entry` | `self, submitted_salary_slips` | `` |  |
| `make_journal_entry` | `self, accounts, currencies, payroll_payable_account, voucher_type, user_remark, submitted_salary_slips, submit_journal_entry` | `` |  |
| `get_payable_amount_for_earnings_and_deductions` | `self, accounts, earnings, deductions, currencies, company_currency, accounting_dimensions, precision, payable_amount` | `` |  |
| `set_payable_amount_against_payroll_payable_account` | `self, accounts, currencies, company_currency, accounting_dimensions, precision, payable_amount, payroll_payable_account, employee_wise_accounting_enabled` | `` |  |
| `get_accounting_entries_and_payable_amount` | `self, account, cost_center, amount, currencies, company_currency, payable_amount, accounting_dimensions, precision, entry_type, party, accounts, reference_type, reference_name, is_advance` | `` |  |
| `update_accounting_dimensions` | `self, row, accounting_dimensions` | `` |  |
| `get_amount_and_exchange_rate_for_journal_entry` | `self, account, amount, company_currency, currencies` | `` |  |
| `has_bank_entries` | `self` | `` |  |
| `make_bank_entry` | `self, for_withheld_salaries` | `` |  |
| `get_salary_slip_details` | `self, for_withheld_salaries` | `` |  |
| `process_loan_repayments_for_bank_entry` | `self, salary_details` | `if_lending_app_installed` |  |
| `set_accounting_entries_for_bank_entry` | `self, je_payment_amount, user_remark` | `` |  |
| `set_journal_entry_in_salary_slips` | `self, submitted_salary_slips, jv_name` | `` |  |
| `set_start_end_dates` | `self` | `` |  |
| `get_employees_with_unmarked_attendance` | `self` | `` |  |
| `get_employee_and_attendance_details` | `self` | `` | Returns a list of employee and attendance details like
[
        {
                "name": "HREMP00001",
                "date_of_joining": "2019-01-01",
                "relieving_date": "2022-01-01",
                "holiday_list": "Holiday List Company",
                "attendance_count": 22
        }
] |
| `get_payroll_dates_for_employee` | `self, employee_details` | `` |  |
| `get_holidays_count` | `self, holiday_list, start_date, end_date` | `` | Returns number of holidays between start and end dates in the holiday list |





## Functions

### `get_salary_structure`
**Arguments:** `company, currency, salary_slip_based_on_timesheet, payroll_frequency`
**Decorators:** ``

**Docstring:**
```

```
### `get_filtered_employees`
**Arguments:** `sal_struct, filters, searchfield, search_string, fields, as_dict, limit, offset, ignore_match_conditions`
**Decorators:** ``

**Docstring:**
```

```
### `set_fields_to_select`
**Arguments:** `query, fields`
**Decorators:** ``

**Docstring:**
```

```
### `set_searchfield`
**Arguments:** `query, searchfield, search_string, qb_object`
**Decorators:** ``

**Docstring:**
```

```
### `set_filter_conditions`
**Arguments:** `query, filters, qb_object`
**Decorators:** ``

**Docstring:**
```
Append optional filters to employee query
```
### `set_match_conditions`
**Arguments:** `query, qb_object`
**Decorators:** ``

**Docstring:**
```

```
### `remove_payrolled_employees`
**Arguments:** `emp_list, start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_start_end_dates`
**Arguments:** `payroll_frequency, start_date, company`
**Decorators:** ``

**Docstring:**
```
Returns dict of start and end dates for given payroll frequency based on start_date
```
### `get_frequency_kwargs`
**Arguments:** `frequency_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_end_date`
**Arguments:** `start_date, frequency`
**Decorators:** ``

**Docstring:**
```

```
### `get_month_details`
**Arguments:** `year, month`
**Decorators:** ``

**Docstring:**
```

```
### `log_payroll_failure`
**Arguments:** `process, payroll_entry, error`
**Decorators:** ``

**Docstring:**
```

```
### `create_salary_slips_for_employees`
**Arguments:** `employees, args, publish_progress`
**Decorators:** ``

**Docstring:**
```

```
### `show_payroll_submission_status`
**Arguments:** `submitted, unsubmitted, payroll_entry`
**Decorators:** ``

**Docstring:**
```

```
### `get_existing_salary_slips`
**Arguments:** `employees, args`
**Decorators:** ``

**Docstring:**
```

```
### `submit_salary_slips_for_employees`
**Arguments:** `payroll_entry, salary_slips, publish_progress`
**Decorators:** ``

**Docstring:**
```

```
### `get_payroll_entries_for_jv`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_list`
**Arguments:** `filters, searchfield, search_string, fields, as_dict, limit, offset, ignore_match_conditions`
**Decorators:** ``

**Docstring:**
```

```
### `employee_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_salary_withholdings`
**Arguments:** `start_date, end_date, employee, pluck`
**Decorators:** ``

**Docstring:**
```

```

