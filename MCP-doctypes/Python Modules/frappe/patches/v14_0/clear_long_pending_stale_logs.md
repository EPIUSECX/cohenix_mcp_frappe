# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/patches/v14_0/clear_long_pending_stale_logs.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Due to large size of log tables on old sites some table cleanups never finished during daily log clean up. This patch discards such data by using "big delete" code.

ref: https://github.com/frappe/frappe/issues/16971
```
### `is_log_cleanup_stuck`
**Arguments:** `doctype, retention`
**Decorators:** ``

**Docstring:**
```
Check if doctype has data significantly older than configured cleanup period
```
### `get_current_setting`
**Arguments:** `fieldname`
**Decorators:** ``

**Docstring:**
```

```

