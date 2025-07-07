# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/general_ledger.py`

## Classes

No classes found in this file.


## Functions

### `make_gl_entries`
**Arguments:** `gl_map, cancel, adv_adj, merge_entries, update_outstanding, from_repost`
**Decorators:** ``

**Docstring:**
```

```
### `make_acc_dimensions_offsetting_entry`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `get_accounting_dimensions_for_offsetting_entry`
**Arguments:** `gl_map, company`
**Decorators:** ``

**Docstring:**
```

```
### `validate_disabled_accounts`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `validate_accounting_period`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `process_gl_map`
**Arguments:** `gl_map, merge_entries, precision, from_repost`
**Decorators:** ``

**Docstring:**
```

```
### `distribute_gl_based_on_cost_center_allocation`
**Arguments:** `gl_map, precision, from_repost`
**Decorators:** ``

**Docstring:**
```

```
### `get_cost_center_allocation_data`
**Arguments:** `company, posting_date, cost_center`
**Decorators:** `request_cache`

**Docstring:**
```

```
### `merge_similar_entries`
**Arguments:** `gl_map, precision`
**Decorators:** ``

**Docstring:**
```

```
### `get_merge_properties`
**Arguments:** `dimensions`
**Decorators:** ``

**Docstring:**
```

```
### `get_merge_key`
**Arguments:** `entry, merge_properties`
**Decorators:** ``

**Docstring:**
```

```
### `check_if_in_list`
**Arguments:** `gle, gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `toggle_debit_credit_if_negative`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `save_entries`
**Arguments:** `gl_map, adv_adj, update_outstanding, from_repost`
**Decorators:** ``

**Docstring:**
```

```
### `make_entry`
**Arguments:** `args, adv_adj, update_outstanding, from_repost`
**Decorators:** ``

**Docstring:**
```

```
### `validate_cwip_accounts`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```
Validate that CWIP account are not used in Journal Entry
```
### `process_debit_credit_difference`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `get_debit_credit_difference`
**Arguments:** `gl_map, precision`
**Decorators:** ``

**Docstring:**
```

```
### `get_debit_credit_allowance`
**Arguments:** `voucher_type, precision`
**Decorators:** ``

**Docstring:**
```

```
### `raise_debit_credit_not_equal_error`
**Arguments:** `debit_credit_diff, voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `has_opening_entries`
**Arguments:** `gl_map`
**Decorators:** ``

**Docstring:**
```

```
### `make_round_off_gle`
**Arguments:** `gl_map, debit_credit_diff, trx_cur_debit_credit_diff, precision`
**Decorators:** ``

**Docstring:**
```

```
### `update_accounting_dimensions`
**Arguments:** `round_off_gle`
**Decorators:** ``

**Docstring:**
```

```
### `get_round_off_account_and_cost_center`
**Arguments:** `company, voucher_type, voucher_no, use_company_default`
**Decorators:** ``

**Docstring:**
```

```
### `make_reverse_gl_entries`
**Arguments:** `gl_entries, voucher_type, voucher_no, adv_adj, update_outstanding, partial_cancel`
**Decorators:** ``

**Docstring:**
```
Get original gl entries of the voucher
and make reverse gl entries by swapping debit and credit
```
### `check_freezing_date`
**Arguments:** `posting_date, adv_adj`
**Decorators:** ``

**Docstring:**
```
Nobody can do GL Entries where posting date is before freezing date
except authorized person

Administrator has all the roles so this check will be bypassed if any role is allowed to post
Hence stop admin to bypass if accounts are freezed
```
### `validate_against_pcv`
**Arguments:** `is_opening, posting_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `set_as_cancel`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```
Set is_cancelled=1 in all original gl entries for the voucher
```
### `validate_allowed_dimensions`
**Arguments:** `gl_entry, dimension_filter_map`
**Decorators:** ``

**Docstring:**
```

```
### `is_immutable_ledger_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

