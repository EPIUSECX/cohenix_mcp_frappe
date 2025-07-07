# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_caching.py`

## Classes

### `TestCachingUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_request_cache` | `self` | `` |  |


### `TestSiteCache`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_site_cache` | `self` | `` |  |


### `TestRedisCache`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_redis_cache` | `self` | `` |  |
| `test_redis_cache_without_params` | `self` | `` |  |
| `test_redis_cache_diff_args` | `self` | `` |  |
| `test_global_clear_cache` | `self` | `` |  |
| `test_user_cache` | `self` | `` |  |


### `TestDocumentCache`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_caching` | `self` | `` |  |
| `test_cache_invalidation_set_value` | `self` | `` |  |


### `TestRedisWrapper`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_delete_keys` | `self` | `` |  |
| `test_hash` | `self` | `` |  |
| `test_user_cache_clear` | `self` | `` |  |
| `test_doctype_cache_clear` | `self` | `` |  |
| `test_backward_compat_cache` | `self` | `` |  |


### `TestHttpCache`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_http_headers` | `self` | `` |  |





## Functions

### `request_specific_api`
**Arguments:** `a, b`
**Decorators:** `request_cache`

**Docstring:**
```

```
### `ping`
**Arguments:** ``
**Decorators:** `site_cache`

**Docstring:**
```

```
### `ping_with_ttl`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

