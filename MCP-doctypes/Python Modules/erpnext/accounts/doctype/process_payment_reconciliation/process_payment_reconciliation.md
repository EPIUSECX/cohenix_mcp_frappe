# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/process_payment_reconciliation/process_payment_reconciliation.py`

## Classes

### `ProcessPaymentReconciliation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_receivable_payable_account` | `self` | `` |  |
| `validate_bank_cash_account` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `get_reconciled_count`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_pr_instance`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `is_job_running`
**Arguments:** `job_name`
**Decorators:** ``

**Docstring:**
```

```
### `pause_job_for_doc`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```

```
### `trigger_job_for_doc`
**Arguments:** `docname`
**Decorators:** ``

**Docstring:**
```
Trigger background job
```
### `trigger_reconciliation_for_queued_docs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Will be called from Cron Job
Fetch queued docs and start reconciliation process for each one
```
### `reconcile_based_on_filters`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Identify current state of document and execute next tasks in background
```
### `get_next_allocation`
**Arguments:** `log`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_and_allocate`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Fetch Invoices and Payments based on filters applied. FIFO ordering is used for allocation.
```
### `reconcile`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `is_any_doc_running`
**Arguments:** `for_filter`
**Decorators:** ``

**Docstring:**
```

```

