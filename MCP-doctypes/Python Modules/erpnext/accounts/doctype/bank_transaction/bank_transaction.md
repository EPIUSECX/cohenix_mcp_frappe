# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_transaction/bank_transaction.py`

## Classes

### `BankTransaction`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_currency` | `self` | `` | Bank Transaction should be on the same currency as the Bank Account. |
| `set_status` | `self` | `` |  |
| `validate_duplicate_references` | `self` | `` | Make sure the same voucher is not allocated twice within the same Bank Transaction |
| `update_allocated_amount` | `self` | `` |  |
| `delink_old_payment_entries` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `before_update_after_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `add_payment_entries` | `self, vouchers` | `` | Add the vouchers with zero allocation. Save() will perform the allocations and clearance |
| `allocate_payment_entries` | `self` | `` | Refactored from bank reconciliation tool.
Non-zero allocations must be amended/cleared manually
Get the bank transaction amount (b) and remove as we allocate
For each payment_entry if allocated_amount == 0:
- get the amount already allocated against all transactions (t), need latest date
- get the voucher amount (from gl) (v)
- allocate (a = v - t)
    - a = 0: should already be cleared, so clear & remove payment_entry
    - 0 < a <= u: allocate a & clear
    - 0 < a, a > u: allocate u
    - 0 > a: Error: already over-allocated
- clear means: set the latest transaction date as clearance date |
| `remove_payment_entries` | `self` | `` |  |
| `remove_payment_entry` | `self, payment_entry` | `` | Clear payment entry and clearance |
| `delink_payment_entry` | `self, payment_entry` | `` |  |
| `clear_linked_payment_entry` | `self, payment_entry, clearance_date` | `` |  |
| `update_linked_bank_transaction` | `self, bank_transaction_name, allocated_amount` | `` | For when a second bank transaction has fixed another, e.g. refund |
| `auto_set_party` | `self` | `` |  |





## Functions

### `get_doctypes_for_bank_reconciliation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get Bank Reconciliation doctypes from all the apps
```
### `get_clearance_details`
**Arguments:** `transaction, payment_entry, bt_allocations, gl_entries, gl_bank_account`
**Decorators:** ``

**Docstring:**
```
There should only be one bank gl entry for a voucher, except for JE.
For JE, there can be multiple bank gl entries for the same account.
In this case, the allocable_amount will be the sum of amounts of all gl entries of the account.
There will be no gl entry for a Bank Transaction so return the unallocated amount.
Should only clear the voucher if all bank gl entries are allocated.
```
### `get_related_bank_gl_entries`
**Arguments:** `docs`
**Decorators:** ``

**Docstring:**
```

```
### `get_total_allocated_amount`
**Arguments:** `docs`
**Decorators:** ``

**Docstring:**
```
Gets the sum of allocations for a voucher on each bank GL account
along with the latest bank transaction date
NOTE: query may also include just saved vouchers/payments but with zero allocated_amount
```
### `get_reconciled_bank_transactions`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `remove_from_bank_transaction`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```
Remove a (cancelled) voucher from all Bank Transactions.
```

