# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/payment_reconciliation/payment_reconciliation.py`

## Classes

### `PaymentReconciliation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `load_from_db` | `self` | `` |  |
| `save` | `self` | `` |  |
| `get_list` | `args` | `staticmethod` |  |
| `get_count` | `args` | `staticmethod` |  |
| `get_stats` | `args` | `staticmethod` |  |
| `db_insert` | `self` | `` |  |
| `db_update` | `self` | `` |  |
| `delete` | `self` | `` |  |
| `get_unreconciled_entries` | `self` | `` |  |
| `get_nonreconciled_payment_entries` | `self` | `` |  |
| `get_payment_entries` | `self` | `` |  |
| `get_jv_entries` | `self` | `` |  |
| `get_return_invoices` | `self` | `` |  |
| `get_dr_or_cr_notes` | `self` | `` |  |
| `add_payment_entries` | `self, non_reconciled_payments` | `` |  |
| `get_invoice_entries` | `self` | `` |  |
| `add_invoice_entries` | `self, non_reconciled_invoices` | `` |  |
| `get_difference_amount` | `self, payment_entry, invoice, allocated_amount` | `` |  |
| `is_auto_process_enabled` | `self` | `` |  |
| `calculate_difference_on_allocation_change` | `self, payment_entry, invoice, allocated_amount` | `` |  |
| `allocate_entries` | `self, args` | `` |  |
| `update_dimension_values_in_allocated_entries` | `self, res` | `` |  |
| `get_allocated_entry` | `self, pay, inv, allocated_amount` | `` |  |
| `reconcile_allocations` | `self, skip_ref_details_update_for_pe` | `` |  |
| `reconcile` | `self` | `` |  |
| `get_payment_details` | `self, row, dr_or_cr` | `` |  |
| `check_mandatory_to_fetch` | `self` | `` |  |
| `validate_entries` | `self` | `` |  |
| `get_invoice_exchange_map` | `self, invoices, payments` | `` |  |
| `validate_allocation` | `self` | `` |  |
| `build_dimensions_filter_conditions` | `self` | `` |  |
| `build_qb_filter_conditions` | `self, get_invoices, get_return_invoices` | `` |  |
| `get_journal_filter_conditions` | `self` | `` |  |





## Functions

### `reconcile_dr_cr_note`
**Arguments:** `dr_cr_notes, company, active_dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `adjust_allocations_for_taxes`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_queries_for_dimension_filters`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```

