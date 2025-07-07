# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/classes/integration_test_case.py`

## Classes

### `IntegrationTestCase`
**Inherits:** `UnitTestCase`


**Docstring:**
```
Integration test class for Frappe tests.

Key features:
- Automatic database setup and teardown
- Utilities for managing database connections
- Context managers for query counting and Redis call monitoring
- Lazy loading of test record dependencies

Note: If you override `setUpClass`, make sure to call `super().setUpClass()`
to maintain the functionality of this base class.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `primary_connection` | `self` | `contextmanager` | Switch to primary DB connection

This is used for simulating multiple users performing actions by simulating two DB connections |
| `secondary_connection` | `self` | `contextmanager` | Switch to secondary DB connection. |
| `_rollback_connections` | `self` | `` |  |
| `assertQueryCount` | `self, count, query_type` | `contextmanager` |  |
| `assertRedisCallCounts` | `self, count` | `contextmanager` |  |
| `assertRowsRead` | `self, count` | `contextmanager` |  |





## Functions

### `_commit_watcher`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_rollback_db`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_restore_ctx_locals`
**Arguments:** `flags`
**Decorators:** ``

**Docstring:**
```

```

