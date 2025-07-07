# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/serial_batch_bundle.py`

## Classes

### `SerialBatchBundle`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `process_serial_and_batch_bundle` | `self` | `` |  |
| `set_item_details` | `self` | `` |  |
| `process_serial_no` | `self` | `` |  |
| `is_material_transfer` | `self` | `` |  |
| `make_serial_batch_no_bundle_for_material_transfer` | `self` | `` |  |
| `make_serial_batch_no_bundle` | `self` | `` |  |
| `validate_actual_qty` | `self, sn_doc` | `` |  |
| `validate_item` | `self` | `` |  |
| `set_serial_and_batch_bundle` | `self, sn_doc` | `` |  |
| `child_doctype` | `self` | `property` |  |
| `is_rejected_entry` | `self` | `` |  |
| `is_packed_entry` | `self` | `` |  |
| `process_batch_no` | `self` | `` |  |
| `validate_item_and_warehouse` | `self` | `` |  |
| `delink_serial_and_batch_bundle` | `self` | `` |  |
| `post_process` | `self` | `` |  |
| `cancel_serial_and_batch_bundle` | `self` | `` |  |
| `is_pos_or_asset_repair_transaction` | `self` | `` |  |
| `submit_serial_and_batch_bundle` | `self` | `` |  |
| `set_warehouse_and_status_in_serial_nos` | `self` | `` |  |
| `update_serial_no_status_warehouse` | `self, sle, serial_nos` | `` |  |
| `update_serial_no_status_for_stock_reco` | `self, serial_nos` | `` |  |
| `set_batch_no_in_serial_nos` | `self` | `` |  |


### `SerialNoValuation`
**Inherits:** `DeprecatedSerialNoValuation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `calculate_stock_value_change` | `self` | `` |  |
| `get_incoming_rate_from_bundle` | `self, serial_no` | `` |  |
| `get_serial_nos` | `self` | `` |  |
| `calculate_valuation_rate` | `self` | `` |  |
| `is_rejected_entry` | `self` | `` |  |
| `get_incoming_rate` | `self` | `` |  |
| `get_incoming_rate_of_serial_no` | `self, serial_no` | `` |  |


### `BatchNoValuation`
**Inherits:** `DeprecatedBatchNoValuation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `calculate_avg_rate` | `self` | `` |  |
| `get_batch_no_ledgers` | `self` | `` |  |
| `prepare_batches` | `self` | `` |  |
| `get_batch_nos` | `self` | `` |  |
| `set_stock_value_difference` | `self` | `` |  |
| `calculate_valuation_rate` | `self` | `` |  |
| `get_incoming_rate` | `self` | `` |  |
| `get_actual_qty` | `self` | `` |  |


### `SerialBatchCreation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, args` | `` |  |
| `set` | `self, args` | `` |  |
| `get` | `self, key` | `` |  |
| `set_item_details` | `self` | `` |  |
| `set_other_details` | `self` | `` |  |
| `duplicate_package` | `self` | `` |  |
| `remove_returned_serial_nos` | `self, package` | `` |  |
| `make_serial_and_batch_bundle` | `self` | `` |  |
| `add_serial_nos_for_batch_item` | `self` | `` |  |
| `update_serial_and_batch_entries` | `self` | `` |  |
| `validate_qty` | `self, doc` | `` |  |
| `set_auto_serial_batch_entries_for_outward` | `self` | `` |  |
| `set_auto_serial_batch_entries_for_inward` | `self` | `` |  |
| `make_serial_no_if_not_exists` | `self` | `` |  |
| `make_serial_nos` | `self, serial_nos` | `` |  |
| `set_serial_batch_entries` | `self, doc` | `` |  |
| `create_batch` | `self` | `` |  |
| `get_auto_created_serial_nos` | `self` | `` |  |





## Functions

### `get_serial_nos`
**Arguments:** `serial_and_batch_bundle, serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `get_batches_from_bundle`
**Arguments:** `serial_and_batch_bundle, batches`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_from_bundle`
**Arguments:** `serial_and_batch_bundle, serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_or_batch_nos`
**Arguments:** `bundle`
**Decorators:** ``

**Docstring:**
```

```
### `is_rejected`
**Arguments:** `voucher_type, voucher_detail_no, warehouse`
**Decorators:** ``

**Docstring:**
```

```
### `get_batch_nos`
**Arguments:** `serial_and_batch_bundle`
**Decorators:** ``

**Docstring:**
```

```
### `get_empty_batches_based_work_order`
**Arguments:** `work_order, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_batches_from_work_order`
**Arguments:** `work_order, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_batches_from_stock_entries`
**Arguments:** `work_order, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `set_batch_details_from_package`
**Arguments:** `ids, batches`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_or_batch_items`
**Arguments:** `items`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_batch`
**Arguments:** `serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `update_batch_qty`
**Arguments:** `voucher_type, voucher_no, via_landed_cost_voucher`
**Decorators:** ``

**Docstring:**
```

```
### `throw_negative_batch_validation`
**Arguments:** `batch_no, warehouse, qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_distinct_batches`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```

