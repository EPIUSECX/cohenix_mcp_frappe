# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_api_v2.py`

## Classes

### `TestResourceAPIV2`
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
| `test_get_list_fields` | `self` | `` |  |
| `test_create_document` | `self` | `` |  |
| `test_copy_document` | `self` | `` |  |
| `test_delete_document` | `self` | `` |  |
| `test_execute_doc_method` | `self` | `` |  |
| `test_update_document` | `self` | `` |  |
| `test_delete_document_non_existing` | `self` | `` |  |


### `TestMethodAPIV2`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_ping` | `self` | `` |  |
| `test_get_user_info` | `self` | `` |  |
| `test_auth_cycle` | `self` | `` |  |
| `test_404s` | `self` | `` |  |
| `test_shorthand_controller_methods` | `self` | `` |  |
| `test_logout` | `self` | `` |  |
| `test_run_doc_method_in_memory` | `self` | `` |  |
| `test_logs` | `self` | `` |  |
| `test_add_comment` | `self` | `` |  |


### `TestDocTypeAPIV2`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_meta` | `self` | `` |  |
| `test_count` | `self` | `` |  |


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
| `test_blocked_writes_v2` | `self` | `` |  |





## Functions

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

