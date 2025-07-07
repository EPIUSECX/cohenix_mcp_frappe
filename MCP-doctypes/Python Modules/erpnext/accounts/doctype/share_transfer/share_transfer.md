# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/share_transfer/share_transfer.py`

## Classes

### `ShareDontExists`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `ShareTransfer`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `basic_validations` | `self` | `` |  |
| `share_exists` | `self, shareholder` | `` |  |
| `folio_no_validation` | `self` | `` |  |
| `autoname_folio` | `self, shareholder, is_company` | `` |  |
| `remove_shares` | `self, shareholder` | `` |  |
| `return_share_balance_entry` | `self, from_no, to_no, rate` | `` |  |
| `get_shareholder_doc` | `self, shareholder` | `` |  |
| `get_company_shareholder` | `self` | `` |  |





## Functions

### `make_jv_entry`
**Arguments:** `company, account, amount, payment_account, credit_applicant_type, credit_applicant, debit_applicant_type, debit_applicant`
**Decorators:** ``

**Docstring:**
```

```

