# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/batch/batch.py`

## Classes

### `UnableToSelectBatchError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Batch`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` | Generate random ID for batch if not specified |
| `onload` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `item_has_batch_enabled` | `self` | `` |  |
| `set_batchwise_valuation` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `set_expiry_date` | `self` | `` |  |
| `get_name_from_naming_series` | `self` | `` | Get a name generated for a Batch from the Batch's naming series.
:return: The string that was generated. |





## Functions

### `get_name_from_hash`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get a name for a Batch by generating a unique hash.
:return: The hash that was generated.
```
### `batch_uses_naming_series`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Verify if the Batch is to be named using a naming series
:return: bool
```
### `_get_batch_prefix`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get the naming series prefix set in Stock Settings.

It does not do any sanity checks so make sure to use it after checking if the Batch
is set to use naming series.
:return: The naming series.
```
### `_make_naming_series_key`
**Arguments:** `prefix`
**Decorators:** ``

**Docstring:**
```
Make naming series key for a Batch.

Naming series key is in the format [prefix].[#####]
:param prefix: Naming series prefix gotten from Stock Settings
:return: The derived key. If no prefix is given, an empty string is returned
```
### `get_batch_naming_series`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get naming series key for a Batch.

Naming series key is in the format [prefix].[#####]
:return: The naming series or empty string if not available
```
### `get_batch_qty`
**Arguments:** `batch_no, warehouse, item_code, posting_date, posting_time, ignore_voucher_nos, for_stock_levels, consider_negative_batches, do_not_check_future_batches`
**Decorators:** ``

**Docstring:**
```
Returns batch actual qty if warehouse is passed,
        or returns dict of qty by warehouse if warehouse is None

The user must pass either batch_no or batch_no + warehouse or item_code + warehouse

:param batch_no: Optional - give qty for this batch no
:param warehouse: Optional - give qty for this warehouse
:param item_code: Optional - give qty for this item
:param for_stock_levels: True consider expired batches
```
### `get_batches_by_oldest`
**Arguments:** `item_code, warehouse`
**Decorators:** ``

**Docstring:**
```
Returns the oldest batch and qty for the given item_code and warehouse
```
### `split_batch`
**Arguments:** `batch_no, item_code, warehouse, qty, new_batch_id`
**Decorators:** ``

**Docstring:**
```
Split the batch into a new batch
```
### `make_batch_bundle`
**Arguments:** `item_code, warehouse, batches, company, type_of_transaction, qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_batches`
**Arguments:** `item_code, warehouse, qty, throw, serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `validate_serial_no_with_batch`
**Arguments:** `serial_nos, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `make_batch`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_reserved_batch_qty`
**Arguments:** `filters`
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
### `get_batch_no`
**Arguments:** `bundle_id`
**Decorators:** ``

**Docstring:**
```

```

