# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pos_closing_entry/pos_closing_entry.py`

## Classes

### `POSClosingEntry`
**Inherits:** `StatusUpdater`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `set_posting_date_and_time` | `self` | `` |  |
| `fetch_invoice_type` | `self` | `` |  |
| `validate_pos_opening_entry` | `self` | `` |  |
| `validate_invoice_mode` | `self` | `` |  |
| `validate_duplicate_pos_invoices` | `self` | `` |  |
| `validate_pos_invoices` | `self` | `` |  |
| `validate_duplicate_sales_invoices` | `self` | `` |  |
| `validate_sales_invoices` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `before_cancel` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `retry` | `self` | `` |  |
| `update_opening_entry` | `self, for_cancel` | `` |  |
| `update_sales_invoices_closing_entry` | `self, cancel` | `` |  |
| `check_pce_is_cancellable` | `self` | `` |  |





## Functions

### `get_cashiers`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_invoices`
**Arguments:** `start, end, pos_profile, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_payments`
**Arguments:** `invoices`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes`
**Arguments:** `invoices`
**Decorators:** ``

**Docstring:**
```

```
### `make_closing_entry_from_opening`
**Arguments:** `opening_entry`
**Decorators:** ``

**Docstring:**
```

```
### `build_invoice_query`
**Arguments:** `invoice_doctype, user, pos_profile, start, end`
**Decorators:** ``

**Docstring:**
```

```

