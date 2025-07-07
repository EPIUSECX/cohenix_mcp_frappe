# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/client.py`

## Classes

No classes found in this file.


## Functions

### `get_list`
**Arguments:** `doctype, fields, filters, group_by, order_by, limit_start, limit_page_length, parent, debug, as_dict, or_filters`
**Decorators:** ``

**Docstring:**
```
Return a list of records by filters, fields, ordering and limit.

:param doctype: DocType of the data to be queried
:param fields: fields to be returned. Default is `name`
:param filters: filter list by this dict
:param order_by: Order by this fieldname
:param limit_start: Start at this index
:param limit_page_length: Number of records to be returned (default 20)
```
### `get_count`
**Arguments:** `doctype, filters, debug, cache`
**Decorators:** ``

**Docstring:**
```

```
### `get`
**Arguments:** `doctype, name, filters, parent`
**Decorators:** ``

**Docstring:**
```
Return a document by name or filters.

:param doctype: DocType of the document to be returned
:param name: return document of this `name`
:param filters: If name is not set, filter by these values and return the first match
```
### `get_value`
**Arguments:** `doctype, fieldname, filters, as_dict, debug, parent`
**Decorators:** ``

**Docstring:**
```
Return a value from a document.

:param doctype: DocType to be queried
:param fieldname: Field to be returned (default `name`)
:param filters: dict or string for identifying the record
```
### `get_single_value`
**Arguments:** `doctype, field`
**Decorators:** ``

**Docstring:**
```

```
### `set_value`
**Arguments:** `doctype, name, fieldname, value`
**Decorators:** ``

**Docstring:**
```
Set a value using get_doc, group of values

:param doctype: DocType of the document
:param name: name of the document
:param fieldname: fieldname string or JSON / dict with key value pair
:param value: value if fieldname is JSON / dict
```
### `insert`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Insert a document

:param doc: JSON or dict object to be inserted
```
### `insert_many`
**Arguments:** `docs`
**Decorators:** ``

**Docstring:**
```
Insert multiple documents

:param docs: JSON or list of dict objects to be inserted in one request
```
### `save`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Update (save) an existing document

:param doc: JSON or dict object with the properties of the document to be updated
```
### `rename_doc`
**Arguments:** `doctype, old_name, new_name, merge`
**Decorators:** ``

**Docstring:**
```
Rename document

:param doctype: DocType of the document to be renamed
:param old_name: Current `name` of the document to be renamed
:param new_name: New `name` to be set
```
### `submit`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Submit a document

:param doc: JSON or dict object to be submitted remotely
```
### `cancel`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Cancel a document

:param doctype: DocType of the document to be cancelled
:param name: name of the document to be cancelled
```
### `delete`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Delete a remote document

:param doctype: DocType of the document to be deleted
:param name: name of the document to be deleted
```
### `bulk_update`
**Arguments:** `docs`
**Decorators:** ``

**Docstring:**
```
Bulk update documents

:param docs: JSON list of documents to be updated remotely. Each document must have `docname` property
```
### `has_permission`
**Arguments:** `doctype, docname, perm_type`
**Decorators:** ``

**Docstring:**
```
Return a JSON with data whether the document has the requested permission.

:param doctype: DocType of the document to be checked
:param docname: `name` of the document to be checked
:param perm_type: one of `read`, `write`, `create`, `submit`, `cancel`, `report`. Default is `read`
```
### `get_doc_permissions`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```
Return an evaluated document permissions dict like `{"read":1, "write":1}`.

:param doctype: DocType of the document to be evaluated
:param docname: `name` of the document to be evaluated
```
### `get_password`
**Arguments:** `doctype, name, fieldname`
**Decorators:** ``

**Docstring:**
```
Return a password type property. Only applicable for System Managers

:param doctype: DocType of the document that holds the password
:param name: `name` of the document that holds the password
:param fieldname: `fieldname` of the password property
```
### `get_time_zone`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the default time zone.
```
### `attach_file`
**Arguments:** `filename, filedata, doctype, docname, folder, decode_base64, is_private, docfield`
**Decorators:** ``

**Docstring:**
```
Attach a file to Document

:param filename: filename e.g. test-file.txt
:param filedata: base64 encode filedata which must be urlencoded
:param doctype: Reference DocType to attach file to
:param docname: Reference DocName to attach file to
:param folder: Folder to add File into
:param decode_base64: decode filedata from base64 encode, default is False
:param is_private: Attach file as private file (1 or 0)
:param docfield: file to attach to (optional)
```
### `is_document_amended`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `validate_link`
**Arguments:** `doctype, docname, fields`
**Decorators:** ``

**Docstring:**
```

```
### `insert_doc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Insert document and return parent document object with appended child document if `doc` is child document else return the inserted document object.

:param doc: doc to insert (dict)
```
### `delete_doc`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Deletes document
if doctype is a child table, then deletes the child record using the parent doc
so that the parent doc's `on_update` is called
```

