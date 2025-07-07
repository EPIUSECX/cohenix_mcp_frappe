# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/gl_entry/gl_entry.py`

## Classes

### `GLEntry`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` | Temporarily name doc for fast insertion
name will be changed using autoname options (in a scheduled job) |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `check_mandatory` | `self` | `` |  |
| `pl_must_have_cost_center` | `self` | `` | Validate that profit and loss type account GL entries have a cost center. |
| `validate_dimensions_for_pl_and_bs` | `self` | `` |  |
| `check_pl_account` | `self` | `` |  |
| `validate_account_details` | `self, adv_adj` | `` | Account must be ledger, active and not freezed |
| `validate_cost_center` | `self` | `` |  |
| `validate_party` | `self` | `` |  |
| `validate_currency` | `self` | `` |  |
| `validate_and_set_fiscal_year` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |





## Functions

### `validate_balance_type`
**Arguments:** `account, adv_adj`
**Decorators:** ``

**Docstring:**
```

```
### `update_outstanding_amt`
**Arguments:** `account, party_type, party, against_voucher_type, against_voucher, on_cancel`
**Decorators:** ``

**Docstring:**
```

```
### `validate_frozen_account`
**Arguments:** `account, adv_adj`
**Decorators:** ``

**Docstring:**
```

```
### `update_against_account`
**Arguments:** `voucher_type, voucher_no`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `rename_gle_sle_docs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `rename_temporarily_named_docs`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Rename temporarily named docs using autoname options
```

