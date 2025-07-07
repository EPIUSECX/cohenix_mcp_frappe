# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/serial_and_batch_bundle/serial_and_batch_bundle.py`

## Classes

### `SerialNoExistsInFutureTransactionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BatchNegativeStockError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoDuplicateError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoWarehouseError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialandBatchBundle`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_voucher_detail_no` | `self` | `` |  |
| `allow_existing_serial_nos` | `self` | `` |  |
| `reset_serial_batch_bundle` | `self` | `` |  |
| `set_batch_no` | `self` | `` |  |
| `validate_serial_nos_inventory` | `self` | `` |  |
| `validate_serial_nos_duplicate` | `self` | `` |  |
| `throw_error_message` | `self, message, exception` | `` |  |
| `set_incoming_rate` | `self, parent, row, save, allow_negative_stock` | `` |  |
| `set_valuation_rate_for_return_entry` | `self, return_against, row, save` | `` |  |
| `validate_returned_serial_batch_no` | `self, return_against, row, original_inv_details` | `` |  |
| `get_valuation_rate_for_return_entry` | `self, return_against` | `` |  |
| `calculate_total_qty` | `self, save` | `` |  |
| `get_serial_nos` | `self` | `` |  |
| `update_valuation_rate` | `self, valuation_rate, save` | `` |  |
| `set_incoming_rate_for_outward_transaction` | `self, row, save, allow_negative_stock` | `` |  |
| `validate_negative_batch` | `self, batch_no, available_qty` | `` |  |
| `is_stock_reco_for_valuation_adjustment` | `self, available_qty` | `` |  |
| `get_sle_for_outward_transaction` | `self` | `` |  |
| `get_return_against` | `self, parent` | `` |  |
| `set_incoming_rate_for_inward_transaction` | `self, row, save` | `` |  |
| `set_serial_and_batch_values` | `self, parent, row, qty_field` | `` |  |
| `validate_voucher_no` | `self` | `` |  |
| `check_future_entries_exists` | `self, is_cancelled` | `` |  |
| `get_serial_nos_for_validate` | `self, is_cancelled` | `` |  |
| `get_skip_serial_nos_for_stock_reconciliation` | `self, is_cancelled` | `` |  |
| `reset_qty` | `self, row, qty_field` | `` |  |
| `validate_quantity` | `self, row, qty_field` | `` |  |
| `get_qty_field` | `self, row, qty_field` | `` |  |
| `set_is_outward` | `self` | `` |  |
| `set_warehouse` | `self` | `` |  |
| `calculate_qty_and_amount` | `self, save` | `` |  |
| `calculate_outgoing_rate` | `self` | `` |  |
| `validate_serial_and_batch_no` | `self` | `` |  |
| `validate_serial_batch_no` | `self, serial_batches` | `` |  |
| `validate_incorrect_serial_nos` | `self, serial_nos` | `` |  |
| `validate_incorrect_batch_nos` | `self, batch_nos` | `` |  |
| `validate_serial_and_batch_no_for_returned` | `self` | `` |  |
| `get_orignal_document_data` | `self` | `` |  |
| `validate_duplicate_serial_and_batch_no` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `delink_serial_and_batch_bundle` | `self` | `` |  |
| `child_table` | `self` | `property` |  |
| `delink_refernce_from_voucher` | `self` | `` |  |
| `delink_reference_from_batch` | `self` | `` |  |
| `validate_serial_and_batch_data` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `set_purchase_document_no` | `self` | `` |  |
| `validate_serial_and_batch_inventory` | `self` | `` |  |
| `validate_batch_inventory` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate_voucher_no_docstatus` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `add_serial_batch` | `self, data` | `` |  |
| `delete_serial_batch_entries` | `self` | `` |  |





## Functions

### `download_blank_csv_template`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```

```
### `upload_csv_file`
**Arguments:** `item_code, file_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_batch_from_csv`
**Arguments:** `item_code, file_path`
**Decorators:** ``

**Docstring:**
```

```
### `parse_csv_file_to_get_serial_batch`
**Arguments:** `reader`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_batch_from_data`
**Arguments:** `item_code, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `create_serial_nos`
**Arguments:** `item_code, serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `make_serial_nos`
**Arguments:** `item_code, serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `make_batch_nos`
**Arguments:** `item_code, batch_nos`
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
### `get_serial_batch_ledgers`
**Arguments:** `item_code, docstatus, voucher_no, name, child_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_filters_for_bundle`
**Arguments:** `item_code, docstatus, voucher_no, name, child_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_serial_and_batch_bundle`
**Arguments:** `child_row`
**Decorators:** ``

**Docstring:**
```

```
### `add_serial_batch_ledgers`
**Arguments:** `entries, child_row, doc, warehouse, do_not_save`
**Decorators:** ``

**Docstring:**
```

```
### `create_serial_batch_no_ledgers`
**Arguments:** `entries, child_row, parent_doc, warehouse, do_not_save`
**Decorators:** ``

**Docstring:**
```

```
### `get_batch`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_type_of_transaction`
**Arguments:** `parent_doc, child_row`
**Decorators:** ``

**Docstring:**
```

```
### `update_serial_batch_no_ledgers`
**Arguments:** `bundle, entries, child_row, parent_doc, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `update_serial_or_batch`
**Arguments:** `bundle_id, serial_no, batch_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_and_batch_ledger`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_auto_data`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_available_batches_qty`
**Arguments:** `available_batches`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_serial_nos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_non_expired_batches`
**Arguments:** `batches`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_based_on_posting_date`
**Arguments:** `kwargs, ignore_serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `get_bundle_wise_serial_nos`
**Arguments:** `data, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_serial_nos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```
Returns a list of `Serial No` reserved in POS Invoice and Stock Reservation Entry.
```
### `get_reserved_voucher_details`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_serial_nos_for_pos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_reserved_serial_nos_for_sre`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```
Returns a list of `Serial No` reserved in Stock Reservation Entry.
```
### `get_reserved_batches_for_pos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```
Returns a dict of `Batch No` followed by the `Qty` reserved in POS Invoices.
```
### `get_reserved_batches_for_sre`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```
Returns a dict of `Batch No` followed by the `Qty` reserved in Stock Reservation Entry.
```
### `get_auto_batch_nos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `filter_zero_near_batches`
**Arguments:** `available_batches, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_qty_based_available_batches`
**Arguments:** `available_batches, qty`
**Decorators:** ``

**Docstring:**
```

```
### `update_available_batches`
**Arguments:** `available_batches`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_batches`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_voucher_wise_serial_batch_from_bundle`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_picked_batches`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_picked_serial_nos`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_ledgers_from_serial_batch_bundle`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_ledgers_for_serial_nos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_ledgers_batches`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_batch_no_from_serial_no`
**Arguments:** `serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `is_serial_batch_no_exists`
**Arguments:** `item_code, type_of_transaction, serial_no, batch_no`
**Decorators:** ``

**Docstring:**
```

```
### `make_serial_no`
**Arguments:** `serial_no, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `make_batch_no`
**Arguments:** `batch_no, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `is_duplicate_serial_no`
**Arguments:** `bundle_id, serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `parse_serial_nos`
**Arguments:** `serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_reco_details`
**Arguments:** `voucher_detail_no`
**Decorators:** ``

**Docstring:**
```

```

