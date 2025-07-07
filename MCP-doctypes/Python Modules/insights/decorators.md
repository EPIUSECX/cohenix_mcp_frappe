# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/decorators.py`

## Classes

No classes found in this file.


## Functions

### `check_role`
**Arguments:** `role`
**Decorators:** ``

**Docstring:**
```

```
### `check_permission`
**Arguments:** `doctype, permission_type`
**Decorators:** ``

**Docstring:**
```

```
### `log_error`
**Arguments:** `raise_exc`
**Decorators:** ``

**Docstring:**
```

```
### `debounce`
**Arguments:** `wait`
**Decorators:** ``

**Docstring:**
```
Debounce decorator to be used on methods.

- This decorator will ensure that the method is called only after
`wait` seconds have passed since the last call.
- The method will be called if the arguments are different from the
last call.
- Returns the result of the last call if the method is called again

Parameters
----------
wait : int
    Number of seconds to wait before calling the method again.

Returns
-------
function
    The decorated function.
```
### `validate_type`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```

```
### `insights_whitelist`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

