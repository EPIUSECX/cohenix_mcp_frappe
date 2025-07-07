# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_perf.py`

## Classes

### `TestPerformance`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `reset_request_specific_caches` | `self` | `` |  |
| `setUp` | `self` | `` |  |
| `test_meta_caching` | `self` | `` |  |
| `test_permitted_fieldnames` | `self` | `` |  |
| `test_set_value_query_count` | `self` | `` |  |
| `test_controller_caching` | `self` | `` |  |
| `test_get_value_limits` | `self` | `` |  |
| `test_db_value_cache` | `self` | `` | Link validation if repeated should just use db.value_cache, hence no extra queries |
| `test_req_per_seconds_basic` | `self` | `` | Ideally should be ran against gunicorn worker, though I have not seen any difference
when using werkzeug's run_simple for synchronous requests. |
| `test_homepage_resolver` | `self` | `` |  |
| `test_consistent_build_version` | `self` | `` |  |
| `test_get_list_single_query` | `self` | `` | get_list should only perform single query. |
| `test_no_ifnull_checks` | `self` | `` |  |
| `test_no_stale_ref_sql` | `self` | `` | frappe.db.sql should not hold any internal references to result set.

pymysql stores results internally. If your code reads a lot and doesn't make another
query, for that entire duration there's copy of result consuming memory in internal
attributes of pymysql.
We clear it manually, this test ensures that it actually works. |
| `test_no_cyclic_references` | `self` | `` |  |
| `test_get_doc_cache_calls` | `self` | `` |  |
| `test_local_caching` | `self` | `` |  |
| `test_redis_cache_calls` | `self` | `` |  |
| `test_idle_cpu_utilization_redis_pubsub` | `self` | `` |  |
| `test_cpu_allocation` | `self` | `` |  |


### `TestOverheadCalls`
**Inherits:** `FrappeAPITestCase`


**Docstring:**
```
Test that typical redis and db calls remain same overtime.

If this tests fail on your PR, make sure you're not introducing something in hot-path of these
endpoints. Only update values if you're really sure that's the right call.
Every call increase here is an actual increase in cost!
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_ping_overheads` | `self` | `` |  |
| `test_ping_overheads_authenticated` | `self` | `` |  |
| `test_list_view_overheads` | `self` | `` |  |
| `test_get_doc_overheads` | `self` | `` |  |





## Functions

### `redis_cached_func`
**Arguments:** ``
**Decorators:** `redis_cache`

**Docstring:**
```

```

