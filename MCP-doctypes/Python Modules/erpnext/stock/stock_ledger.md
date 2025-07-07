# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/stock_ledger.py`

## Classes

### `NegativeStockError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoExistsInFutureTransaction`


**Docstring:**
```

```

**Methods:**
No methods found.

### `update_entries_after`


**Docstring:**
```
update valution rate and qty after transaction
from the current time-bucket onwards

:param args: args as dict

        args = {
                "item_code": "ABC",
                "warehouse": "XYZ",
                "posting_date": "2012-12-12",
                "posting_time": "12:00"
        }
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, args, allow_zero_rate, allow_negative_stock, via_landed_cost_voucher, verbose` | `` |  |
| `get_reserved_stock` | `self` | `` |  |
| `set_precision` | `self` | `` |  |
| `initialize_previous_data` | `self, args` | `` | Get previous sl entries for current item for each related warehouse
and assigns into self.data dict

:Data Structure:

self.data = {
        warehouse1: {
                'previus_sle': {},
                'qty_after_transaction': 10,
                'valuation_rate': 100,
                'stock_value': 1000,
                'prev_stock_value': 1000,
                'stock_queue': '[[10, 100]]',
                'stock_value_difference': 1000
        }
} |
| `build` | `self` | `` |  |
| `has_stock_reco_with_serial_batch` | `self, sle` | `` |  |
| `process_sle_against_current_timestamp` | `self` | `` |  |
| `get_sle_against_current_voucher` | `self` | `` |  |
| `get_future_entries_to_fix` | `self` | `` |  |
| `get_dependent_entries_to_fix` | `self, entries_to_fix, sle` | `` |  |
| `update_distinct_item_warehouses` | `self, dependant_sle` | `` |  |
| `is_dependent_voucher_reposted` | `self, dependant_sle` | `` |  |
| `get_dependent_voucher_detail_nos` | `self, key` | `` |  |
| `validate_previous_sle_qty` | `self, sle` | `` |  |
| `process_sle` | `self, sle` | `` |  |
| `get_serialized_values` | `self, sle` | `` |  |
| `reset_actual_qty_for_stock_reco` | `self, sle` | `` |  |
| `update_serial_no_status` | `self, sle` | `` |  |
| `calculate_valuation_for_serial_batch_bundle` | `self, sle` | `` |  |
| `get_outgoing_rate_for_batched_item` | `self, sle` | `` |  |
| `validate_negative_stock` | `self, sle` | `` | validate negative stock for entries current datetime onwards
will not consider cancelled entries |
| `get_dynamic_incoming_outgoing_rate` | `self, sle` | `` |  |
| `has_landed_cost_based_on_pi` | `self, sle` | `` |  |
| `get_incoming_outgoing_rate_from_transaction` | `self, sle` | `` |  |
| `update_outgoing_rate_on_transaction` | `self, sle` | `` | Update outgoing rate in Stock Entry, Delivery Note, Sales Invoice and Sales Return
In case of Stock Entry, also calculate FG Item rate and total incoming/outgoing amount |
| `update_rate_on_stock_entry` | `self, sle, outgoing_rate` | `` |  |
| `is_manufacture_entry_with_sabb` | `self, sle` | `` |  |
| `recalculate_amounts_in_stock_entry` | `self, voucher_no, voucher_detail_no` | `` |  |
| `update_rate_on_delivery_and_sales_return` | `self, sle, outgoing_rate` | `` |  |
| `update_rate_on_purchase_receipt` | `self, sle, outgoing_rate` | `` |  |
| `update_rate_on_subcontracting_receipt` | `self, sle, outgoing_rate` | `` |  |
| `update_rate_on_stock_reconciliation` | `self, sle` | `` |  |
| `get_incoming_value_for_serial_nos` | `self, sle, serial_nos` | `` |  |
| `get_moving_average_values` | `self, sle` | `` |  |
| `update_queue_values` | `self, sle` | `` |  |
| `is_return_purchase_entry` | `self, sle` | `` |  |
| `update_batched_values` | `self, sle` | `` |  |
| `check_if_allow_zero_valuation_rate` | `self, voucher_type, voucher_detail_no` | `` |  |
| `get_fallback_rate` | `self, sle` | `` | When exact incoming rate isn't available use any of other "average" rates as fallback.
This should only get used for negative stock. |
| `get_sle_before_datetime` | `self, args` | `` | get previous stock ledger entry before current time-bucket |
| `get_sle_after_datetime` | `self, args` | `` | get Stock Ledger Entries after a particular datetime, for reposting |
| `raise_exceptions` | `self` | `` |  |
| `update_bin_data` | `self, sle` | `` |  |
| `update_bin` | `self` | `` |  |





## Functions

### `make_sl_entries`
**Arguments:** `sl_entries, allow_negative_stock, via_landed_cost_voucher`
**Decorators:** ``

**Docstring:**
```
Create SL entries from SL entry dicts

args:
        - allow_negative_stock: disable negative stock valiations if true
        - via_landed_cost_voucher: landed cost voucher cancels and reposts
        entries of purchase document. This flag is used to identify if
        cancellation and repost is happening via landed cost voucher, in
        such cases certain validations need to be ignored (like negative
                        stock)
```
### `repost_current_voucher`
**Arguments:** `args, allow_negative_stock, via_landed_cost_voucher`
**Decorators:** ``

