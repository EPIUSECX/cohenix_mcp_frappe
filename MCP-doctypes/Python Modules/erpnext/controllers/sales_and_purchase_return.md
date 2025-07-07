# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/sales_and_purchase_return.py`

## Classes

### `StockOverReturnError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `validate_return`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_return_against`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_returned_items`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `validate_quantity`
**Arguments:** `doc, key, args, ref, valid_items, already_returned_items`
**Decorators:** ``

**Docstring:**
```

```
### `get_ref_item_dict`
**Arguments:** `valid_items, ref_item_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_already_returned_items`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_returned_qty_map_for_row`
**Arguments:** `return_against, party, row_name, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `make_return_doc`
**Arguments:** `doctype, source_name, target_doc, return_against_rejected_qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_rate_for_return`
**Arguments:** `voucher_type, voucher_no, item_code, return_against, item_row, voucher_detail_no, sle`
**Decorators:** ``

**Docstring:**
```

```
### `get_return_against_item_fields`
**Arguments:** `voucher_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_filters`
**Arguments:** `voucher_type, voucher_no, voucher_detail_no, return_against, item_code, return_against_item_field, item_row`
**Decorators:** ``

**Docstring:**
```

```
### `get_returned_serial_nos`
**Arguments:** `child_doc, parent_doc, serial_no_field, ignore_voucher_detail_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_returned_batches`
**Arguments:** `child_doc, parent_doc, batch_no_field, ignore_voucher_detail_no`
**Decorators:** ``

**Docstring:**
```

```
### `available_serial_batch_for_return`
**Arguments:** `field, doctype, reference_ids, is_rejected`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_serial_batches`
**Arguments:** `field, doctype, reference_ids, is_rejected`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_batches_based_on_bundle`
**Arguments:** `field, _bundle_ids`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_and_batch_bundle`
**Arguments:** `field, doctype, reference_ids, is_rejected`
**Decorators:** ``

**Docstring:**
```

```
### `filter_serial_batches`
**Arguments:** `parent_doc, data, row, warehouse_field, qty_field`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_batch_qty`
**Arguments:** `parent_doc, batch_no, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `make_serial_batch_bundle_for_return`
**Arguments:** `data, child_doc, parent_doc, warehouse_field, qty_field`
**Decorators:** ``

**Docstring:**
```

```
### `get_available_serial_nos`
**Arguments:** `serial_nos, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_data`
**Arguments:** `invoice`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoice_item_returned_qty`
**Arguments:** `doctype, invoice, customer, item_row_name`
**Decorators:** ``

**Docstring:**
```

```
### `is_invoice_returnable`
**Arguments:** `doctype, invoice`
**Decorators:** ``

**Docstring:**
```

```
### `get_sales_invoice_item_from_consolidated_invoice`
**Arguments:** `return_against_pos_invoice, pos_invoice_item`
**Decorators:** ``

**Docstring:**
```

```

