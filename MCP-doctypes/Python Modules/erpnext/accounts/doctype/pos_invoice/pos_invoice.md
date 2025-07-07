# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_invoice/pos_invoice.py`

## Classes

### `POSInvoice`
**Inherits:** `SalesInvoice`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `clear_unallocated_mode_of_payments` | `self` | `` |  |
| `create_and_add_consolidated_sales_invoice` | `self` | `` |  |
| `create_return_sales_invoice` | `self` | `` |  |
| `delink_serial_and_batch_bundle` | `self` | `` |  |
| `submit_serial_batch_bundle` | `self, table_name` | `` |  |
| `check_phone_payments` | `self` | `` |  |
| `validate_stock_availablility` | `self` | `` |  |
| `validate_is_pos_using_sales_invoice` | `self` | `` |  |
| `validate_serialised_or_batched_item` | `self` | `` |  |
| `validate_return_items_qty` | `self` | `` |  |
| `validate_mode_of_payment` | `self` | `` |  |
| `validate_change_account` | `self` | `` |  |
| `validate_change_amount` | `self` | `` |  |
| `validate_payment_amount` | `self` | `` |  |
| `validate_company_with_pos_company` | `self` | `` |  |
| `set_outstanding_amount` | `self` | `` |  |
| `validate_loyalty_transaction` | `self` | `` |  |
| `set_status` | `self, update, status, update_modified` | `` |  |
| `set_pos_fields` | `self, for_validate` | `` | Set retail related fields from POS Profiles |
| `set_missing_values` | `self, for_validate` | `` |  |
| `reset_mode_of_payments` | `self` | `` |  |
| `create_payment_request` | `self` | `` |  |
| `get_new_payment_request` | `self, mop` | `` |  |
| `get_existing_payment_request` | `self, pay` | `` |  |
| `update_payments` | `self, payments` | `` |  |





## Functions

### `get_stock_availability`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_bundle_availability`
**Arguments:** `bundle_item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_bin_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_reserved_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_return`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_merge_log`
**Arguments:** `invoices`
**Decorators:** ``

**Docstring:**
```

```
### `add_return_modes`
**Arguments:** `doc, pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `item_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_group`
**Arguments:** `pos_profile`
**Decorators:** ``

**Docstring:**
```

```
### `create_payments_on_invoice`
**Arguments:** `doc, idx, payment_details`
**Decorators:** ``

**Docstring:**
```

```

