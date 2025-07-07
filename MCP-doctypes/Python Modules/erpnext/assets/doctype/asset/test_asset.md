# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset/test_asset.py`

## Classes

### `AssetSetup`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |


### `TestAsset`
**Inherits:** `AssetSetup`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_asset_category_is_fetched` | `self` | `` | Tests if the Item's Asset Category value is assigned to the Asset, if the field is empty. |
| `test_gross_purchase_amount_is_mandatory` | `self` | `` |  |
| `test_pr_or_pi_mandatory_if_not_existing_asset` | `self` | `` | Tests if either PI or PR is present if CWIP is enabled and is_existing_asset=0. |
| `test_available_for_use_date_is_after_purchase_date` | `self` | `` |  |
| `test_item_exists` | `self` | `` |  |
| `test_validate_item` | `self` | `` |  |
| `test_purchase_asset` | `self` | `` |  |
| `test_purchase_of_grouped_asset` | `self` | `` |  |
| `test_is_fixed_asset_set` | `self` | `` |  |
| `test_scrap_asset` | `self` | `` |  |
| `test_gle_made_by_asset_sale` | `self` | `` |  |
| `test_gle_made_by_asset_sale_for_existing_asset` | `self` | `` |  |
| `test_asset_with_maintenance_required_status_after_sale` | `self` | `` |  |
| `test_asset_splitting` | `self` | `` |  |
| `test_expense_head` | `self` | `` |  |
| `test_cwip_accounting` | `self` | `` |  |
| `test_asset_cwip_toggling_cases` | `self` | `` |  |


### `TestDepreciationMethods`
**Inherits:** `AssetSetup`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_schedule_for_straight_line_method` | `self` | `` |  |
| `test_schedule_for_straight_line_method_with_daily_prorata_based` | `self` | `` |  |
| `test_schedule_for_straight_line_method_for_existing_asset` | `self` | `` |  |
| `test_schedule_for_double_declining_method` | `self` | `` |  |
| `test_schedule_for_double_declining_method_for_existing_asset` | `self` | `` |  |
| `test_schedule_for_prorated_straight_line_method` | `self` | `` |  |
| `test_depreciation_entry_for_wdv_without_pro_rata` | `self` | `` |  |
| `test_pro_rata_depreciation_entry_for_wdv` | `self` | `` |  |
| `test_monthly_depreciation_by_wdv_method` | `self` | `` |  |


### `TestDepreciationBasics`
**Inherits:** `AssetSetup`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_depreciation_without_pro_rata` | `self` | `` |  |
| `test_depreciation_with_pro_rata` | `self` | `` |  |
| `test_get_depreciation_amount` | `self` | `` | Tests if get_depreciation_amount() returns the right value. |
| `test_make_depr_schedule` | `self` | `` | Tests if make_depr_schedule() returns the right values. |
| `test_set_accumulated_depreciation` | `self` | `` | Tests if set_accumulated_depreciation() returns the right values. |
| `test_check_is_pro_rata` | `self` | `` | Tests if check_is_pro_rata() returns the right value(i.e. checks if has_pro_rata is accurate). |
| `test_expected_value_after_useful_life_greater_than_purchase_amount` | `self` | `` | Tests if an error is raised when expected_value_after_useful_life(110,000) > gross_purchase_amount(100,000). |
| `test_depreciation_start_date` | `self` | `` | Tests if an error is raised when neither depreciation_start_date nor available_for_use_date are specified. |
| `test_opening_accumulated_depreciation` | `self` | `` | Tests if an error is raised when opening_accumulated_depreciation > (gross_purchase_amount - expected_value_after_useful_life). |
| `test_opening_booked_depreciations` | `self` | `` | Tests if an error is raised when opening_number_of_booked_depreciations is not specified when opening_accumulated_depreciation is. |
| `test_number_of_depreciations` | `self` | `` | Tests if an error is raised when opening_number_of_booked_depreciations >= total_number_of_depreciations. |
| `test_depreciation_start_date_is_before_purchase_date` | `self` | `` |  |
| `test_depreciation_start_date_is_before_available_for_use_date` | `self` | `` |  |
| `test_finance_books_are_present_if_calculate_depreciation_is_enabled` | `self` | `` |  |
| `test_post_depreciation_entries` | `self` | `` | Tests if post_depreciation_entries() works as expected. |
| `test_depr_entry_posting_when_depr_expense_account_is_an_expense_account` | `self` | `` | Tests if the Depreciation Expense Account gets debited and the Accumulated Depreciation Account gets credited when the former's an Expense Account. |
| `test_depr_entry_posting_when_depr_expense_account_is_an_income_account` | `self` | `` |  |
| `test_clear_depr_schedule` | `self` | `` | Tests if clear_depr_schedule() works as expected. |
| `test_clear_depr_schedule_for_multiple_finance_books` | `self` | `` |  |
| `test_depreciation_schedules_are_set_up_for_multiple_finance_books` | `self` | `` |  |
| `test_depreciation_entry_cancellation` | `self` | `` |  |
| `test_asset_expected_value_after_useful_life` | `self` | `` |  |
| `test_gle_made_by_depreciation_entries` | `self` | `` |  |
| `test_expected_value_change` | `self` | `` | tests if changing `expected_value_after_useful_life`
affects `value_after_depreciation` |
| `test_asset_cost_center` | `self` | `` |  |
| `test_depreciation_on_final_day_of_the_month` | `self` | `` | Tests if final day of the month is picked each time, if the depreciation start date is the last day of the month. |
| `test_manual_depreciation_for_existing_asset` | `self` | `` |  |
| `test_manual_depreciation_for_depreciable_asset` | `self` | `` |  |
| `test_manual_depreciation_with_incorrect_jv_voucher_type` | `self` | `` |  |
| `test_multi_currency_asset_pr_creation` | `self` | `` |  |





## Functions

### `get_gl_entries`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_data`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_asset`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_asset_category`
**Arguments:** `enable_cwip`
**Decorators:** ``

**Docstring:**
```

```
### `create_fixed_asset_item`
**Arguments:** `item_code, auto_create_assets, is_grouped_asset`
**Decorators:** ``

**Docstring:**
```

```
### `set_depreciation_settings_in_company`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `enable_cwip_accounting`
**Arguments:** `asset_category, enable`
**Decorators:** ``

**Docstring:**
```

```

