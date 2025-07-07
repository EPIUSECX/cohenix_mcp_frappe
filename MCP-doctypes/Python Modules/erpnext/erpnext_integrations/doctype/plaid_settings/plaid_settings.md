# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/erpnext_integrations/doctype/plaid_settings/plaid_settings.py`

## Classes

### `PlaidSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_link_token` | `` | `staticmethod` |  |





## Functions

### `get_plaid_configuration`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_institution`
**Arguments:** `token, response`
**Decorators:** ``

**Docstring:**
```

```
### `add_bank_accounts`
**Arguments:** `response, bank, company`
**Decorators:** ``

**Docstring:**
```

```
### `add_account_type`
**Arguments:** `account_type`
**Decorators:** ``

**Docstring:**
```

```
### `add_account_subtype`
**Arguments:** `account_subtype`
**Decorators:** ``

**Docstring:**
```

```
### `sync_transactions`
**Arguments:** `bank, bank_account`
**Decorators:** ``

**Docstring:**
```
Sync transactions based on the last integration date as the start date, after sync is completed
add the transaction date of the oldest transaction as the last integration date.
```
### `get_transactions`
**Arguments:** `bank, bank_account, start_date, end_date`
**Decorators:** ``

**Docstring:**
```

```
### `new_bank_transaction`
**Arguments:** `transaction`
**Decorators:** ``

**Docstring:**
```

```
### `automatic_synchronization`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_synchronization`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_link_token_for_update`
**Arguments:** `access_token`
**Decorators:** ``

**Docstring:**
```

```
### `get_company`
**Arguments:** `bank_account_name`
**Decorators:** ``

**Docstring:**
```

```
### `update_bank_account_ids`
**Arguments:** `response`
**Decorators:** ``

**Docstring:**
```

```

