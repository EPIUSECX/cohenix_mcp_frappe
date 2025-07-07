# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/document.py`

## Classes

### `Document`
**Inherits:** `BaseDocument`


**Docstring:**
```
All controllers inherit from `Document`.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` | Constructor.

:param arg1: DocType name as string, document **dict**, or DocRef object
:param arg2: Document name, if `arg1` is DocType name.

If DocType name and document name are passed, the object will load
all values (including child documents) from the database. |
| `is_locked` | `self` | `property` |  |
| `load_from_db` | `self` | `` | Load document and children from database and create properties
from fields |
| `load_children_from_db` | `self` | `` |  |
| `_load_child_table_from_db` | `self, fieldname, child_doctype` | `` |  |
| `reload` | `self` | `` | Reload document from database |
| `get_latest` | `self` | `` |  |
| `check_permission` | `self, permtype, permlevel` | `` | Raise `frappe.PermissionError` if not permitted |
| `has_permission` | `self, permtype` | `` | Call `frappe.permissions.has_permission` if `ignore_permissions` flag isn't truthy

:param permtype: `read`, `write`, `submit`, `cancel`, `delete`, etc. |
| `_handle_permission_failure` | `self, perm_type` | `` |  |
| `raise_no_permission_to` | `self, perm_type` | `` | Raise `frappe.PermissionError`. |
| `insert` | `self, ignore_permissions, ignore_links, ignore_if_duplicate, ignore_mandatory, set_name, set_child_names` | `` | Insert the document in the database (as a new document).
This will check for user permissions and execute `before_insert`,
`validate`, `on_update`, `after_insert` methods if they are written.

:param ignore_permissions: Do not check permissions if True.
:param ignore_links: Do not check validity of links if True.
:param ignore_if_duplicate: Do not raise error if a duplicate entry exists.
:param ignore_mandatory: Do not check missing mandatory fields if True.
:param set_name: Name to set for the document, if valid.
:param set_child_names: Whether to set names for the child documents. |
| `check_if_locked` | `self` | `` |  |
| `save` | `self` | `` | Wrapper for _save |
| `_save` | `self, ignore_permissions, ignore_version` | `` | Save the current document in the database in the **DocType**'s table or
`tabSingles` (for single types).

This will check for user permissions and execute
`validate` before updating, `on_update` after updating triggers.

:param ignore_permissions: Do not check permissions if True.
:param ignore_version: Do not save version if True. |
| `validate_amended_from` | `self` | `` |  |
| `copy_attachments_from_amended_from` | `self` | `` | Copy attachments from `amended_from` |
| `update_children` | `self` | `` | update child tables |
| `update_child_table` | `self, fieldname, df` | `` | sync child table for given fieldname |
| `get_doc_before_save` | `self` | `` |  |
| `has_value_changed` | `self, fieldname` | `` | Return True if value has changed before and after saving. |
| `get_value_before_save` | `self, fieldname` | `` | Returns value of a field before saving

Note: This function only works in save context like doc.save, doc.submit. |
| `set_new_name` | `self, force, set_name, set_child_names` | `` | Calls `frappe.naming.set_new_name` for parent and child docs. |
| `get_title` | `self` | `` | Get the document title based on title_field or `title` or `name` |
| `set_title_field` | `self` | `` | Set title field based on template |
| `update_single` | `self, d` | `` | Updates values for Single type Document in `tabSingles`. |
| `set_user_and_timestamp` | `self` | `` |  |
| `set_docstatus` | `self` | `` |  |
| `_validate` | `self` | `` |  |
| `_validate_non_negative` | `self` | `` |  |
| `_fix_rating_value` | `self` | `` |  |
| `validate_workflow` | `self` | `` | Validate if the workflow transition is valid |
| `validate_set_only_once` | `self` | `` | Validate that fields are not changed if not in insert |
| `is_child_table_same` | `self, fieldname` | `` | Validate child table is same as original table before saving |
| `apply_fieldlevel_read_permissions` | `self` | `` | Remove values the user is not allowed to read. |
| `validate_higher_perm_levels` | `self` | `` | If the user does not have permissions at permlevel > 0, then reset the values to original / default |
| `get_permlevel_access` | `self, permission_type` | `` |  |
| `has_permlevel_access_to` | `self, fieldname, df, permission_type` | `` |  |
| `get_permissions` | `self` | `` |  |
| `_set_defaults` | `self` | `` |  |
| `check_if_latest` | `self` | `` | Checks if `modified` timestamp provided by document being updated is same as the
`modified` timestamp in the database. If there is a different, the document has been
updated in the database after the current copy was read. Will throw an error if
timestamps don't match.

