# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_reconciliation/test_stock_reconciliation.py`

## Classes

### `TestStockReconciliation`
**Inherits:** `IntegrationTestCase, StockTestMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDown` | `self` | `` |  |
| `test_reco_for_fifo` | `self` | `` |  |
| `test_reco_for_moving_average` | `self` | `` |  |
| `_test_reco_sle_gle` | `self, valuation_method` | `` |  |
| `test_get_items` | `self` | `` |  |
| `test_stock_reco_for_serialized_item` | `self` | `` |  |
| `test_stock_reco_for_batch_item` | `self` | `` |  |
| `test_stock_reco_for_serial_and_batch_item` | `self` | `` |  |
| `test_stock_reco_for_serial_and_batch_item_with_future_dependent_entry` | `self` | `` | Behaviour: 1) Create Stock Reconciliation, which will be the origin document
of a new batch having a serial no
2) Create a Stock Entry that adds a serial no to the same batch following this
Stock Reconciliation
3) Cancel Stock Entry
Expected Result: 3) Serial No only in the Stock Entry is Inactive and Batch qty decreases |
| `test_customer_provided_items` | `self` | `` |  |
| `test_backdated_stock_reco_qty_reposting` | `self` | `` | Test if a backdated stock reco recalculates future qty until next reco.
-------------------------------------------
Var             | Doc   |       Qty     | Balance
-------------------------------------------
PR5     | PR    |   10  |  10   (posting date: today-4) [backdated]
SR5             | Reco  |       0       |       8       (posting date: today-4) [backdated]
PR1             | PR    |       10      |       18      (posting date: today-3)
PR2             | PR    |       1       |       19      (posting date: today-2)
SR4             | Reco  |       0       |       6       (posting date: today-1) [backdated]
PR3             | PR    |       1       |       7       (posting date: today) # can't post future PR |
| `test_backdated_stock_reco_future_negative_stock` | `self` | `` | Test if a backdated stock reco causes future negative stock and is blocked.
-------------------------------------------
Var             | Doc   |       Qty     | Balance
-------------------------------------------
PR1             | PR    |       10      |       10              (posting date: today-2)
SR3             | Reco  |       0       |       1               (posting date: today-1) [backdated & blocked]
DN2             | DN    |       -2      |       8(-1)   (posting date: today) |
| `test_backdated_stock_reco_cancellation_future_negative_stock` | `self` | `` | Test if a backdated stock reco cancellation that causes future negative stock is blocked.
-------------------------------------------
Var | Doc  | Qty | Balance
-------------------------------------------
SR  | Reco | 100 | 100     (posting date: today-1) (shouldn't be cancelled after DN)
DN  | DN   | 100 |   0     (posting date: today) |
| `test_intermediate_sr_bin_update` | `self` | `` | Bin should show correct qty even for backdated entries.

-------------------------------------------
| creation | Var | Doc  | Qty | balance qty
-------------------------------------------
|  1       | SR  | Reco | 10  | 10     (posting date: today+10)
|  3       | SR2 | Reco | 11  | 11     (posting date: today+11)
|  2       | DN  | DN   | 5   | 6 <-- assert in BIN  (posting date: today+12) |
| `test_valid_batch` | `self` | `` |  |
| `test_serial_no_cancellation` | `self` | `` |  |
| `test_serial_no_creation_and_inactivation` | `self` | `` |  |
| `test_serial_no_batch_no_item` | `self` | `` |  |
| `test_backdated_stock_reco_entry` | `self` | `` |  |
| `test_update_stock_reconciliation_while_reposting` | `self` | `` |  |
| `test_make_stock_zero_for_serial_batch_item` | `self` | `` |  |
| `test_backdated_purchase_receipt_with_stock_reco` | `self` | `` |  |
| `test_balance_qty_for_batch_with_backdated_stock_reco_and_future_entries` | `self` | `` |  |
| `test_stock_reco_and_backdated_purchase_receipt` | `self` | `` |  |
| `test_not_reconcile_all_batch` | `self` | `` |  |
| `test_not_reconcile_all_serial_nos` | `self` | `` |  |
| `test_stock_reco_with_legacy_batch` | `self` | `` |  |
| `test_skip_reposting_for_entries_after_stock_reco` | `self` | `` |  |
| `test_stock_reco_for_negative_batch` | `self` | `` |  |
| `test_stock_reco_batch_item_current_valuation` | `self` | `` |  |
| `test_stock_reco_recalculate_qty_for_backdated_entry` | `self` | `` |  |





## Functions

### `create_batch_item_with_batch`
**Arguments:** `item_name, batch_id`
**Decorators:** ``

**Docstring:**
```

```
### `insert_existing_sle`
**Arguments:** `warehouse, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `create_batch_or_serial_no_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_stock_reconciliation`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `set_valuation_method`
**Arguments:** `item_code, valuation_method`
**Decorators:** ``

**Docstring:**
```

```

