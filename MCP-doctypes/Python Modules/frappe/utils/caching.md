# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/caching.py`

## Classes

No classes found in this file.


## Functions

### `__generate_request_cache_key`
**Arguments:** `args, kwargs`
**Decorators:** ``

**Docstring:**
```
Generate a key for the cache.
```
### `request_cache`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```
Decorator to cache function calls mid-request.

Cache is stored in `frappe.local.request_cache`.

The cache only persists for the current request and is cleared when the request is over.

The function is called just once per request with the same set of (kw)arguments.

---
Usage:
```
        from frappe.utils.caching import request_cache

        @request_cache
        def calculate_pi(num_terms=0):
            import math, time

            print(f"{num_terms = }")
            time.sleep(10)
            return math.pi

        calculate_pi(10)  # will calculate value
        calculate_pi(10)  # will return value from cache
```
```
### `site_cache`
**Arguments:** `ttl, maxsize`
**Decorators:** ``

**Docstring:**
```
Decorator to cache method calls across requests.

The cache is stored in `frappe.utils.caching._SITE_CACHE`.

The cache persists on the parent process.

It offers a light-weight cache for the current process without the additional
overhead of serializing / deserializing Python objects.

Note: This cache isn't shared among workers. If you need to share data across
workers, use redis (frappe.cache API) instead.

---
Usage:
```
        from frappe.utils.caching import site_cache

        @site_cache
        def calculate_pi():
            import math, time

            precision = get_precision("Math Constant", "Pi") # depends on site data
            return round(math.pi, precision)

        calculate_pi(10) # will calculate value
        calculate_pi(10) # will return value from cache
        calculate_pi.clear_cache() # clear this function's cache for all sites
        calculate_pi(10) # will calculate value
```
```
### `redis_cache`
**Arguments:** `ttl, user, shared`
**Decorators:** ``

**Docstring:**
```
Decorator to cache method calls and its return values in Redis

args:
        ttl: time to expiry in seconds, defaults to 1 hour
        user: `true` should cache be specific to session user.
        shared: `true` should cache be shared across sites
```
### `http_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Decorator to send cache-control response from whitelisted endpoints.

Reference: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control

args:
        public: Results can be cached by proxy if set to True, otherwise only client (browser) can
                        cache results.
        max_age: Cache Time-To-Live
        stale_while_revalidate: Duration for which stale response can be served while revalidation
                                                        occurs.
```
### `deprecated_local_cache`
**Arguments:** `namespace, key, generator, regenerate_if_none`
**Decorators:** ``

**Docstring:**
```

```

