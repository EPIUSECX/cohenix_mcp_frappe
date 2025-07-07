# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/delete_doc.py`

## Classes

No classes found in this file.


## Functions

### `delete_doc`
**Arguments:** `doctype, name, force, ignore_doctypes, for_reload, ignore_permissions, flags, ignore_on_trash, ignore_missing, delete_permanently`
**Decorators:** ``

**Docstring:**
```
Deletes a doc(dt, dn) and validates if it is not submitted and not linked in a live record
```
### `add_to_deleted_document`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Add this document to Deleted Document table. Called after delete
```
### `update_naming_series`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `delete_from_table`
**Arguments:** `doctype, name, ignore_doctypes, doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_flags`
**Arguments:** `doc, flags, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `check_permission_and_not_submitted`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `check_if_doc_is_linked`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Raises exception if the given document is linked in another record.
```
### `check_if_doc_is_dynamically_linked`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Raise `frappe.LinkExistsError` if the document is dynamically linked
```
### `raise_link_exists_exception`
**Arguments:** `doc, reference_doctype, reference_docname, row`
**Decorators:** ``

**Docstring:**
```

```
### `delete_dynamic_links`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `delete_references`
**Arguments:** `doctype, reference_doctype, reference_name, reference_doctype_field, reference_name_field`
**Decorators:** ``

**Docstring:**
```

```
### `clear_references`
**Arguments:** `doctype, reference_doctype, reference_name, reference_doctype_field, reference_name_field`
**Decorators:** ``

**Docstring:**
```

```
### `clear_timeline_references`
**Arguments:** `link_doctype, link_name`
**Decorators:** ``

**Docstring:**
```

```
### `insert_feed`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `delete_controllers`
**Arguments:** `doctype, module`
**Decorators:** ``

**Docstring:**
```
Delete controller code in the doctype folder
```

