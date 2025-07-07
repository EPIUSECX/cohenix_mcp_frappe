# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/payroll/doctype/payroll_entry/test_payroll_entry.py`

## Classes

### `TestPayrollEntry`
**Inherits:** `FrappeTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_payroll_entry` | `self` | `` |  |
| `test_multi_currency_payroll_entry` | `self` | `` |  |
| `test_payroll_entry_with_employee_cost_center` | `self` | `` |  |
| `test_employee_cost_center_breakup` | `self` | `` | Test only the latest salary structure assignment is considered for cost center breakup |
| `test_get_end_date` | `self` | `` |  |
| `test_loan_with_settings_enabled` | `self` | `if_lending_app_installed` |  |
| `test_loan_with_settings_disabled` | `self` | `if_lending_app_installed` |  |
| `test_salary_slip_operation_queueing` | `self` | `` |  |
| `test_salary_slip_operation_failure` | `self` | `` |  |
| `test_payroll_entry_cancellation` | `self` | `` |  |
| `test_payroll_entry_status` | `self` | `` |  |
| `test_payroll_entry_cancellation_against_cancelled_journal_entry` | `self` | `` |  |
| `test_payroll_accrual_journal_entry_with_employee_tagging` | `self` | `` |  |
| `test_payroll_accrual_journal_entry_without_employee_tagging` | `self` | `` |  |
| `test_advance_deduction_in_accrual_journal_entry` | `self` | `` |  |
| `test_employee_wise_bank_entry_with_cost_centers` | `self` | `` |  |
| `test_validate_attendance` | `self` | `` |  |
| `test_skip_bank_entry_for_employees_with_zero_amount` | `self` | `` |  |
| `test_loan_repayment_from_salary` | `self` | `if_lending_app_installed` |  |
| `test_loan_repayment_from_salary_with_employee_tagging` | `self` | `if_lending_app_installed` |  |
| `run_test_for_loan_repayment_from_salary` | `self` | `` |  |





## Functions

### `get_payroll_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_payroll_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_account`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `setup_salary_structure`
**Arguments:** `employee, company_doc, currency, salary_structure`
**Decorators:** ``

**Docstring:**
```

```
### `create_assignments_with_cost_centers`
**Arguments:** `employee1, employee2`
**Decorators:** ``

**Docstring:**
```

```
### `setup_lending`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_loan_for_employee`
**Arguments:** `applicant`
**Decorators:** ``

**Docstring:**
```

```
### `get_repayment_party_type`
**Arguments:** `loan`
**Decorators:** ``

**Docstring:**
```

```
### `submit_bank_entry`
**Arguments:** `payroll_entry_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_linked_journal_entries`
**Arguments:** `payroll_entry_id, docstatus`
**Decorators:** ``

**Docstring:**
```

```

