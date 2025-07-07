# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/bank_transaction/auto_match_party.py`

## Classes

### `AutoMatchParty`


**Docstring:**
```
Matches by Account/IBAN and then by Party Name/Description sequentially.
Returns when a result is obtained.

Result (if present) is of the form: (Party Type, Party,)
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get` | `self, key` | `` |  |
| `match` | `self` | `` |  |


### `AutoMatchbyAccountIBAN`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get` | `self, key` | `` |  |
| `match` | `self` | `` |  |
| `match_account_in_party` | `self` | `` | Returns (Party Type, Party) if a matching account is found in Bank Account or Employee:
1. Get party from a matching (iban/account no) Bank Account
2. If not found, get party from Employee with matching bank account details (iban/account no) |
| `get_or_filters` | `self, party` | `` | Return OR filters for Bank Account and IBAN |


### `AutoMatchbyPartyNameDescription`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `get` | `self, key` | `` |  |
| `match` | `self` | `` |  |
| `match_party_name_desc_in_party` | `self` | `` | Fuzzy search party name and/or description against parties in the system |
| `fuzzy_search_and_return_result` | `self, party, names, field` | `` |  |
| `process_fuzzy_result` | `self, result` | `` | If there are multiple valid close matches return None as result may be faulty.
Return the result only if one accurate match stands out.

Returns: Result, Skip (whether or not to discontinue matching) |





## Functions

### `get_parties_in_order`
**Arguments:** `deposit`
**Decorators:** ``

**Docstring:**
```

```

