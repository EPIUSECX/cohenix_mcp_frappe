# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/expense_claim/test_expense_claim.py`

## Classes

### `TestExpenseClaim`
**Inherits:** `HRMSTestSuite`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `test_total_expense_claim_for_project` | `self` | `` |  |
| `test_expense_claim_status_as_payment_from_journal_entry` | `self` | `` |  |
| `test_expense_claim_status_as_payment_from_payment_entry` | `self` | `` |  |
| `test_expense_claim_status_as_payment_allocation_using_pr` | `self` | `` |  |
| `test_expense_claim_against_fully_paid_advances` | `self` | `` |  |
| `test_advance_amount_allocation_against_claim_with_taxes` | `self` | `` |  |
| `test_expense_claim_partially_paid_via_advance` | `self` | `` |  |
| `test_expense_claim_with_deducted_returned_advance` | `self` | `` |  |
| `test_expense_claim_gl_entry` | `self` | `` |  |
| `test_invalid_gain_loss_for_expense_claim` | `self` | `` |  |
| `test_rejected_expense_claim` | `self` | `` |  |
| `test_expense_approver_perms` | `self` | `` |  |
| `test_multiple_payment_entries_against_expense` | `self` | `` |  |
| `test_expense_claim_against_delivery_trip` | `self` | `` |  |
| `test_journal_entry_against_expense_claim` | `self` | `` |  |
| `test_accounting_dimension_mapping` | `self` | `` |  |
| `test_rounding` | `self` | `` |  |
| `test_repost` | `self` | `` |  |
| `test_company_department_validation` | `self` | `` |  |





## Functions

### `get_payable_account`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `generate_taxes`
**Arguments:** `company, rate`
**Decorators:** ``

**Docstring:**
```

```
### `make_expense_claim`
**Arguments:** `payable_account, amount, sanctioned_amount, company, account, project, task_name, do_not_submit, taxes, employee`
**Decorators:** ``

**Docstring:**
```

```
### `make_payment_entry`
**Arguments:** `expense_claim, amount`
**Decorators:** ``

**Docstring:**
```

```
### `make_journal_entry`
**Arguments:** `expense_claim, do_not_submit`
**Decorators:** ``

**Docstring:**
```

```
### `create_payment_reconciliation`
**Arguments:** `company, employee, payable_account`
**Decorators:** ``

**Docstring:**
```

```
### `allocate_using_payment_reconciliation`
**Arguments:** `expense_claim, employee, journal_entry, payable_account`
**Decorators:** ``

**Docstring:**
```

```
### `create_project`
**Arguments:** `project_name`
**Decorators:** ``

**Docstring:**
```

```

