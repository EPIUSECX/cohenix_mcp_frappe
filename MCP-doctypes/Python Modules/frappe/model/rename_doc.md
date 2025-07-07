# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/rename_doc.py`

## Classes

No classes found in this file.


## Functions

### `update_document_title`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Update the name or title of a document. Return `name` if document was renamed, `docname` if renaming operation was queued.

:param doctype: DocType of the document
:param docname: Name of the document
:param title: New Title of the document
:param name: New Name of the document
:param merge: Merge the current Document with the existing one if exists
:param enqueue: Enqueue the rename operation, title is updated in current process
```
### `rename_doc`
**Arguments:** `doctype, old, new, force, merge, ignore_permissions, ignore_if_exists, show_alert, rebuild_search, doc, validate`
**Decorators:** ``

**Docstring:**
```
Rename a doc(dt, old) to doc(dt, new) and update all linked fields of type "Link".

doc: Document object to be renamed.
new: New name for the record. If None, and doctype is specified, new name may be automatically generated via before_rename hooks.
doctype: DocType of the document. Not required if doc is passed.
old: Current name of the document. Not required if doc is passed.
force: Allow even if document is not allowed to be renamed.
merge: Merge with existing document of new name.
ignore_permissions: Ignore user permissions while renaming.
ignore_if_exists: Don't raise exception if document with new name already exists. This will quietely overwrite the existing document.
show_alert: Display alert if document is renamed successfully.
rebuild_search: Rebuild linked doctype search after renaming.
validate: Validate before renaming. If False, it is assumed that the caller has already validated.
```
### `update_assignments`
**Arguments:** `old, new, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `update_user_settings`
**Arguments:** `old, new, link_fields`
**Decorators:** ``

**Docstring:**
```
Update the user settings of all the linked doctypes while renaming.
```
### `update_customizations`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```

```
### `update_attachments`
**Arguments:** `doctype, old, new`
**Decorators:** ``

**Docstring:**
```

```
### `rename_versions`
**Arguments:** `doctype, old, new`
**Decorators:** ``

**Docstring:**
```

```
### `rename_parent_and_child`
**Arguments:** `doctype, old, new, meta`
**Decorators:** ``

**Docstring:**
```

```
### `update_autoname_field`
**Arguments:** `doctype, new, meta`
**Decorators:** ``

**Docstring:**
```

```
### `validate_rename`
**Arguments:** `doctype, old, new, meta, merge, force, ignore_permissions, ignore_if_exists, save_point, old_doc`
**Decorators:** ``

**Docstring:**
```

```
### `rename_doctype`
**Arguments:** `doctype, old, new`
**Decorators:** ``

**Docstring:**
```

```
### `update_child_docs`
**Arguments:** `old, new, meta`
**Decorators:** ``

**Docstring:**
```

```
### `update_link_field_values`
**Arguments:** `link_fields, old, new, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_link_fields`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `update_options_for_fieldtype`
**Arguments:** `fieldtype, old, new`
**Decorators:** ``

**Docstring:**
```

```
### `get_select_fields`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```
get select type fields where doctype's name is hardcoded as
new line separated list
```
### `update_select_field_values`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```

```
### `update_parenttype_values`
**Arguments:** `old, new`
**Decorators:** ``

**Docstring:**
```

```
### `rename_dynamic_links`
**Arguments:** `doctype, old, new`
**Decorators:** ``

**Docstring:**
```

```
### `bulk_rename`
**Arguments:** `doctype, rows, via_console`
**Decorators:** ``

**Docstring:**
```
Bulk rename documents

:param doctype: DocType to be renamed
:param rows: list of documents as `((oldname, newname, merge(optional)), ..)`
```

