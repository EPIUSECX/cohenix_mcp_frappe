# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/exchange_rate_revaluation/exchange_rate_revaluation.py`

## Classes

### `ExchangeRateRevaluation`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_rounding_loss_allowance` | `self` | `` |  |
| `set_total_gain_loss` | `self` | `` |  |
| `validate_mandatory` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `remove_accounts_without_gain_loss` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `check_journal_entry_condition` | `self` | `` |  |
| `fetch_and_calculate_accounts_data` | `self` | `` |  |
| `get_accounts_data` | `self` | `` |  |
| `get_account_balance_from_gle` | `company, posting_date, account, party_type, party, rounding_loss_allowance` | `staticmethod` |  |
| `calculate_new_account_balance` | `company, posting_date, account_details` | `staticmethod` |  |
| `throw_invalid_response_message` | `self, account_details` | `` |  |
| `get_for_unrealized_gain_loss_account` | `self` | `` |  |
| `make_jv_entries` | `self` | `` |  |
| `make_jv_for_zero_balance` | `self` | `` |  |
| `make_jv_for_revaluation` | `self` | `` |  |





## Functions

### `calculate_exchange_rate_using_last_gle`
**Arguments:** `company, account, party_type, party`
**Decorators:** ``

**Docstring:**
```
Use last GL entry to calculate exchange rate
```
### `get_account_details`
**Arguments:** `company, posting_date, account, party_type, party, rounding_loss_allowance`
**Decorators:** ``

**Docstring:**
```

```

