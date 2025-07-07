# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/redis_wrapper.py`

## Classes

### `RedisearchWrapper`
**Inherits:** `Search`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `sugadd` | `self, key` | `` |  |
| `suglen` | `self, key` | `` |  |
| `sugdel` | `self, key, string` | `` |  |
| `sugget` | `self, key` | `` |  |


### `RedisWrapper`


**Docstring:**
```
Redis client that will automatically prefix conf.db_name
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `connected` | `self` | `` |  |
| `__call__` | `self` | `` | WARNING: Added for backward compatibility to support frappe.cache().method(...) |
| `make_key` | `self, key, user, shared` | `` |  |
| `set_value` | `self, key, val, user, expires_in_sec, shared` | `` | Sets cache value.

:param key: Cache key
:param val: Value to be cached
:param user: Prepends key with User
:param expires_in_sec: Expire value of this key in X seconds |
| `get_value` | `self, key, generator, user, expires, shared` | `` | Return cache value. If not found and generator function is
        given, call the generator.

:param key: Cache key.
:param generator: Function to be called to generate a value if `None` is returned.
:param expires: If the key is supposed to be with an expiry, don't store it in frappe.local |
| `expire_key` | `self, key, time` | `` |  |
| `get_all` | `self, key` | `` |  |
| `get_keys` | `self, key` | `` | Return keys starting with `key`. |
| `delete_keys` | `self, key` | `` | Delete keys with wildcard `*`. |
| `delete_key` | `self` | `` |  |
| `delete_value` | `self, keys, user, make_keys, shared` | `` | Delete value, list of values. |
| `lpush` | `self, key, value` | `` |  |
| `rpush` | `self, key, value` | `` |  |
| `lpop` | `self, key` | `` |  |
| `rpop` | `self, key` | `` |  |
| `llen` | `self, key` | `` |  |
| `lrange` | `self, key, start, stop` | `` |  |
| `ltrim` | `self, key, start, stop` | `` |  |
| `hset` | `self, name, key, value, shared` | `` |  |
| `hexists` | `self, name, key, shared` | `` |  |
| `exists` | `self` | `` |  |
| `hgetall` | `self, name` | `` |  |
| `hget` | `self, name, key, generator, shared` | `` |  |
| `hdel` | `self, name, keys, shared, pipeline` | `` | A wrapper around redis' HDEL command

:param name: The hash name
:param keys: the keys to delete
:param shared: shared frappe key or not
:param pipeline: A redis.client.Pipeline object, if this transaction is to be run in a pipeline |
| `hdel_names` | `self, names, key` | `` | A function to call HDEL on multiple hash names with a common key, run in a single pipeline

:param names: The hash names
:param key: The common key |
| `hdel_keys` | `self, name_starts_with, key` | `` | Delete hash names with wildcard `*` and key |
| `hkeys` | `self, name` | `` |  |
| `sadd` | `self, name` | `` | Add a member/members to a given set |
| `srem` | `self, name` | `` | Remove a specific member/list of members from the set. |
| `sismember` | `self, name, value` | `` | Return True or False based on if a given value is present in the set. |
| `spop` | `self, name` | `` | Remove and returns a random member from the set. |
| `srandmember` | `self, name, count` | `` | Return a random member from the set. |
| `smembers` | `self, name` | `` | Return all members of the set. |
| `ft` | `self, index_name` | `` |  |


### `_TrackedConnection`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `_enable_client_tracking` | `self, conn` | `` |  |


### `ClientCache`


**Docstring:**
```
A subset of RedisWrapper that keeps "local" cache across requests.

Main reason for doing this is improving performance while reading things like hooks, schema.
This feature is internal to Frappe Framework and is subjected to change without any notice.
There aren't many use cases for such aggressive caching outside of core Framework.

This is an implementation of Redis' "client side caching" concept:
        - https://redis.io/docs/latest/develop/reference/client-side-caching/

Usage/Notes:
        - Cache keys that do not change often: Think hours-days, not minutes.
        - Cache keys that are read frequently, e.g. every request or at least >10% of the requests.
        - Cache values are not huge, consider avg size of ~4kb per value. You can deviate here and
          there but not go crazy with caching large values in this cache.
        - We have hardcoded 10 minutes "local" ttl and max 1024 keys.
                You're not supposed to work with these numbers, not change them.
        - Same keys can be accessed with `frappe.cache` too, but that won't implement invalidation.
        - Invalidate things as usual using `delete_value`. Local invalidation should be instant.
          Do not expect sub-second invalidation guarantees across processes.
          If you need that kind of guarantees, don't use this cache.
        - When redis connection isn't available or any unknown exceptions are encountered, this
          cache automatically turns itself off and falls back to behaviour that is equivalent to
          default Redis cache behaviour.
        - Never use `frappe.cache`'s request local cache along with client-side cache. Two
          different copies of same key are a big source of data races.
        - This cache uses simple FIFO eviction policy. Make sure your access patterns don't cause
          the worst case behaviour for this policy. E.g. looping over `maxsize` items repeatedly.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, maxsize, ttl, monitor` | `` |  |
| `get_value` | `self, key` | `` |  |
| `set_value` | `self, key, val` | `` |  |
| `get_doc` | `self, doctype, name` | `` | Utility to fetch and store documents in client cache.

Use sparingly, this should ideally be used for settings and doctypes that have few known
number of documents. |
| `ensure_max_size` | `self` | `` |  |
| `delete_value` | `self, key` | `` |  |
| `delete_keys` | `self, pattern` | `` |  |
| `run_invalidator_thread` | `self` | `` |  |
| `erase_persistent_caches` | `self` | `` | Send signal to clear all worker-specific caches

This can include cached controller resolution, @site_cache and any other similar persistent
cache. |
| `_handle_invalidation` | `self, message` | `` |  |
| `_handle_persistent_cache_invalidation` | `self, message` | `` |  |
| `_exception_handler` | `self, exc, pubsub, pubsub_thread` | `` |  |
| `clear_cache` | `self` | `` |  |
| `statistics` | `self` | `property` |  |
| `reset_statistics` | `self` | `` |  |





## Functions

### `setup_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_sentinel_connection`
**Arguments:** `sentinels, sentinel_username, sentinel_password, master_username, master_password`
**Decorators:** ``

**Docstring:**
```

```

