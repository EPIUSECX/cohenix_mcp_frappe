# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/expense_claim/expense_claim.py`

## Classes

### `InvalidExpenseApproverError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ExpenseApproverIdentityError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `MismatchError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ExpenseClaim`
**Inherits:** `AccountsController, PWANotificationsMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_status` | `self, update` | `` |  |
| `validate_company_and_department` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `publish_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `update_claimed_amount_in_employee_advance` | `self` | `` |  |
| `update_task_and_project` | `self` | `` |  |
| `make_gl_entries` | `self, cancel` | `` |  |
| `get_gl_entries` | `self` | `` |  |
| `add_tax_gl_entries` | `self, gl_entries` | `` |  |
| `validate_account_details` | `self` | `` |  |
| `calculate_total_amount` | `self` | `` |  |
| `calculate_taxes` | `self` | `` |  |
| `validate_advances` | `self` | `` |  |
| `validate_sanctioned_amount` | `self` | `` |  |
| `set_expense_account` | `self, validate` | `` |  |





## Functions

### `update_reimbursed_amount`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_reimbursed_amount`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_outstanding_amount_for_claim`
**Arguments:** `claim`
**Decorators:** ``

**Docstring:**
```

```
### `make_bank_entry`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claim_account_and_cost_center`
**Arguments:** `expense_claim_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claim_account`
**Arguments:** `expense_claim_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_advances`
**Arguments:** `employee, advance_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claim`
**Arguments:** `employee_name, company, employee_advance_name, posting_date, paid_amount, claimed_amount, return_amount`
**Decorators:** ``

**Docstring:**
```

```
### `update_payment_for_expense_claim`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Updates payment/reimbursed amount in Expense Claim
on Payment Entry/Journal Entry cancellation/submission
```
### `update_outstanding_amount_in_payment_entry`
**Arguments:** `expense_claim, pe_reference`
**Decorators:** ``

**Docstring:**
```
updates outstanding amount back in Payment Entry reference
```
### `validate_expense_claim_in_jv`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Validates Expense Claim amount in Journal Entry
```
### `make_expense_claim_for_delivery_trip`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_allocation_amount`
**Arguments:** `paid_amount, claimed_amount, return_amount, unclaimed_amount`
**Decorators:** ``

**Docstring:**
```

```

