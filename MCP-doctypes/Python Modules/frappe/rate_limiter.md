# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/rate_limiter.py`

## Classes

### `RateLimiter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, limit, window` | `` |  |
| `apply` | `self` | `` |  |
| `reject` | `self` | `` |  |
| `update` | `self` | `` |  |
| `headers` | `self` | `` |  |
| `record_request_end` | `self` | `` |  |
| `respond` | `self` | `` |  |





## Functions

### `apply`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `respond`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `rate_limit`
**Arguments:** `key, limit, seconds, methods, ip_based`
**Decorators:** ``

**Docstring:**
```
Decorator to rate limit an endpoint.

This will limit Number of requests per endpoint to `limit` within `seconds`.
Uses redis cache to track request counts.

:param key: Key is used to identify the requests uniqueness (Optional)
:param limit: Maximum number of requests to allow with in window time
:type limit: Callable or Integer
:param seconds: window time to allow requests
:param methods: Limit the validation for these methods.
        `ALL` is a wildcard that applies rate limit on all methods.
:type methods: string or list or tuple
:param ip_based: flag to allow ip based rate-limiting
:type ip_based: Boolean

Return: a decorator function that limit the number of requests per endpoint
```

