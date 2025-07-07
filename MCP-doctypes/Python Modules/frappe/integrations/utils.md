# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/utils.py`

## Classes

No classes found in this file.


## Functions

### `make_request`
**Arguments:** `method, url, auth, headers, data, json, params`
**Decorators:** ``

**Docstring:**
```

```
### `make_get_request`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Make a 'GET' HTTP request to the given `url` and return processed response.

You can optionally pass the below parameters:

* `headers`: Headers to be set in the request.
* `params`: Query parameters to be passed in the request.
* `auth`: Auth credentials.
```
### `make_post_request`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Make a 'POST' HTTP request to the given `url` and return processed response.

You can optionally pass the below parameters:

* `headers`: Headers to be set in the request.
* `data`: Data to be passed in body of the request.
* `json`: JSON to be passed in the request.
* `params`: Query parameters to be passed in the request.
* `auth`: Auth credentials.
```
### `make_put_request`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Make a 'PUT' HTTP request to the given `url` and return processed response.

You can optionally pass the below parameters:

* `headers`: Headers to be set in the request.
* `data`: Data to be passed in body of the request.
* `json`: JSON to be passed in the request.
* `params`: Query parameters to be passed in the request.
* `auth`: Auth credentials.
```
### `make_patch_request`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Make a 'PATCH' HTTP request to the given `url` and return processed response.

You can optionally pass the below parameters:

* `headers`: Headers to be set in the request.
* `data`: Data to be passed in body of the request.
* `json`: JSON to be passed in the request.
* `params`: Query parameters to be passed in the request.
* `auth`: Auth credentials.
```
### `make_delete_request`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Make a 'DELETE' HTTP request to the given `url` and return processed response.

You can optionally pass the below parameters:

* `headers`: Headers to be set in the request.
* `data`: Data to be passed in body of the request.
* `json`: JSON to be passed in the request.
* `params`: Query parameters to be passed in the request.
* `auth`: Auth credentials.
```
### `create_request_log`
**Arguments:** `data, integration_type, service_name, name, error, request_headers, output`
**Decorators:** ``

**Docstring:**
```
DEPRECATED: The parameter integration_type will be removed in the next major release.
Use is_remote_request instead.
```
### `get_json`
**Arguments:** `obj`
**Decorators:** ``

**Docstring:**
```

```
### `json_handler`
**Arguments:** `obj`
**Decorators:** ``

**Docstring:**
```

```

