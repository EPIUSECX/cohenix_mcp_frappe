# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset/depreciation.py`

## Classes

No classes found in this file.


## Functions

### `post_depreciation_entries`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `book_depreciation_entries`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `get_depreciable_assets_data`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `make_depreciation_entry_on_disposal`
**Arguments:** `asset_doc, disposal_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_acc_frozen_upto`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_credit_debit_accounts_for_asset`
**Arguments:** `asset_category, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_depreciation_cost_center_and_series`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `get_depr_cost_center_and_series`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_depreciation_entry`
**Arguments:** `depr_schedule_name, date, sch_start_idx, sch_end_idx, accounting_dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `_make_journal_entry_for_depreciation`
**Arguments:** `depr_schedule_doc, asset, date, depr_schedule, sch_start_idx, sch_end_idx, depr_cost_center, depr_series, credit_account, debit_account, accounting_dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `setup_journal_entry_metadata`
**Arguments:** `je, depr_schedule_doc, depr_series, depr_schedule, asset`
**Decorators:** ``

**Docstring:**
```

```
### `get_credit_and_debit_entry`
**Arguments:** `credit_account, depr_schedule, asset, depr_cost_center, debit_account, dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `get_credit_and_debit_accounts`
**Arguments:** `accumulated_depreciation_account, depreciation_expense_account`
**Decorators:** ``

**Docstring:**
```

```
### `set_depr_entry_posting_status_for_failed_assets`
**Arguments:** `failed_asset_names`
**Decorators:** ``

**Docstring:**
```

```
### `notify_depr_entry_posting_error`
**Arguments:** `failed_asset_names, error_log_names`
**Decorators:** ``

**Docstring:**
```

```
### `get_comma_separated_links`
**Arguments:** `names, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_message_for_depr_entry_posting_error`
**Arguments:** `asset_links, error_log_links`
**Decorators:** ``

**Docstring:**
```

```
### `scrap_asset`
**Arguments:** `asset_name, scrap_date`
**Decorators:** ``

**Docstring:**
```

```
### `validate_asset_for_scrap`
**Arguments:** `asset, scrap_date`
**Decorators:** ``

**Docstring:**
```

```
### `validate_scrap_date`
**Arguments:** `asset, scrap_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_last_depreciation_date`
**Arguments:** `asset_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_note_for_scrap`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `create_journal_entry_for_scrap`
**Arguments:** `asset, scrap_date`
**Decorators:** ``

**Docstring:**
```

```
### `restore_asset`
**Arguments:** `asset_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_note_for_restore`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_journal_entry_for_scrap`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `depreciate_asset`
**Arguments:** `asset_doc, date, notes`
**Decorators:** ``

**Docstring:**
```

```
### `cancel_depreciation_entries`
**Arguments:** `asset_doc, date`
**Decorators:** ``

**Docstring:**
```

```
### `reset_depreciation_schedule`
**Arguments:** `asset_doc, notes`
**Decorators:** ``

**Docstring:**
```

```
### `reverse_depreciation_entry_made_on_disposal`
**Arguments:** `asset`
**Decorators:** ``

**Docstring:**
```

```
### `disposal_was_made_on_original_schedule_date`
**Arguments:** `schedule_idx, row, disposal_date`
**Decorators:** ``

**Docstring:**
```
If asset is scrapped or sold on original schedule date,
then the depreciation entry should not be reversed.
```
### `disposal_happens_in_the_future`
**Arguments:** `disposal_date`
**Decorators:** ``

**Docstring:**
```

```
### `create_reverse_depreciation_entry`
**Arguments:** `asset_name, journal_entry`
**Decorators:** ``

**Docstring:**
```

```
### `update_value_after_depreciation_on_asset_restore`
**Arguments:** `schedule, row, journal_entry`
**Decorators:** ``

**Docstring:**
```

```
### `get_depreciation_amount_in_je`
**Arguments:** `journal_entry`
**Decorators:** ``

**Docstring:**
```

```
### `get_gl_entries_on_asset_regain`
**Arguments:** `asset, selling_amount, finance_book, voucher_type, voucher_no, date`
**Decorators:** ``

**Docstring:**
```

```
### `get_gl_entries_on_asset_disposal`
**Arguments:** `asset, selling_amount, finance_book, voucher_type, voucher_no, date`
**Decorators:** ``

**Docstring:**
```

```
### `get_asset_details`
**Arguments:** `asset, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `get_depreciation_accounts`
**Arguments:** `asset_category, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_profit_gl_entries`
**Arguments:** `asset, profit_amount, gl_entries, disposal_account, depreciation_cost_center, date`
**Decorators:** ``

**Docstring:**
```

```
### `get_disposal_account_and_cost_center`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_value_after_depreciation_on_disposal_date`
**Arguments:** `asset, disposal_date, finance_book`
**Decorators:** ``

**Docstring:**
```

```
### `validate_disposal_date`
**Arguments:** `reference_date, disposal_date, label`
**Decorators:** ``

**Docstring:**
```

```

