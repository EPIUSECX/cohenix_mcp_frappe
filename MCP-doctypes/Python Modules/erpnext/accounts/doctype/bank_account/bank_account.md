# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_account/bank_account.py`

## Classes

### `BankAccount`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` | Load address and contacts in `__onload` |
| `autoname` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_account` | `self` | `` |  |
| `validate_company` | `self` | `` |  |
| `validate_iban` | `self` | `` | Algorithm: https://en.wikipedia.org/wiki/International_Bank_Account_Number#Validating_the_IBAN |
| `update_default_bank_account` | `self` | `` |  |





## Functions

### `make_bank_account`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_party_bank_account`
**Arguments:** `party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_company_bank_account`
**Arguments:** `company, party_type, party`
**Decorators:** ``

**Docstring:**
```

```
### `get_bank_account_details`
**Arguments:** `bank_account`
**Decorators:** ``

**Docstring:**
```

```

