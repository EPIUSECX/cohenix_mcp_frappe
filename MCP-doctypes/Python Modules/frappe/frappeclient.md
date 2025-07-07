# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/frappeclient.py`

## Classes

### `AuthError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SiteExpiredError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SiteUnreachableError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FrappeException`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `FrappeClient`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, url, username, password, verify, api_key, api_secret, frappe_authorization_source` | `` |  |
| `__enter__` | `self` | `` |  |
| `__exit__` | `self` | `` |  |
| `_login` | `self, username, password` | `` | Login/start a session. Called internally on init |
| `setup_key_authentication_headers` | `self` | `` |  |
| `logout` | `self` | `` | Logout session |
| `get_list` | `self, doctype, fields, filters, limit_start, limit_page_length` | `` | Return list of records of a particular type. |
| `insert` | `self, doc` | `` | Insert a document to the remote server

:param doc: A dict or Document object to be inserted remotely |
| `insert_many` | `self, docs` | `` | Insert multiple documents to the remote server

:param docs: List of dict or Document objects to be inserted in one request |
| `update` | `self, doc` | `` | Update a remote document

:param doc: dict or Document object to be updated remotely. `name` is mandatory for this |
| `bulk_update` | `self, docs` | `` | Bulk update documents remotely

:param docs: List of dict or Document objects to be updated remotely (by `name`) |
| `delete` | `self, doctype, name` | `` | Delete remote document by name

:param doctype: `doctype` to be deleted
:param name: `name` of document to be deleted |
| `submit` | `self, doc` | `` | Submit remote document

:param doc: dict or Document object to be submitted remotely |
| `get_value` | `self, doctype, fieldname, filters` | `` | Return a value from a document.

:param doctype: DocType to be queried
:param fieldname: Field to be returned (default `name`)
:param filters: dict or string for identifying the record |
| `set_value` | `self, doctype, docname, fieldname, value` | `` | Set a value in a remote document

:param doctype: DocType of the document to be updated
:param docname: name of the document to be updated
:param fieldname: fieldname of the document to be updated
:param value: value to be updated |
| `cancel` | `self, doctype, name` | `` | Cancel a remote document

:param doctype: DocType of the document to be cancelled
:param name: name of the document to be cancelled |
| `get_doc` | `self, doctype, name, filters, fields` | `` | Return a single remote document.

:param doctype: DocType of the document to be returned
:param name: (optional) `name` of the document to be returned
:param filters: (optional) Filter by this dict if name is not set
:param fields: (optional) Fields to be returned, will return everything if not set |
| `rename_doc` | `self, doctype, old_name, new_name` | `` | Rename remote document

:param doctype: DocType of the document to be renamed
:param old_name: Current `name` of the document to be renamed
:param new_name: New `name` to be set |
| `migrate_doctype` | `self, doctype, filters, update, verbose, exclude, preprocess` | `` | Migrate records from another doctype |
| `migrate_single` | `self, doctype` | `` |  |
| `get_api` | `self, method, params` | `` |  |
| `post_api` | `self, method, params` | `` |  |
| `get_request` | `self, params` | `` |  |
| `post_request` | `self, data` | `` |  |
| `preprocess` | `self, params` | `` | convert dicts, lists to json |
| `post_process` | `self, response` | `` |  |


### `FrappeOAuth2Client`
**Inherits:** `FrappeClient`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, url, access_token, verify` | `` |  |





## Functions

No top-level functions found in this file.