Will also validate document transitions (Save > Submit > Cancel) calling
`self.check_docstatus_transition`. |
| `check_docstatus_transition` | `self, to_docstatus` | `` | Ensures valid `docstatus` transition.
Valid transitions are (number in brackets is `docstatus`):

- Save (0) > Save (0)
- Save (0) > Submit (1)
- Submit (1) > Submit (1)
- Submit (1) > Cancel (2) |
| `set_parent_in_children` | `self` | `` | Updates `parent` and `parenttype` property in all children. |
| `set_name_in_children` | `self` | `` |  |
| `validate_update_after_submit` | `self` | `` |  |
| `_validate_mandatory` | `self` | `` |  |
| `_validate_links` | `self` | `` |  |
| `get_all_children` | `self, parenttype` | `` | Return all children documents from **Table** type fields in a list. |
| `run_method` | `self, method` | `` | run standard triggers, plus those in hooks |
| `run_trigger` | `self, method` | `` |  |
| `run_notifications` | `self, method` | `` | Run notifications for this method |
| `_submit` | `self` | `` | Submit the document. Sets `docstatus` = 1, then saves. |
| `_cancel` | `self` | `` | Cancel the document. Sets `docstatus` = 2, then saves. |
| `_rename` | `self, name, merge, force, validate_rename` | `` | Rename the document. Triggers frappe.rename_doc, then reloads. |
| `submit` | `self` | `` | Submit the document. Sets `docstatus` = 1, then saves. |
| `cancel` | `self` | `` | Cancel the document. Sets `docstatus` = 2, then saves. |
| `discard` | `self` | `` | Discard the draft document. Sets `docstatus` = 2 with db_set. |
| `rename` | `self, name, merge, force, validate_rename` | `` | Rename the document to `name`. This transforms the current object. |
| `delete` | `self, ignore_permissions, force` | `` | Delete document. |
| `run_before_save_methods` | `self` | `` | Run standard methods before     `INSERT` or `UPDATE`. Standard Methods are:

- `validate`, `before_save` for **Save**.
- `validate`, `before_submit` for **Submit**.
- `before_cancel` for **Cancel**
- `before_update_after_submit` for **Update after Submit**

Will also update title_field if set |
| `load_doc_before_save` | `self` | `` | load existing document from db before saving |
| `run_post_save_methods` | `self` | `` | Run standard methods after `INSERT` or `UPDATE`. Standard Methods are:

- `on_update` for **Save**.
- `on_update`, `on_submit` for **Submit**.
- `on_cancel` for **Cancel**
- `update_after_submit` for **Update after Submit** |
| `clear_cache` | `self` | `` |  |
| `reset_seen` | `self` | `` | Clear _seen property and set current user as seen |
| `notify_update` | `self` | `` | Publish realtime that the current document is modified |
| `db_set` | `self, fieldname, value, update_modified, notify, commit` | `` | Set a value in the document object, update the timestamp and update the database.

WARNING: This method does not trigger controller validations and should
be used very carefully.

:param fieldname: fieldname of the property to be updated, or a {"field":"value"} dictionary
:param value: value of the property to be updated
:param update_modified: default True. updates the `modified` and `modified_by` properties
:param notify: default False. run doc.notify_update() to send updates via socketio
:param commit: default False. run frappe.db.commit() |
| `db_get` | `self, fieldname` | `` | get database value for this fieldname |
| `check_no_back_links_exist` | `self` | `` | Check if document links to any active document before Cancel. |
| `save_version` | `self` | `` | Save version info |
| `hook` | `f` | `staticmethod` | Decorator: Make method `hookable` (i.e. extensible by another app).

Note: If each hooked method returns a value (dict), then all returns are
collated in one dict and returned. Ideally, don't return values in hookable
methods, set properties in the document. |
| `is_whitelisted` | `self, method_name` | `` |  |
| `validate_value` | `self, fieldname, condition, val2, doc, raise_exception` | `` | Check that value of fieldname should be 'condition' val2
else throw Exception. |
| `validate_table_has_rows` | `self, parentfield, raise_exception` | `` | Raise exception if Table field is empty. |
| `round_floats_in` | `self, doc, fieldnames` | `` | Round floats for all `Currency`, `Float`, `Percent` fields for the given doc.

:param doc: Document whose numeric properties are to be rounded.
:param fieldnames: [Optional] List of fields to be rounded. |
| `get_url` | `self` | `` | Return Desk URL for this document. |
| `add_comment` | `self, comment_type, text, comment_email, comment_by` | `` | Add a comment to this document.

