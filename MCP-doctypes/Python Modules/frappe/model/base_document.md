# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/base_document.py`

## Classes

### `BaseDocument`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, d` | `` |  |
| `__json__` | `self` | `` |  |
| `meta` | `self` | `cached_property` |  |
| `permitted_fieldnames` | `self` | `cached_property` |  |
| `_weakref` | `self` | `cached_property` |  |
| `__getstate__` | `self` | `` | Return a copy of `__dict__` excluding unpicklable values like `meta`.

Called when pickling.
More info: https://docs.python.org/3/library/pickle.html#handling-stateful-objects |
| `remove_unpicklable_values` | `self, state` | `` | Remove unpicklable values before pickling |
| `update` | `self, d` | `` | Update multiple fields of a doctype using a dictionary of key-value pairs.

Example:
        doc.update({
                "user": "admin",
                "balance": 42000
        })

Developer Note: Logic in the set method is re-implemented here for perf |
| `update_if_missing` | `self, d` | `` | Set default values for fields without existing values |
| `get_db_value` | `self, key` | `` |  |
| `get` | `self, key, filters, limit, default` | `` |  |
| `getone` | `self, key, filters` | `` |  |
| `set` | `self, key, value, as_value` | `` |  |
| `delete_key` | `self, key` | `` |  |
| `append` | `self, key, value, position` | `` | Append an item to a child table.

Example:
        doc.append("childtable", {
                "child_table_field": "value",
                "child_table_int_field": 0,
                ...
        }) |
| `parent_doc` | `self` | `property` |  |
| `parent_doc` | `self, value` | `` |  |
| `parent_doc` | `self` | `` |  |
| `extend` | `self, key, value` | `` |  |
| `remove` | `self, doc` | `` | Usage: from the parent doc, pass the child table doc to remove that child doc from the
child table, thus removing it from the parent doc |
| `_init_child` | `self, value, key` | `` |  |
| `_table_fieldnames` | `self` | `cached_property` |  |
| `_get_table_fields` | `self` | `` | To get table fields during Document init
Meta.get_table_fields goes into recursion for special doctypes |
| `get_valid_dict` | `self, sanitize, convert_dates_to_str, ignore_nulls, ignore_virtual` | `` |  |
| `init_child_tables` | `self` | `` | This is needed so that one can loop over child table properties
without worrying about whether or not they have values |
| `init_valid_columns` | `self` | `` |  |
| `get_valid_columns` | `self` | `` |  |
| `is_new` | `self` | `` |  |
| `docstatus` | `self` | `property` |  |
| `docstatus` | `self, value` | `` |  |
| `as_dict` | `self, no_nulls, no_default_fields, convert_dates_to_str, no_child_table_fields, no_private_properties` | `` |  |
| `as_json` | `self` | `` |  |
| `get_table_field_doctype` | `self, fieldname` | `` |  |
| `get_parentfield_of_doctype` | `self, doctype` | `` |  |
| `db_insert` | `self, ignore_if_duplicate` | `` | INSERT the document (with valid columns) in the database.

args:
        ignore_if_duplicate: ignore primary key collision
                                        at database level (postgres)
                                        in python (mariadb) |
| `db_update` | `self` | `` |  |
| `db_update_all` | `self` | `` | Raw update parent + children
DOES NOT VALIDATE AND CALL TRIGGERS |
| `show_unique_validation_message` | `self, e` | `` |  |
| `get_field_name_by_key_name` | `self, key_name` | `` | MariaDB stores a mapping between `key_name` and `column_name`.
Return the `column_name` associated with the `key_name` passed.

Args:
        key_name (str): The name of the database index.

Raises:
        IndexError: If the key is not found in the table.

Return:
        str: The column name associated with the key. |
| `get_label_from_fieldname` | `self, fieldname` | `` | Return the associated label for fieldname.

Args:
        fieldname (str): The fieldname in the DocType to use to pull the label.

Return:
        str: The label associated with the fieldname, if found, otherwise `None`. |
| `update_modified` | `self` | `` | Update modified timestamp |
| `_fix_numeric_types` | `self` | `` |  |
| `_get_missing_mandatory_fields` | `self` | `` | Get mandatory fields that do not have any values |
| `get_invalid_links` | `self, is_submittable` | `` | Return list of invalid links and also update fetch values if not set. |
| `set_fetch_from_value` | `self, doctype, df, values` | `` |  |
| `_validate_selects` | `self` | `` |  |
| `_validate_data_fields` | `self` | `` |  |
| `_validate_constants` | `self` | `` |  |
| `_validate_length` | `self` | `` |  |
| `_validate_code_fields` | `self` | `` |  |
| `_sync_autoname_field` | `self` | `` | Keep autoname field in sync with `name` |
| `throw_length_exceeded_error` | `self, df, max_length, value` | `` |  |
| `_validate_update_after_submit` | `self` | `` |  |
| `_sanitize_content` | `self` | `` | Sanitize HTML and Email in field values. Used to prevent XSS.

- Ignore if 'Ignore XSS Filter' is checked or fieldtype is 'Code' |
| `_save_passwords` | `self` | `` | Save password field values in __Auth table |
| `get_password` | `self, fieldname, raise_exception` | `` |  |
| `is_dummy_password` | `self, pwd` | `` |  |
| `precision` | `self, fieldname, parentfield` | `` | Return float precision for a particular field (or get global default).

:param fieldname: Fieldname for which precision is required.
:param parentfield: If fieldname is in child table. |
| `get_formatted` | `self, fieldname, doc, currency, absolute_value, translated, format` | `` |  |
| `is_print_hide` | `self, fieldname, df, for_print` | `` | Return True if fieldname is to be hidden for print.

Print Hide can be set via the Print Format Builder or in the controller as a list
of hidden fields. Example

        class MyDoc(Document):
                def __setup__(self):
                        self.print_hide = ["field1", "field2"]

:param fieldname: Fieldname to be checked if hidden. |
| `in_format_data` | `self, fieldname` | `` | Return True if shown via Print Format::`format_data` property.

Called from within standard print format. |
| `reset_values_if_no_permlevel_access` | `self, has_access_to, high_permlevel_fields` | `` | If the user does not have permissions at permlevel > 0, then reset the values to original / default |
| `get_value` | `self, fieldname` | `` |  |
| `cast` | `self, value, df` | `` |  |
| `_extract_images_from_text_editor` | `self` | `` |  |





## Functions

### `get_controller`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return the locally cached **class** object of the given DocType.

For `custom` type, return `frappe.model.document.Document`.

:param doctype: DocType name as string.
```
### `import_controller`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `_filter`
**Arguments:** `data, filters, limit`
**Decorators:** ``

**Docstring:**
```
pass filters as:
{"key": "val", "key": ["!=", "val"],
"key": ["in", "val"], "key": ["not in", "val"], "key": "^val",
"key" : True (exists), "key": False (does not exist) }
```