**Docstring:**
```

```
### `get_args_for_future_sle`
**Arguments:** `row`
**Decorators:** ``

**Docstring:**
```

```
### `validate_serial_no`
**Arguments:** `sle`
**Decorators:** ``

**Docstring:**
```

```
### `validate_cancellation`
**Arguments:** `kargs`
**Decorators:** ``

**Docstring:**
```

```
### `set_as_cancel`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `make_entry`
**Arguments:** `args, allow_negative_stock, via_landed_cost_voucher`
**Decorators:** ``

**Docstring:**
```

```
### `repost_future_sle`
**Arguments:** `args, voucher_type, voucher_no, allow_negative_stock, via_landed_cost_voucher, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_reposting_data`
**Arguments:** `file_path`
**Decorators:** ``

**Docstring:**
```

```
### `validate_item_warehouse`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `update_args_in_repost_item_valuation`
**Arguments:** `doc, index, args, distinct_item_warehouses, affected_transactions`
**Decorators:** ``

**Docstring:**
```

```
### `get_reposting_file_name`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `create_json_gz_file`
**Arguments:** `data, doc, file_name`
**Decorators:** ``

**Docstring:**
```

```
### `create_file`
**Arguments:** `doc, compressed_content`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_to_be_repost`
**Arguments:** `voucher_type, voucher_no, doc, reposting_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_distinct_item_warehouse`
**Arguments:** `args, doc, reposting_data`
**Decorators:** ``

**Docstring:**
```

```
### `parse_distinct_items_and_warehouses`
**Arguments:** `distinct_items_and_warehouses`
**Decorators:** ``

**Docstring:**
```

```
### `get_affected_transactions`
**Arguments:** `doc, reposting_data`
**Decorators:** ``

**Docstring:**
```

```
### `get_current_index`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_previous_sle_of_current_voucher`
**Arguments:** `args, operator, exclude_current_voucher`
**Decorators:** ``

**Docstring:**
```
get stock ledger entries filtered by specific posting datetime conditions
```
### `get_previous_sle`
**Arguments:** `args, for_update, extra_cond`
**Decorators:** ``

**Docstring:**
```
get the last sle on or before the current time-bucket,
to get actual qty before transaction, this function
is called from various transaction like stock entry, reco etc

args = {
        "item_code": "ABC",
        "warehouse": "XYZ",
        "posting_date": "2012-12-12",
        "posting_time": "12:00",
        "sle": "name of reference Stock Ledger Entry"
}
```
### `get_stock_ledger_entries`
**Arguments:** `previous_sle, operator, order, limit, for_update, debug, check_serial_no, extra_cond`
**Decorators:** ``

**Docstring:**
```
get stock ledger entries filtered by specific posting datetime conditions
```
### `get_sle_by_voucher_detail_no`
**Arguments:** `voucher_detail_no, excluded_sle`
**Decorators:** ``

**Docstring:**
```

```
### `get_batch_incoming_rate`
**Arguments:** `item_code, warehouse, batch_no, posting_date, posting_time, creation`
**Decorators:** ``

**Docstring:**
```

```
### `get_valuation_rate`
**Arguments:** `item_code, warehouse, voucher_type, voucher_no, allow_zero_rate, currency, company, raise_error_if_no_rate, batch_no, serial_and_batch_bundle`
**Decorators:** ``

**Docstring:**
```

```
### `update_qty_in_future_sle`
**Arguments:** `args, allow_negative_stock`
**Decorators:** ``

**Docstring:**
```
Recalculate Qty after Transaction in future SLEs based on current SLE.
```
### `get_stock_reco_qty_shift`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_next_stock_reco`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```
Returns next nearest stock reconciliaton's details.
```
### `get_datetime_limit_condition`
**Arguments:** `detail`
**Decorators:** ``

**Docstring:**
```

```
### `validate_negative_qty_in_future_sle`
**Arguments:** `args, allow_negative_stock`
**Decorators:** ``

**Docstring:**
```

```
### `is_negative_with_precision`
**Arguments:** `neg_sle, is_batch`
**Decorators:** ``

**Docstring:**
```
Returns whether system precision rounded qty is insufficient.
E.g: -0.0003 in precision 3 (0.000) is sufficient for the user.
```
### `get_future_sle_with_negative_qty`
**Arguments:** `sle_args`
**Decorators:** ``

**Docstring:**
```

```
### `get_future_sle_with_negative_batch_qty`
**Arguments:** `sle_args`
**Decorators:** ``

**Docstring:**
```

```
### `validate_reserved_stock`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `validate_reserved_serial_nos`
**Arguments:** `item_code, warehouse, serial_nos`
**Decorators:** ``

**Docstring:**
```

```
### `validate_reserved_batch_nos`
**Arguments:** `item_code, warehouse, batch_nos`
**Decorators:** ``

**Docstring:**
```

```
### `is_negative_stock_allowed`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_incoming_rate_for_inter_company_transfer`
**Arguments:** `sle`
**Decorators:** ``

**Docstring:**
```
For inter company transfer, incoming rate is the average of the outgoing rate
```
### `is_internal_transfer`
**Arguments:** `sle`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_value_difference`
**Arguments:** `item_code, warehouse, posting_date, posting_time, voucher_no`
**Decorators:** ``

**Docstring:**
```

```

