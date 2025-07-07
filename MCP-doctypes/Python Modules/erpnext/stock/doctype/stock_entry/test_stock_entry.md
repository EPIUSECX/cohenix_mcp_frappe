# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/stock_entry/test_stock_entry.py`

## Classes

### `TestStockEntry`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `tearDown` | `self` | `` |  |
| `test_stock_entry_qty` | `self` | `` |  |
| `test_fifo` | `self` | `` |  |
| `test_auto_material_request` | `self` | `` |  |
| `test_barcode_item_stock_entry` | `self` | `` |  |
| `test_auto_material_request_for_variant` | `self` | `` |  |
| `test_auto_material_request_for_warehouse_group` | `self` | `` |  |
| `_test_auto_material_request` | `self, item_code, material_request_type, warehouse` | `` |  |
| `test_add_to_transit_entry` | `self` | `` |  |
| `test_material_receipt_gl_entry` | `self` | `` |  |
| `test_material_issue_gl_entry` | `self` | `` |  |
| `test_material_transfer_gl_entry` | `self` | `` |  |
| `test_repack_multiple_fg` | `self` | `` | Test `is_finished_item` for one item repacked into two items. |
| `test_repack_no_change_in_valuation` | `self` | `` |  |
| `test_repack_with_additional_costs` | `self` | `` |  |
| `check_stock_ledger_entries` | `self, voucher_type, voucher_no, expected_sle` | `` |  |
| `check_gl_entries` | `self, voucher_type, voucher_no, expected_gl_entries` | `` |  |
| `test_serial_no_not_reqd` | `self` | `` |  |
| `test_serial_no_reqd` | `self` | `` |  |
| `test_serial_no_qty_less` | `self` | `` |  |
| `test_serial_no_transfer_in` | `self` | `` |  |
| `test_serial_by_series` | `self` | `` |  |
| `test_serial_move` | `self` | `` |  |
| `test_serial_cancel` | `self` | `` |  |
| `test_serial_batch_item_stock_entry` | `self` | `` | Behaviour: 1) Submit Stock Entry (Receipt) with Serial & Batched Item
2) Cancel same Stock Entry
Expected Result: 1) Batch is created with Reference in Serial No
2) Batch is deleted and Serial No is Inactive |
| `test_warehouse_company_validation` | `self` | `` |  |
| `test_warehouse_user` | `self` | `` |  |
| `test_freeze_stocks` | `self` | `` |  |
| `test_work_order` | `self` | `` |  |
| `test_work_order_manufacture_with_material_consumption` | `self` | `` |  |
| `test_variant_work_order` | `self` | `` |  |
| `test_nagative_stock_for_batch` | `self` | `` |  |
| `test_quality_check_for_scrap_item` | `self` | `` |  |
| `test_quality_check` | `self` | `` |  |
| `test_customer_provided_parts_se` | `self` | `` |  |
| `test_zero_incoming_rate` | `self` | `` | Make sure incoming rate of 0 is allowed while consuming.

qty  | rate | valuation rate
 1   | 100  | 100
 1   | 0    | 50
-1   | 100  | 0
-1   | 0  <--- assert this |
| `test_gle_for_opening_stock_entry` | `self` | `` |  |
| `test_total_basic_amount_zero` | `self` | `` |  |
| `test_conversion_factor_change` | `self` | `` |  |
| `test_additional_cost_distribution_manufacture` | `self` | `` |  |
| `test_additional_cost_distribution_non_manufacture` | `self` | `` |  |
| `test_independent_manufacture_entry` | `self` | `` | Test FG items and incoming rate calculation in Maniufacture Entry without WO or BOM linked. |
| `test_future_negative_sle` | `self` | `` |  |
| `test_future_negative_sle_batch` | `self` | `` |  |
| `test_multi_batch_value_diff` | `self` | `` | Test value difference on stock entry in case of multi-batch.
| Stock entry | batch | qty | rate | value diff on SE             |
| ---         | ---   | --- | ---  | ---                          |
| receipt     | A     | 1   | 10   | 30                           |
| receipt     | B     | 1   | 20   |                              |
| issue       | A     | -1  | 10   | -30 (to assert after submit) |
| issue       | B     | -1  | 20   |                              | |
| `test_transfer_qty_validation` | `self` | `` |  |
| `test_mapped_stock_entry` | `self` | `` | Check if rate and stock details are populated in mapped SE given warehouse. |
| `test_stock_entry_item_details` | `self` | `` |  |
| `test_reposting_for_depedent_warehouse` | `self` | `` |  |
| `test_batch_expiry` | `self` | `` |  |
| `test_negative_stock_reco` | `self` | `` |  |
| `test_negative_batch` | `self` | `` |  |
| `test_auto_reorder_level` | `self` | `` |  |
| `test_auto_reorder_level_with_lead_time_days` | `self` | `` |  |
| `test_use_serial_and_batch_fields` | `self` | `` |  |
| `test_serial_batch_bundle_type_of_transaction` | `self` | `` |  |
| `test_stock_entry_for_same_posting_date_and_time` | `self` | `` |  |
| `test_stock_entry_amount` | `self` | `` |  |
| `test_use_batch_wise_valuation_for_moving_average_item` | `self` | `` |  |
| `test_periodic_accounting_entries` | `self` | `` |  |





## Functions

### `get_sle`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_serialized_item`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `get_qty_after_transaction`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_multiple_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `initialize_records_for_future_negative_sle_test`
**Arguments:** `item_code, batch_no, warehouses, opening_qty, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `create_stock_entries`
**Arguments:** `sequence_of_entries`
**Decorators:** ``

**Docstring:**
```

```

