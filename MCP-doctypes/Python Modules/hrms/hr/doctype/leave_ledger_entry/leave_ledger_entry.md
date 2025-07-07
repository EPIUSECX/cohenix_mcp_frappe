# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/leave_ledger_entry/leave_ledger_entry.py`

## Classes

### `InvalidLeaveLedgerEntry`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LeaveLedgerEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `validate_leave_allocation_against_leave_application`
**Arguments:** `ledger`
**Decorators:** ``

**Docstring:**
```
Checks that leave allocation has no leave application against it
```
### `create_leave_ledger_entry`
**Arguments:** `ref_doc, args, submit`
**Decorators:** ``

**Docstring:**
```

```
### `delete_ledger_entry`
**Arguments:** `ledger`
**Decorators:** ``

**Docstring:**
```
Delete ledger entry on cancel of leave application/allocation/encashment
```
### `get_previous_expiry_ledger_entry`
**Arguments:** `ledger`
**Decorators:** ``

**Docstring:**
```
Returns the expiry ledger entry having same creation date as the ledger entry to be cancelled
```
### `process_expired_allocation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Check if a carry forwarded allocation has expired and create a expiry ledger entry
Case 1: carry forwarded expiry period is set for the leave type,
        create a separate leave expiry entry against each entry of carry forwarded and non carry forwarded leaves
Case 2: leave type has no specific expiry period for carry forwarded leaves
        and there is no carry forwarded leave allocation, create a single expiry against the remaining leaves.
```
### `create_expiry_ledger_entry`
**Arguments:** `allocations`
**Decorators:** ``

**Docstring:**
```
Create ledger entry for expired allocation
```
### `get_remaining_leaves`
**Arguments:** `allocation`
**Decorators:** ``

**Docstring:**
```
Returns remaining leaves from the given allocation
```
### `expire_allocation`
**Arguments:** `allocation, expiry_date`
**Decorators:** ``

**Docstring:**
```
expires non-carry forwarded allocation
```
### `expire_carried_forward_allocation`
**Arguments:** `allocation`
**Decorators:** ``

**Docstring:**
```
Expires remaining leaves in the on carried forward allocation
```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

