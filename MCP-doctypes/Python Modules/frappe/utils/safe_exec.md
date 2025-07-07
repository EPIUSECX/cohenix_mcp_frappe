# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/safe_exec.py`

## Classes

### `ServerScriptNotEnabled`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NamespaceDict`


**Docstring:**
```
Raise AttributeError if function not found in namespace
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__getattr__` | `self, key` | `` |  |


### `FrappeTransformer`
**Inherits:** `RestrictingNodeTransformer`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `check_name` | `self, node, name` | `` |  |


### `FrappePrintCollector`
**Inherits:** `PrintCollector`


**Docstring:**
```
Collect written text, and return it when called.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `_call_print` | `self` | `` |  |





## Functions

### `is_safe_exec_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `safe_exec`
**Arguments:** `script, _globals, _locals`
**Decorators:** ``

**Docstring:**
```

```
### `safe_eval`
**Arguments:** `code, eval_globals, eval_locals`
**Decorators:** ``

**Docstring:**
```

```
### `_validate_safe_eval_syntax`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```

```
### `safe_exec_flags`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `get_safe_globals`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_keys_for_autocomplete`
**Arguments:** `key, value, prefix, offset, meta, depth, max_depth`
**Decorators:** ``

**Docstring:**
```

```
### `is_job_queued`
**Arguments:** `job_name, queue`
**Decorators:** ``

**Docstring:**
```
:param job_name: used to identify a queued job, usually dotted path to function
:param queue: should be either long, default or short
```
### `safe_enqueue`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```
Enqueue function to be executed using a background worker
Accepts frappe.enqueue params like job_name, queue, timeout, etc.
in addition to params to be passed to function

:param function: whitelisted function or API Method set in Server Script
```
### `call_whitelisted_function`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```
Executes a whitelisted function or Server Script of type API
```
### `run_script`
**Arguments:** `script`
**Decorators:** ``

**Docstring:**
```
run another server script
```
### `call_with_form_dict`
**Arguments:** `function, kwargs`
**Decorators:** ``

**Docstring:**
```

```
### `patched_qb`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `_flatten`
**Arguments:** `module`
**Decorators:** `lru_cache`

**Docstring:**
```

```
### `get_python_builtins`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_hooks`
**Arguments:** `hook, default, app_name`
**Decorators:** ``

**Docstring:**
```
Get hooks via `app/hooks.py`

:param hook: Name of the hook. Will gather all hooks for this name and return as a list.
:param default: Default if no hook found.
:param app_name: Filter by app.
```
### `read_sql`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```
a wrapper for frappe.db.sql to allow reads
```
### `check_safe_sql_query`
**Arguments:** `query, throw`
**Decorators:** ``

**Docstring:**
```
Check if SQL query is safe for running in restricted context.

Safe queries:
        1. Read only 'select' or 'explain' queries
        2. CTE on mariadb where writes are not allowed.
```
### `_getitem`
**Arguments:** `obj, key`
**Decorators:** ``

**Docstring:**
```

```
### `_getattr_for_safe_exec`
**Arguments:** `object, name, default`
**Decorators:** ``

**Docstring:**
```

```
### `_get_attr_for_eval`
**Arguments:** `object, name, default`
**Decorators:** ``

**Docstring:**
```

```
### `_validate_attribute_read`
**Arguments:** `object, name`
**Decorators:** ``

**Docstring:**
```

```
### `_write`
**Arguments:** `obj`
**Decorators:** ``

**Docstring:**
```

```
### `add_data_utils`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `add_module_properties`
**Arguments:** `module, data, filter_method`
**Decorators:** ``

**Docstring:**
```

```

