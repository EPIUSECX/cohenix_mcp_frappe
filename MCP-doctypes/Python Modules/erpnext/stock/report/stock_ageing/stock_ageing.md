# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/report/stock_ageing/stock_ageing.py`

## Classes

### `FIFOSlots`


**Docstring:**
```
Returns FIFO computed slots of inwarded stock as per date.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, filters, sle` | `` |  |
| `generate` | `self` | `` | Returns dict of the foll.g structure:
Key = Item A / (Item A, Warehouse A)
Key: {
        'details' -> Dict: ** item details **,
        'fifo_queue' -> List: ** list of lists containing entries/slots for existing stock,
                consumed/updated and maintained via FIFO. **
} |
| `__init_key_stores` | `self, row` | `` | Initialise keys and FIFO Queue. |
| `__compute_incoming_stock` | `self, row, fifo_queue, transfer_key, serial_nos` | `` | Update FIFO Queue on inward stock. |
| `__compute_outgoing_stock` | `self, row, fifo_queue, transfer_key, serial_nos` | `` | Update FIFO Queue on outward stock. |
| `__adjust_incoming_transfer_qty` | `self, transfer_data, fifo_queue, row` | `` | Add previously removed stock back to FIFO Queue. |
| `__update_balances` | `self, row, key` | `` |  |
| `__aggregate_details_by_item` | `self, wh_wise_data` | `` | Aggregate Item-Wh wise data into single Item entry. |
| `__get_stock_ledger_entries` | `self` | `` |  |
| `__get_bundle_wise_serial_nos` | `self` | `` |  |
| `__get_item_query` | `self` | `` |  |
| `__get_warehouse_conditions` | `self, sle, sle_query` | `` |  |





## Functions

### `execute`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `format_report_data`
**Arguments:** `filters, item_details, to_date`
**Decorators:** ``

**Docstring:**
```
Returns ordered, formatted data with ranges.
```
### `check_and_replace_valuations_if_moving_average`
**Arguments:** `range_values, item_valuation_method, valuation_rate`
**Decorators:** ``

**Docstring:**
```

```
### `get_average_age`
**Arguments:** `fifo_queue, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_range_age`
**Arguments:** `filters, fifo_queue, to_date, item_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_chart_data`
**Arguments:** `data, filters`
**Decorators:** ``

**Docstring:**
```

```
### `setup_ageing_columns`
**Arguments:** `filters, range_columns`
**Decorators:** ``

**Docstring:**
```

```
### `add_column`
**Arguments:** `range_columns, label, fieldname, fieldtype, width`
**Decorators:** ``

**Docstring:**
```

```

