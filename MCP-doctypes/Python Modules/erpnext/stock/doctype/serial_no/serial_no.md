# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/serial_no/serial_no.py`

## Classes

### `SerialNoCannotCreateDirectError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoCannotCannotChangeError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNoWarehouseError`
**Inherits:** `ValidationError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SerialNo`
**Inherits:** `StockController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_warehouse` | `self` | `` |  |
| `set_maintenance_status` | `self` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

### `get_available_serial_nos`
**Arguments:** `serial_no_series, qty`
**Decorators:** ``

**Docstring:**
```

```
### `get_new_serial_number`
**Arguments:** `series`
**Decorators:** ``

**Docstring:**
```

```
### `get_items_html`
**Arguments:** `serial_nos, item_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos`
**Arguments:** `serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_from_sle_list`
**Arguments:** `bundles`
**Decorators:** ``

**Docstring:**
```

```
### `clean_serial_no_string`
**Arguments:** `serial_no`
**Decorators:** ``

**Docstring:**
```

```
### `update_maintenance_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `auto_fetch_serial_number`
**Arguments:** `qty, item_code, warehouse, posting_date, batch_nos, for_doctype, exclude_sr_nos`
**Decorators:** ``

**Docstring:**
```

```
### `get_pos_reserved_serial_nos`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_serial_numbers`
**Arguments:** `filters, qty, do_not_include`
**Decorators:** ``

**Docstring:**
```

```
### `get_serial_nos_for_outward`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```

