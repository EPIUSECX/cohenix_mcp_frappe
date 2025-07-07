# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/batch/test_batch.py`

## Classes

### `TestBatch`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_item_has_batch_enabled` | `self` | `` |  |
| `make_batch_item` | `cls, item_name` | `classmethod` |  |
| `test_purchase_receipt` | `self, batch_qty` | `` | Test automated batch creation from Purchase Receipt |
| `test_batch_stock_levels` | `self, batch_qty` | `` | Test automated batch creation from Purchase Receipt |
| `test_stock_entry_incoming` | `self` | `` | Test batch creation via Stock Entry (Work Order) |
| `test_delivery_note` | `self` | `` | Test automatic batch selection for outgoing items |
| `test_batch_negative_stock_error` | `self` | `` | Test automatic batch selection for outgoing items |
| `test_stock_entry_outgoing` | `self` | `` | Test automatic batch selection for outgoing stock entry |
| `test_batch_split` | `self` | `` | Test batch splitting |
| `test_get_batch_qty` | `self` | `` | Test getting batch quantities by batch_numbers, item_code or warehouse |
| `test_total_batch_qty` | `self` | `` |  |
| `make_new_batch_and_entry` | `cls, item_name, batch_name, warehouse` | `classmethod` | Make a new stock entry for given target warehouse and batch name of item |
| `test_batch_name_with_naming_series` | `self` | `` |  |
| `make_new_batch` | `self, item_name, batch_id, do_not_insert` | `` |  |
| `test_batch_wise_item_price` | `self` | `` |  |
| `test_basic_batch_wise_valuation` | `self, batch_qty` | `` |  |
| `test_update_batch_properties` | `self` | `` |  |
| `test_autocreation_of_batches` | `self` | `` | Test if auto created Serial No excludes existing serial numbers |





## Functions

### `create_batch`
**Arguments:** `item_code, rate, create_item_price_for_batch`
**Decorators:** ``

**Docstring:**
```

```
### `create_price_list_for_batch`
**Arguments:** `item_code, batch, rate`
**Decorators:** ``

**Docstring:**
```

```
### `make_new_batch`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

