# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/handler.py`

## Classes

No classes found in this file.


## Functions

### `handle`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
handle request
```
### `execute_cmd`
**Arguments:** `cmd, from_async`
**Decorators:** ``

**Docstring:**
```
execute a request as python module
```
### `run_server_script`
**Arguments:** `server_script`
**Decorators:** ``

**Docstring:**
```

```
### `is_valid_http_method`
**Arguments:** `method`
**Decorators:** ``

**Docstring:**
```

```
### `logout`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `web_logout`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `upload_file`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_write_permission`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `download_file`
**Arguments:** `file_url`
**Decorators:** ``

**Docstring:**
```
Download file using token and REST API. Valid session or
token is required to download private files.

Method : GET
Endpoints : download_file, frappe.core.doctype.file.file.download_file
URL Params : file_name = /path/to/file relative to site path
```
### `get_attr`
**Arguments:** `cmd`
**Decorators:** ``

**Docstring:**
```
get method object from cmd
```
### `run_doc_method`
**Arguments:** `method, docs, dt, dn, arg, args`
**Decorators:** ``

**Docstring:**
```
run a whitelisted controller method
```