:param comment_type: e.g. `Comment`. See Communication for more info. |
| `add_seen` | `self, user` | `` | add the given/current user to list of users who have seen this document (_seen) |
| `add_viewed` | `self, user, force, unique_views` | `` | Add a view log for the current document |
| `log_error` | `self, title, message` | `` | Helper function to create an Error Log |
| `get_signature` | `self` | `` | Return signature (hash) for private URL. |
| `get_document_share_key` | `self, expires_on, no_expiry` | `` |  |
| `get_liked_by` | `self` | `` |  |
| `__onload` | `self` | `property` |  |
| `set_onload` | `self, key, value` | `` |  |
| `get_onload` | `self, key` | `` |  |
| `queue_action` | `self, action` | `` | Run an action in background. If the action has an inner function,
like _submit for submit, it will call that instead |
| `lock` | `self, timeout` | `` | Creates a lock file for the given document. If timeout is set,
it will retry every 1 second for acquiring the lock again

:param timeout: Timeout in seconds, default 0 |
| `unlock` | `self` | `` | Delete the lock file for this document |
| `validate_from_to_dates` | `self, from_date_field, to_date_field` | `` | Validate that the value of `from_date_field` is not later than the value of `to_date_field`. |
| `get_assigned_users` | `self` | `` |  |
| `add_tag` | `self, tag` | `` | Add a Tag to this document |
| `remove_tag` | `self, tag` | `` | Remove a Tag to this document |
| `get_tags` | `self` | `` | Return a list of Tags attached to this document |
| `deferred_insert` | `self` | `` | Push the document to redis temporarily and insert later.

WARN: This doesn't guarantee insertion as redis can be restarted
before data is flushed to database. |
| `__str__` | `self` | `` |  |
| `__repr__` | `self` | `` |  |


### `LazyDocument`


**Docstring:**
```
Mixin for Document class that implments lazy loading for child tables.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `load_children_from_db` | `self` | `override` | Override Document which eagerly loads child tables |
| `get` | `self, key, filters, limit, default` | `override` |  |
| `append` | `self, key, value, position` | `override` |  |
| `db_update_all` | `self` | `override` |  |
| `init_child_tables` | `self` | `override` |  |


### `LazyChildTable`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, fieldname, doctype` | `` |  |
| `__get__` | `self, doc, objtype` | `` |  |





## Functions

### `get_doc`
**Arguments:** ``
**Decorators:** `overload`

**Docstring:**
```

```
### `get_doc`
**Arguments:** ``
**Decorators:** `overload`

**Docstring:**
```
Retrieve Single DocType from DB, doctype must be positional argument.
```
### `get_doc`
**Arguments:** ``
**Decorators:** `overload`

**Docstring:**
```
Retrieve DocType from DB, doctype and name must be positional argument.
```
### `get_doc`
**Arguments:** ``
**Decorators:** `overload`

**Docstring:**
```
Initialize document from kwargs.
Not recommended. Use `frappe.new_doc` instead.
```
### `get_doc`
**Arguments:** `documentdict`
**Decorators:** `overload`

**Docstring:**
```
Create document from dict.
Not recommended. Use `frappe.new_doc` instead.
```
### `get_doc`
**Arguments:** ``
**Decorators:** `simple_singledispatch`

**Docstring:**
```
Return a `frappe.model.Document` object.

:param arg1: Document dict or DocType name.
:param arg2: [optional] document name.
:param for_update: [optional] select document for update.

There are multiple ways to call `get_doc`

        # will fetch the latest user object (with child table) from the database
        user = get_doc("User", "test@example.com")

        # create a new object
        user = get_doc({
                "doctype":"User"
                "email_id": "test@example.com",
                "roles: [
                        {"role": "System Manager"}
                ]
        })

        # create new object with keyword arguments
        user = get_doc(doctype='User', email_id='test@example.com')

        # select a document for update
        user = get_doc("User", "test@example.com", for_update=True)
```
### `_basedoc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_str`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_from_mapping_proxy`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_from_dict`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `get_lazy_doc`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `execute_action`
**Arguments:** `__doctype, __name, __action`
**Decorators:** ``

**Docstring:**
```
Execute an action on a document (called by background worker)
```
### `bulk_insert`
**Arguments:** `doctype, documents, ignore_duplicates, chunk_size, commit_chunks`
**Decorators:** ``

**Docstring:**
```
Insert simple Documents objects to database in bulk.

Warning/Info:
        - All documents are inserted without triggering ANY hooks.
        - This function assumes you've done the due dilligence and inserts in similar fashion as db_insert
        - Documents can be any iterable / generator containing Document objects
```
### `_document_values_generator`
**Arguments:** `documents, columns`
**Decorators:** ``

**Docstring:**
```

```
### `unlock_document`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_lazy_controller`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```

