# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/account/account.py`

## Classes

### `RootNotEditable`


**Docstring:**
```

```

**Methods:**
No methods found.

### `BalanceMismatchError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidAccountMergeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Account`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `onload` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_parent_child_account_type` | `self` | `` |  |
| `validate_parent` | `self` | `` | Fetch Parent Details and validate parent account |
| `set_root_and_report_type` | `self` | `` |  |
| `validate_receivable_payable_account_type` | `self` | `` |  |
| `validate_root_details` | `self` | `` |  |
| `validate_root_company_and_sync_account_to_children` | `self` | `` |  |
| `validate_group_or_ledger` | `self` | `` |  |
| `validate_frozen_accounts_modifier` | `self` | `` |  |
| `validate_balance_must_be_debit_or_credit` | `self` | `` |  |
| `validate_account_currency` | `self` | `` |  |
| `validate_account_number` | `self, account_number` | `` |  |
| `create_account_for_child_company` | `self, parent_acc_name_map, descendants, parent_acc_name` | `` |  |
| `convert_group_to_ledger` | `self` | `` |  |
| `convert_ledger_to_group` | `self` | `` |  |
| `check_gle_exists` | `self` | `` |  |
| `check_if_child_exists` | `self` | `` |  |
| `validate_mandatory` | `self` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

### `get_parent_account`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_account_currency`
**Arguments:** `account`
**Decorators:** ``

**Docstring:**
```
Helper function to get account currency
```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_account_autoname`
**Arguments:** `account_number, account_name, company`
**Decorators:** ``

**Docstring:**
```

```
### `update_account_number`
**Arguments:** `name, account_name, account_number, from_descendant`
**Decorators:** ``

**Docstring:**
```

```
### `merge_account`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```

```
### `get_root_company`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `sync_update_account_number_in_child`
**Arguments:** `descendants, old_acc_name, account_name, account_number, old_acc_number`
**Decorators:** ``

**Docstring:**
```

```
### `_ensure_idle_system`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

