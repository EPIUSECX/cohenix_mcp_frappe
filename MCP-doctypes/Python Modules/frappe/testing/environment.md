# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/testing/environment.py`

## Classes

### `IntegrationTestPreparation`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, cfg` | `` |  |
| `__call__` | `self, suite, app, category` | `` | Prepare the environment for integration tests. |
| `_run_before_test_hooks` | `app, category` | `staticmethod, debug_timer` | Run 'before_tests' hooks |
| `_create_global_test_record_dependencies` | `app, category` | `staticmethod, debug_timer` | Create global test record dependencies |





## Functions

### `_initialize_test_environment`
**Arguments:** `site, config`
**Decorators:** `debug_timer`

**Docstring:**
```
Initialize the test environment
```
### `_cleanup_after_tests`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Perform cleanup operations after running tests
```
### `_disable_scheduler_if_needed`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Disable scheduler if it's not already disabled
```
### `_decorate_all_methods_and_functions_with_type_checker`
**Arguments:** ``
**Decorators:** `debug_timer`

**Docstring:**
```

```

