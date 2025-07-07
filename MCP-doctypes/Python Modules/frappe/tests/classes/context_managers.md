# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/classes/context_managers.py`

## Classes

No classes found in this file.


## Functions

### `freeze_time`
**Arguments:** `time_to_freeze, is_utc`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: freeze time with freezegun.
```
### `set_user`
**Arguments:** `user`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: set the user.
```
### `patch_hooks`
**Arguments:** `overridden_hooks`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: patch a hook.
```
### `change_settings`
**Arguments:** `commit`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: change settings in a settings doctype.
```
### `switch_site`
**Arguments:** `site`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: drop current connection and switch to a different site.
```
### `enable_safe_exec`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: enable safe exec (server scripts).
```
### `debug_on`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: enter an interactive debugger on specified exceptions, default: (AssertionError,).
```
### `timeout_context`
**Arguments:** `seconds, error_message`
**Decorators:** `contextmanager`

**Docstring:**
```
Temporarily: timeout an operation.
```
### `timeout`
**Arguments:** `seconds, error_message`
**Decorators:** ``

**Docstring:**
```
Timeout decorator to ensure a test doesn't run for too long.
```
### `trace_fields`
**Arguments:** `doc_class, field_name, forbidden_values, custom_validation`
**Decorators:** `contextmanager`

**Docstring:**
```
A context manager for temporarily tracing fields in a DocType.

Can be used in two ways:
1. Tracing a single field:
   trace_fields(DocType, "field_name", forbidden_values=[...], custom_validation=...)
2. Tracing multiple fields:
   trace_fields(DocType, field1={"forbidden_values": [...], "custom_validation": ...}, ...)

Args:
    doc_class (Document): The DocType class to modify.
    field_name (str, optional): The name of the field to trace (for single field tracing).
    forbidden_values (list, optional): A list of forbidden values for the field (for single field tracing).
    custom_validation (callable, optional): A custom validation function (for single field tracing).
    **field_configs: Keyword arguments for multiple field tracing, where each key is a field name and
                     the value is a dict containing 'forbidden_values' and/or 'custom_validation'.

Yields:
    Document class
```

