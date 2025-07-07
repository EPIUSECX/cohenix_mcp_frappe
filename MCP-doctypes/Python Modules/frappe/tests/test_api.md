# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_api.py`

## Classes

### `ThreadWithReturnValue`
**Inherits:** `Thread`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, group, target, name, args, kwargs` | `` |  |
| `run` | `self` | `` |  |
| `join` | `self` | `` |  |


### `FrappeAPITestCase`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `site_url` | `self` | `property` |  |
| `resource` | `self` | `` |  |
| `method` | `self` | `` |  |
| `doctype_path` | `self` | `` |  |
| `get_path` | `self` | `` |  |
| `sid` | `self` | `cached_property` |  |
| `get` | `self, path, params` | `` |  |
| `post` | `self, path, data` | `` |  |
| `put` | `self, path, data` | `` |  |
| `patch` | `self, path, data` | `` |  |
| `delete` | `self, path` | `` |  |
| `tearDown` | `self` | `` |  |


### `TestResourceAPI`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_unauthorized_call` | `self` | `` |  |
| `test_get_list` | `self` | `` |  |
| `test_get_list_limit` | `self` | `` |  |
| `test_get_list_dict` | `self` | `` |  |
| `test_get_list_debug` | `self` | `` |  |
| `test_get_list_fields` | `self` | `` |  |
| `test_create_document` | `self` | `` |  |
| `test_update_document` | `self` | `` |  |
| `test_delete_document` | `self` | `` |  |
| `test_run_doc_method` | `self` | `` |  |


### `TestMethodAPI`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_ping` | `self` | `` |  |
| `test_get_user_info` | `self` | `` |  |
| `test_auth_cycle` | `self` | `` |  |
| `test_404s` | `self` | `` |  |
| `test_logs` | `self` | `` |  |
| `test_array_response` | `self` | `` |  |


### `TestReadOnlyMode`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```
During migration if read only mode can be enabled.
Test if reads work well and writes are blocked
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `test_reads` | `self` | `` |  |
| `test_blocked_writes` | `self` | `` |  |


### `TestWSGIApp`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_request_hooks` | `self` | `` |  |


### `TestResponse`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_generate_pdf` | `self` | `` |  |
| `test_binary_and_csv_response` | `self` | `` |  |
| `test_download_private_file_with_unique_url` | `self` | `` |  |
| `test_login_redirects` | `self` | `` |  |





## Functions

### `suppress_stdout`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```
Supress stdout for tests which expectedly make noise
but that you don't need in tests
```
### `make_request`
**Arguments:** `target, args, kwargs, site`
**Decorators:** ``

**Docstring:**
```

```
### `patch_request_header`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `before_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `after_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `generate_admin_keys`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_array`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```

