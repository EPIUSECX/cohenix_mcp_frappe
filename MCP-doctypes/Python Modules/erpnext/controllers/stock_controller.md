# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/controllers/stock_controller.py`

## Classes

### `QualityInspectionRequiredError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QualityInspectionRejectedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `QualityInspectionNotSubmittedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BatchExpiredError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `StockController`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `reset_conversion_factor` | `self` | `` |  |
| `check_zero_rate` | `self` | `` |  |
| `validate_items_exist` | `self` | `` |  |
| `validate_duplicate_serial_and_batch_bundle` | `self, table_name` | `` |  |
| `make_gl_entries` | `self, gl_entries, from_repost, via_landed_cost_voucher` | `` |  |
| `validate_serialized_batch` | `self` | `` |  |
| `clean_serial_nos` | `self` | `` |  |
| `make_bundle_using_old_serial_batch_fields` | `self, table_name, via_landed_cost_voucher` | `` |  |
| `get_parent_details_for_packed_items` | `self` | `` |  |
| `make_bundle_for_sales_purchase_return` | `self, table_name` | `` |  |
| `make_bundle_for_rejected_qty` | `self, table_name` | `` |  |
| `make_bundle_for_non_rejected_qty` | `self, table_name` | `` |  |
| `get_reference_ids` | `self, table_name, qty_field, bundle_field` | `` |  |
| `is_serial_batch_item` | `self, item_code` | `` |  |
| `update_bundle_details` | `self, bundle_details, table_name, row, is_rejected, parent_details` | `` |  |
| `create_serial_batch_bundle` | `self, bundle_details, row` | `` |  |
| `validate_serial_nos_and_batches_with_bundle` | `self, row` | `` |  |
| `set_use_serial_batch_fields` | `self` | `` |  |
| `get_gl_entries` | `self, warehouse_account, default_expense_account, default_cost_center` | `` |  |
| `get_debit_field_precision` | `self` | `` |  |
| `get_voucher_details` | `self, default_expense_account, default_cost_center, sle_map` | `` |  |
| `get_items_and_warehouses` | `self` | `` | Get list of items and warehouses affected by a transaction |
| `get_stock_ledger_details` | `self` | `` |  |
| `check_expense_account` | `self, item` | `` |  |
| `delete_auto_created_batches` | `self` | `` |  |
| `set_serial_and_batch_bundle` | `self, table_name, ignore_validate` | `` |  |
| `make_package_for_transfer` | `self, serial_and_batch_bundle, warehouse, type_of_transaction, do_not_submit, qty` | `` |  |
| `get_sl_entries` | `self, d, args` | `` |  |
| `set_landed_cost_voucher_amount` | `self` | `` |  |
| `has_landed_cost_amount` | `self` | `` |  |
| `get_item_account_wise_lcv_entries` | `self` | `` |  |
| `update_inventory_dimensions` | `self, row, sl_dict` | `` |  |
| `make_sl_entries` | `self, sl_entries, allow_negative_stock, via_landed_cost_voucher` | `` |  |
| `make_gl_entries_on_cancel` | `self` | `` |  |
| `get_serialized_items` | `self` | `` |  |
| `validate_warehouse` | `self` | `` |  |
| `update_billing_percentage` | `self, update_modified` | `` |  |
| `validate_inspection` | `self` | `` | Checks if quality inspection is set/ is valid for Items that require inspection. |
| `validate_qi_presence` | `self, row` | `` | Check if QI is present on row level. Warn on save and stop on submit if missing. |
| `validate_qi_submission` | `self, row` | `` | Check if QI is submitted on row level, during submission |
| `validate_qi_rejection` | `self, row` | `` | Check if QI is rejected on row level, during submission |
| `update_blanket_order` | `self` | `` |  |
| `validate_customer_provided_item` | `self` | `` |  |
| `set_rate_of_stock_uom` | `self` | `` |  |
| `validate_internal_transfer` | `self` | `` |  |
| `validate_internal_transfer_warehouse` | `self` | `` |  |
| `validate_in_transit_warehouses` | `self` | `` |  |
| `validate_multi_currency` | `self` | `` |  |
| `validate_packed_items` | `self` | `` |  |
| `validate_internal_transfer_qty` | `self` | `` |  |
| `get_item_wise_inter_transfer_qty` | `self` | `` |  |
| `get_item_wise_inter_received_qty` | `self` | `` |  |
| `validate_putaway_capacity` | `self` | `` |  |
| `prepare_over_receipt_message` | `self, rule, values` | `` |  |
| `repost_future_sle_and_gle` | `self, force, via_landed_cost_voucher` | `` |  |
| `add_gl_entry` | `self, gl_entries, account, cost_center, debit, credit, remarks, against_account, debit_in_account_currency, credit_in_account_currency, account_currency, project, voucher_detail_no, item, posting_date` | `` |  |





## Functions

### `show_accounting_ledger_preview`
**Arguments:** `company, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `show_stock_ledger_preview`
**Arguments:** `company, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_accounting_ledger_preview`
**Arguments:** `doc, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_stock_ledger_preview`
**Arguments:** `doc, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_sl_entries_for_preview`
**Arguments:** `doctype, docname, fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_gl_entries_for_preview`
**Arguments:** `doctype, docname, fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_columns`
**Arguments:** `raw_columns, fields`
**Decorators:** ``

**Docstring:**
```

```
### `get_data`
**Arguments:** `raw_columns, raw_data`
**Decorators:** ``

**Docstring:**
```

```
### `repost_required_for_queue`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
check if stock document contains repeated item-warehouse with queue based valuation.

if queue exists for repeated items then SLEs need to reprocessed in background again.
```
### `check_item_quality_inspection`
**Arguments:** `doctype, items`
**Decorators:** ``

**Docstring:**
```

```
### `make_quality_inspections`
**Arguments:** `doctype, docname, items, inspection_type`
**Decorators:** ``

**Docstring:**
```

```
### `is_reposting_pending`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `future_sle_exists`
**Arguments:** `args, sl_entries, allow_force_reposting`
**Decorators:** ``

**Docstring:**
```

```
### `validate_future_sle_not_exists`
**Arguments:** `args, key, sl_entries`
**Decorators:** ``

**Docstring:**
```

```
### `get_cached_data`
**Arguments:** `args, key`
**Decorators:** ``

**Docstring:**
```

```
### `get_sle_entries_against_voucher`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_conditions_to_validate_future_sle`
**Arguments:** `sl_entries`
**Decorators:** ``

**Docstring:**
```

```
### `create_repost_item_valuation_entry`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `create_item_wise_repost_entries`
**Arguments:** `voucher_type, voucher_no, allow_zero_rate, via_landed_cost_voucher`
**Decorators:** ``

**Docstring:**
```
Using a voucher create repost item valuation records for all item-warehouse pairs.
```
### `make_bundle_for_material_transfer`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

