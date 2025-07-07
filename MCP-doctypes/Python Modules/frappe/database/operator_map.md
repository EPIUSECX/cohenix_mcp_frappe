# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/operator_map.py`

## Classes

No classes found in this file.


## Functions

### `like`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `LIKE`

Args:
        key (str): field
        value (str): criterion

Return:
        frappe.qb: `frappe.qb` object with `LIKE`
```
### `func_in`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `IN`.

Args:
        key (str): field
        value (Union[int, str]): criterion

Return:
        frappe.qb: `frappe.qb` object with `IN`
```
### `not_like`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `NOT LIKE`.

Args:
        key (str): field
        value (str): criterion

Return:
        frappe.qb: `frappe.qb` object with `NOT LIKE`
```
### `func_not_in`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `NOT IN`.

Args:
        key (str): field
        value (Union[int, str]): criterion

Return:
        frappe.qb: `frappe.qb` object with `NOT IN`
```
### `func_regex`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `REGEX`

Args:
        key (str): field
        value (str): criterion

Return:
        frappe.qb: `frappe.qb` object with `REGEX`
```
### `func_between`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `BETWEEN`.

Args:
        key (str): field
        value (Union[int, str]): criterion

Return:
        frappe.qb: `frappe.qb` object with `BETWEEN`
```
### `func_is`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper for IS
```
### `func_timespan`
**Arguments:** `key, value`
**Decorators:** ``

**Docstring:**
```
Wrapper method for `TIMESPAN`.

Args:
        key (str): field
        value (str): criterion

Return:
        frappe.qb: `frappe.qb` object with `TIMESPAN`
```

