# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset/asset.py`

## Classes

### `Asset`
**Inherits:** `AccountsController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `create_asset_depreciation_schedule` | `self` | `` |  |
| `set_depr_rate_and_value_after_depreciation` | `self` | `` |  |
| `show_schedule_creation_message` | `self, schedules` | `` |  |
| `on_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `set_purchase_doc_row_item` | `self` | `` |  |
| `get_linked_item` | `self, purchase_doc_type, purchase_doc` | `` |  |
| `validate_asset_and_reference` | `self` | `` |  |
| `validate_item` | `self` | `` |  |
| `validate_cost_center` | `self` | `` |  |
| `validate_in_use_date` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `validate_finance_books` | `self` | `` |  |
| `validate_category` | `self` | `` |  |
| `validate_precision` | `self` | `` |  |
| `validate_asset_values` | `self` | `` |  |
| `validate_gross_and_purchase_amount` | `self` | `` |  |
| `make_asset_movement` | `self` | `` |  |
| `set_depreciation_rate` | `self` | `` |  |
| `validate_asset_finance_books` | `self, row` | `` |  |
| `validate_opening_depreciation_values` | `self, row` | `` |  |
| `validate_depreciation_start_date` | `self, row` | `` |  |
| `set_total_booked_depreciations` | `self` | `` |  |
| `validate_expected_value_after_useful_life` | `self` | `` |  |
| `validate_cancellation` | `self` | `` |  |
| `cancel_movement_entries` | `self` | `` |  |
| `delete_depreciation_entries` | `self` | `` |  |
| `set_status` | `self, status` | `` | Get and update status |
| `get_status` | `self` | `` | Returns status based on whether it is draft, submitted, scrapped or depreciated |
| `get_value_after_depreciation` | `self, finance_book` | `` |  |
| `get_default_finance_book_idx` | `self` | `` |  |
| `get_manual_depreciation_entries` | `self` | `` |  |
| `validate_make_gl_entry` | `self` | `` |  |
| `get_purchase_document` | `self` | `` |  |
| `get_fixed_asset_account` | `self` | `` |  |
| `get_cwip_account` | `self, cwip_enabled` | `` |  |
| `make_gl_entries` | `self` | `` |  |
| `check_asset_capitalization_gl_entries` | `self` | `` |  |
| `get_depreciation_rate` | `self, args, on_validate` | `` |  |
| `get_double_declining_balance_rate` | `self, args, rate_field_precision` | `` |  |
| `get_written_down_value_rate` | `self, args, rate_field_precision, on_validate` | `` |  |





## Functions

### `has_gl_entries`
**Arguments:** `doctype, docname, target_account`
**Decorators:** ``

**Docstring:**
```

```
### `update_maintenance_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_post_gl_entry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_naming_series`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_sales_invoice`
**Arguments:** `asset, item_code, company, serial_no, posting_date`
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_maintenance`
**Arguments:** `asset, item_code, item_name, asset_category, company`
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_repair`
**Arguments:** `company, asset, asset_name`
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_capitalization`
**Arguments:** `company, asset, asset_name, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_value_adjustment`
**Arguments:** `asset, asset_category, company`
**Decorators:** ``

**Docstring:**
```

```
### `transfer_asset`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_details`
**Arguments:** `item_code, asset_category, gross_purchase_amount`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_account`
**Arguments:** `account_name, asset, asset_category, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_journal_entry`
**Arguments:** `asset_name`
**Decorators:** ``

**Docstring:**
```

```
### `make_asset_movement`
**Arguments:** `assets, purpose`
**Decorators:** ``

**Docstring:**
```

```
### `is_cwip_accounting_enabled`
**Arguments:** `asset_category`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_value_after_depreciation`
**Arguments:** `asset_name, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `has_active_capitalization`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `get_values_from_purchase_doc`
**Arguments:** `purchase_doc_name, item_code, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `split_asset`
**Arguments:** `asset_name, split_qty`
**Decorators:** ``

**Docstring:**
```
Split an asset into two based on the given quantity.
```
### `validate_split_quantity`
**Arguments:** `existing_asset, split_qty`
**Decorators:** ``

**Docstring:**
```

```
### `create_new_asset_from_split`
**Arguments:** `existing_asset, split_qty`
**Decorators:** ``

**Docstring:**
```
Create a new asset from the split quantity.
```
### `update_existing_asset_after_split`
**Arguments:** `existing_asset, remaining_qty, splitted_asset`
**Decorators:** ``

**Docstring:**
```
Update the existing asset with the remaining quantity.
```
### `process_asset_split`
**Arguments:** `existing_asset, split_qty, splitted_asset, is_new_asset`
**Decorators:** ``

**Docstring:**
```
Handle asset creation or update during the split.
```
### `set_split_asset_values`
**Arguments:** `asset_doc, scaling_factor, split_qty, existing_asset, is_new_asset`
**Decorators:** ``

**Docstring:**
```

```
### `log_asset_activity`
**Arguments:** `existing_asset, asset_doc, splitted_asset, is_new_asset`
**Decorators:** ``

**Docstring:**
```

```
### `update_finance_books`
**Arguments:** `asset_doc, existing_asset, new_asset, scaling_factor, is_new_asset`
**Decorators:** ``

**Docstring:**
```
Update finance books and depreciation schedules for the asset.
```
### `reschedule_depr_for_updated_asset`
**Arguments:** `existing_asset, new_asset, fb_row, scaling_factor, is_new_asset`
**Decorators:** ``

**Docstring:**
```
Reschedule depreciation for an asset after a split.
```
### `create_new_depr_schedule`
**Arguments:** `current_depr_schedule_doc, existing_asset, new_asset, is_new_asset, fb_row`
**Decorators:** ``

**Docstring:**
```
Create a new depreciation schedule based on the current one.
```
### `update_depreciation_terms`
**Arguments:** `new_depr_schedule_doc, scaling_factor`
**Decorators:** ``

**Docstring:**
```
Update depreciation terms with scaled amounts.
```
### `add_depr_schedule_notes`
**Arguments:** `new_depr_schedule_doc, existing_asset, new_asset, is_new_asset`
**Decorators:** ``

**Docstring:**
```

```
### `add_reference_in_jv_on_split`
**Arguments:** `entry_name, new_asset_name, old_asset_name, depreciation_amount`
**Decorators:** ``

**Docstring:**
```
Add a reference to a new asset in a journal entry after a split.
```
### `adjust_existing_accounts`
**Arguments:** `journal_entry, old_asset_name, depreciation_amount, entries_to_add`
**Decorators:** ``

**Docstring:**
```
Adjust existing accounts and prepare new entries for the new asset.
```
### `adjust_account_balance`
**Arguments:** `account, depreciation_amount`
**Decorators:** ``

**Docstring:**
```
Adjust the balance of an account based on the depreciation amount.
```
### `add_new_entries`
**Arguments:** `journal_entry, entries_to_add, new_asset_name, depreciation_amount`
**Decorators:** ``

**Docstring:**
```
Add new entries for the new asset to the journal entry.
```

