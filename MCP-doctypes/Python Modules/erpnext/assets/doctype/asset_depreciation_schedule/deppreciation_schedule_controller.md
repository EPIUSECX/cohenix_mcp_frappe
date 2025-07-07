# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/assets/doctype/asset_depreciation_schedule/deppreciation_schedule_controller.py`

## Classes

### `DepreciationScheduleController`
**Inherits:** `StraightLineMethod, WDVMethod`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `create_depreciation_schedule` | `self, fb_row, disposal_date` | `` |  |
| `clear` | `self` | `` |  |
| `create` | `self` | `` |  |
| `initialize_variables` | `self` | `` |  |
| `get_final_number_of_depreciations` | `self` | `` |  |
| `set_final_number_of_depreciations_considering_increase_in_asset_life` | `self` | `` |  |
| `is_wdv_or_dd_non_yearly_pro_rata` | `self` | `` |  |
| `_check_is_pro_rata` | `self` | `` |  |
| `_get_modified_available_for_use_date_for_existing_assets` | `self` | `` | if Asset has opening booked depreciations = 3,
frequency of depreciation = 3,
available for use date = 17-07-2023,
depreciation start date = 30-06-2024
then from date should be 01-04-2024 |
| `get_total_days` | `self, date` | `` |  |
| `_get_pro_rata_amt` | `self, from_date, to_date, original_schedule_date` | `` |  |
| `get_number_of_pending_months` | `self` | `` |  |
| `get_last_booked_depreciation_date` | `self` | `` |  |
| `get_booked_depr_for_months_count` | `self, last_depr_date` | `` |  |
| `get_total_pending_days_or_years` | `self` | `` |  |
| `has_fiscal_year_changed` | `self, row_idx` | `` |  |
| `get_prev_depreciation_amount` | `self, row_idx` | `` |  |
| `get_next_schedule_date` | `self, row_idx` | `` |  |
| `set_depreciation_amount_for_disposal` | `self, row_idx` | `` |  |
| `set_depreciation_amount_for_first_row` | `self, row_idx` | `` | For the first row, if available for use date is mid of the month, then pro rata amount is needed |
| `set_depreciation_amount_for_last_row` | `self, row_idx` | `` |  |
| `adjust_depr_amount_for_salvage_value` | `self, row_idx` | `` | Adjust depreciation amount in the last period based on the expected value after useful life |
| `validate_depreciation_amount_for_low_value_assets` | `self` | `` | If gross purchase amount is too low, then depreciation amount
can come zero sometimes based on the frequency and number of depreciations. |
| `add_depr_schedule_row` | `self, row_idx` | `` |  |
| `set_accumulated_depreciation` | `self` | `` |  |
| `get_depreciation_amount` | `self, row_idx` | `` |  |
| `_get_total_days` | `self, depreciation_start_date, row_idx` | `` |  |
| `get_total_days_in_current_depr_year` | `self` | `` |  |
| `get_fiscal_year` | `self, date` | `` |  |





## Functions

No top-level functions found in this file.
