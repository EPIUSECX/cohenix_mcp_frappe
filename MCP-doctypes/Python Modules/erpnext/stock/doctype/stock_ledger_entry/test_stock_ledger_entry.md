# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_ledger_entry/test_stock_ledger_entry.py`

## Classes

### `TestStockLedgerEntry`
**Inherits:** `IntegrationTestCase, StockTestMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_item_cost_reposting` | `self` | `` |  |
| `test_purchase_return_valuation_reposting` | `self` | `` |  |
| `test_sales_return_valuation_reposting` | `self` | `` |  |
| `test_reposting_of_sales_return_for_packed_item` | `self` | `` |  |
| `test_back_dated_entry_not_allowed` | `self` | `` |  |
| `test_batchwise_item_valuation_fifo` | `self` | `` |  |
| `test_batchwise_item_valuation_moving_average` | `self` | `` |  |
| `test_batchwise_item_valuation_stock_reco` | `self` | `` |  |
| `test_batch_wise_valuation_across_warehouse` | `self` | `` |  |
| `test_intermediate_average_batch_wise_valuation` | `self` | `` | A batch has moving average up until posting time,
check if same is respected when backdated entry is inserted in middle |
| `test_legacy_item_valuation_stock_entry` | `self` | `` |  |
| `test_fifo_dependent_consumption` | `self` | `` |  |
| `test_fifo_multi_item_repack_consumption` | `self` | `` |  |
| `test_negative_fifo_valuation` | `self` | `` | When stock goes negative discard FIFO queue.
Only pervailing valuation rate should be used for making transactions in such cases. |
| `test_dependent_gl_entry_reposting` | `self` | `` |  |
| `test_tie_breaking` | `self` | `` |  |
| `test_timestamp_clash` | `self` | `` |  |
| `test_previous_sle_with_clashed_timestamp` | `self` | `` |  |
| `test_backdated_sle_with_same_timestamp` | `self` | `` |  |
| `test_transfer_invariants` | `self` | `` | Extact stock value should be transferred. |
| `test_negative_qty_with_precision` | `self` | `` | Test if system precision is respected while validating negative qty. |
| `test_future_negative_qty_with_precision` | `self` | `` | Ledger:
| Voucher | Qty         | Balance
-------------------
| Reco    | 559.8327| 559.8327
| SE      | -470.84     | [Backdated] (new bal: 88.9927)
| SE      | 11.007      | 570.8397 (new bal: 99.9997)
| DN      | -100        | 470.8397 (new bal: -0.0003)

Check if future negative qty is asserted as per precision 3.
-0.0003 should be considered as 0.000 |


### `TestDeferredNaming`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `get_gle_sles` | `se` | `staticmethod` |  |
| `test_deferred_naming` | `self` | `` |  |
| `test_hash_naming` | `self` | `` |  |





## Functions

### `create_repack_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_product_bundle_item`
**Arguments:** `new_item_code, packed_items`
**Decorators:** ``

**Docstring:**
```

```
### `create_items`
**Arguments:** `items, uoms`
**Decorators:** ``

**Docstring:**
```

```
### `setup_item_valuation_test`
**Arguments:** `valuation_method, suffix, use_batchwise_valuation, batches_list`
**Decorators:** ``

**Docstring:**
```

```
### `create_purchase_receipt_entries_for_batchwise_item_valuation_test`
**Arguments:** `pr_entry_list`
**Decorators:** ``

**Docstring:**
```

```
### `create_delivery_note_entries_for_batchwise_item_valuation_test`
**Arguments:** `dn_entry_list`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_sle_details_for_doc_list`
**Arguments:** `doc_list, columns, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_value_from_q`
**Arguments:** `q`
**Decorators:** ``

**Docstring:**
```

```
### `create_stock_entry_entries_for_batchwise_item_valuation_test`
**Arguments:** `se_entry_list, purpose`
**Decorators:** ``

**Docstring:**
```

```
### `get_unique_suffix`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

