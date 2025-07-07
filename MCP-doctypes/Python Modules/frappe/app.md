# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/app.py`

## Classes

No classes found in this file.


## Functions

### `after_response_wrapper`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Wrap a WSGI application to call after_response hooks after we have responded.

This is done to reduce response time by deferring expensive tasks.
```
### `application`
**Arguments:** `request`
**Decorators:** `after_response_wrapper`

**Docstring:**
```

```
### `run_after_request_hooks`
**Arguments:** `request, response`
**Decorators:** ``

**Docstring:**
```

```
### `init_request`
**Arguments:** `request`
**Decorators:** ``

**Docstring:**
```

```
### `setup_read_only_mode`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
During maintenance_mode reads to DB can still be performed to reduce downtime. This
function sets up read only mode

- Setting global flag so other pages, desk and database can know that we are in read only mode.
- Setup read only database access either by:
    - Connecting to read replica if one exists
    - Or setting up read only SQL transactions.
```
### `log_request`
**Arguments:** `request, response`
**Decorators:** ``

**Docstring:**
```

```
### `process_response`
**Arguments:** `response`
**Decorators:** ``

**Docstring:**
```

```
### `set_cors_headers`
**Arguments:** `response`
**Decorators:** ``

**Docstring:**
```

```
### `make_form_dict`
**Arguments:** `request`
**Decorators:** ``

**Docstring:**
```

```
### `handle_exception`
**Arguments:** `e`
**Decorators:** `handle_does_not_exist_error`

**Docstring:**
```

```
### `sync_database`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `serve`
**Arguments:** `port, profile, no_reload, no_threading, site, sites_path, proxy`
**Decorators:** ``

**Docstring:**
```

```
### `application_with_statics`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

