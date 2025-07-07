# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_invoice_merge_log/pos_invoice_merge_log.py`

## Classes

### `POSInvoiceMergeLog`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_duplicate_pos_invoices` | `self` | `` |  |
| `validate_customer` | `self` | `` |  |
| `validate_pos_invoice_status` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `process_merging_into_sales_invoice` | `self, data` | `` |  |
| `process_merging_into_credit_notes` | `self, data` | `` |  |
| `distinguish_return_pos_invoices` | `self, data, sales_invoice_doc` | `` |  |
| `merge_pos_invoice_into` | `self, invoice, data` | `` |  |
| `get_new_sales_invoice` | `self` | `` |  |
| `update_pos_invoices` | `self, invoice_docs, sales_invoice, credit_notes` | `` |  |
| `serial_and_batch_bundle_reference_for_pos_invoice` | `self` | `` |  |
| `delink_serial_and_batch_bundle` | `self` | `` |  |
| `get_serial_and_batch_bundles` | `self` | `` |  |
| `cancel_linked_invoices` | `self` | `` |  |





## Functions

### `update_item_wise_tax_detail`
**Arguments:** `consolidate_tax_row, tax_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_all_unconsolidated_invoices`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_invoice_customer_map`
**Arguments:** `pos_invoices`
**Decorators:** ``

**Docstring:**
```

```
### `split_invoices_by_accounting_dimension`
**Arguments:** `pos_invoices`
**Decorators:** ``

**Docstring:**
```

```
### `consolidate_pos_invoices`
**Arguments:** `pos_invoices, closing_entry`
**Decorators:** ``

**Docstring:**
```

```
### `unconsolidate_pos_invoices`
**Arguments:** `closing_entry`
**Decorators:** ``

**Docstring:**
```

```
### `split_invoices`
**Arguments:** `invoices`
**Decorators:** ``

**Docstring:**
```
Splits invoices into multiple groups
Use-case:
If a serial no is sold and later it is returned
then split the invoices such that the selling entry is merged first and then the return entry
```
### `create_merge_logs`
**Arguments:** `invoice_by_customer, closing_entry`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_merge_logs`
**Arguments:** `merge_logs, closing_entry`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_job`
**Arguments:** `job`
**Decorators:** ``

**Docstring:**
```

```
### `check_scheduler_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_error_message`
**Arguments:** `message`
**Decorators:** ``

**Docstring:**
```

```

