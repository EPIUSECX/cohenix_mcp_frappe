# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/utils.py`

## Classes

### `InvalidWarehouseCompany`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PendingRepostingError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_stock_value_from_bin`
**Arguments:** `warehouse, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_value_on`
**Arguments:** `warehouses, posting_date, item_code, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_balance`
**Arguments:** `item_code, warehouse, posting_date, posting_time, with_valuation_rate, with_serial_no, inventory_dimensions_dict`
**Decorators:** ``

**Docstring:**
```
Returns stock balance quantity at given warehouse on given posting date or current date.

If `with_valuation_rate` is True, will return tuple (qty, rate)
```
### `get_serial_nos_data`
**Arguments:** `serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `get_latest_stock_qty`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_latest_stock_balance`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_bin`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_or_make_bin`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `_create_bin`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```
Create a bin and take care of concurrent inserts.
```
### `get_incoming_rate`
**Arguments:** `args, raise_error_if_no_rate`
**Decorators:** ``

**Docstring:**
```
Get Incoming Rate based on valuation method
```
### `get_batch_incoming_rate`
**Arguments:** `item_code, warehouse, batch_no, posting_date, posting_time, creation`
**Decorators:** ``

**Docstring:**
```

```
### `get_avg_purchase_rate`
**Arguments:** `serial_nos`
**Decorators:** ``

**Docstring:**
```
get average value of serial numbers
```
### `get_valuation_method`
**Arguments:** `item_code`
**Decorators:** ``

**Docstring:**
```
get valuation method from item or default
```
### `get_fifo_rate`
**Arguments:** `previous_stock_queue, qty`
**Decorators:** ``

**Docstring:**
```
get FIFO (average) Rate from Queue
```
### `get_lifo_rate`
**Arguments:** `previous_stock_queue, qty`
**Decorators:** ``

**Docstring:**
```
get LIFO (average) Rate from Queue
```
### `_get_fifo_lifo_rate`
**Arguments:** `previous_stock_queue, qty, method`
**Decorators:** ``

**Docstring:**
```

```
### `get_valid_serial_nos`
**Arguments:** `sr_nos, qty, item_code`
**Decorators:** ``

**Docstring:**
```
split serial nos, validate and return list of valid serial nos
```
### `validate_warehouse_company`
**Arguments:** `warehouse, company`
**Decorators:** ``

**Docstring:**
```

```
### `is_group_warehouse`
**Arguments:** `warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `validate_disabled_warehouse`
**Arguments:** `warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `update_included_uom_in_report`
**Arguments:** `columns, result, include_uom, conversion_factors`
**Decorators:** ``

**Docstring:**
```

```
### `add_additional_uom_columns`
**Arguments:** `columns, result, include_uom, conversion_factors`
**Decorators:** ``

**Docstring:**
```

```
### `get_incoming_outgoing_rate_for_cancel`
**Arguments:** `item_code, voucher_type, voucher_no, voucher_detail_no`
**Decorators:** ``

**Docstring:**
```

```
### `is_reposting_item_valuation_in_progress`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_pending_reposting`
**Arguments:** `posting_date, throw_error`
**Decorators:** ``

**Docstring:**
```
Check if there are pending reposting job till the specified posting date.
```
### `scan_barcode`
**Arguments:** `search_value`
**Decorators:** ``

**Docstring:**
```

```
### `_update_item_info`
**Arguments:** `scan_result`
**Decorators:** ``

**Docstring:**
```

```
### `get_combine_datetime`
**Arguments:** `posting_date, posting_time`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_stock_uom`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

