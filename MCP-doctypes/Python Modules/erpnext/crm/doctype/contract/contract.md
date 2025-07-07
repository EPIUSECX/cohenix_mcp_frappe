# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/contract/contract.py`

## Classes

### `Contract`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `set_missing_values` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `before_update_after_submit` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `update_contract_status` | `self` | `` |  |
| `update_fulfilment_status` | `self` | `` |  |
| `get_fulfilment_progress` | `self` | `` |  |





## Functions

### `get_status`
**Arguments:** `start_date, end_date`
**Decorators:** ``

**Docstring:**
```
Get a Contract's status based on the start, current and end dates

Args:
        start_date (str): The start date of the contract
        end_date (str): The end date of the contract

Returns:
        str: 'Active' if within range, otherwise 'Inactive'
```
### `update_status_for_contracts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Run the daily hook to update the statuses for all signed
and submitted Contracts
```

