# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/meta.py`

## Classes

### `Meta`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype` | `` |  |
| `load_from_db` | `self` | `` |  |
| `process` | `self` | `` |  |
| `as_dict` | `self, no_nulls` | `` |  |
| `get_link_fields` | `self` | `` |  |
| `get_data_fields` | `self` | `` |  |
| `get_phone_fields` | `self` | `` |  |
| `get_dynamic_link_fields` | `self` | `` |  |
| `_dynamic_link_fields` | `self` | `cached_property` |  |
| `get_select_fields` | `self` | `` |  |
| `get_image_fields` | `self` | `` |  |
| `get_code_fields` | `self` | `` |  |
| `get_set_only_once_fields` | `self` | `` | Return fields with `set_only_once` set |
| `_set_only_once_fields` | `self` | `cached_property` |  |
| `get_table_fields` | `self` | `` |  |
| `get_global_search_fields` | `self` | `` | Return list of fields with `in_global_search` set and `name` if set. |
| `get_valid_columns` | `self` | `` |  |
| `_valid_columns` | `self` | `cached_property` |  |
| `get_valid_fields` | `self` | `` |  |
| `_valid_fields` | `self` | `cached_property` |  |
| `get_field` | `self, fieldname` | `` | Return docfield from meta. |
| `has_field` | `self, fieldname` | `` | Return True if fieldname exists. |
| `get_label` | `self, fieldname` | `` | Return label of the given fieldname. |
| `get_options` | `self, fieldname` | `` |  |
| `get_link_doctype` | `self, fieldname` | `` |  |
| `get_search_fields` | `self` | `` |  |
| `get_fields_to_fetch` | `self, link_fieldname` | `` | Return a list of docfield objects for fields whose values
are to be fetched and updated for a particular link field.

These fields are of type Data, Link, Text, Readonly and their
fetch_from property is set as `link_fieldname`.`source_fieldname` |
| `get_list_fields` | `self` | `` |  |
| `get_custom_fields` | `self` | `` |  |
| `get_title_field` | `self` | `` | Return the title field of this doctype,
explict via `title_field`, or `title` or `name` |
| `get_translatable_fields` | `self` | `` | Return all fields that are translation enabled |
| `is_translatable` | `self, fieldname` | `` | Return true of false given a field |
| `get_workflow` | `self` | `` |  |
| `get_naming_series_options` | `self` | `` | Get list naming series options. |
| `add_custom_fields` | `self` | `` |  |
| `apply_property_setters` | `self` | `` | Property Setters are set via Customize Form. They override standard properties
of the doctype or its child properties like fields, links etc. This method
applies the customized properties over the standard meta object |
| `add_custom_links_and_actions` | `self` | `` |  |
| `check_if_large_table` | `self` | `` | Apply some heuristics to detect large tables.

UI code can use this information to adapt accordingly. |
| `init_field_caches` | `self` | `` |  |
| `sort_fields` | `self` | `` | Sort fields on the basis of following rules (priority descending):
- `field_order` property setter
- `insert_after` computed based on default order for standard fields
- `insert_after` property for custom fields |
| `_update_fields_based_on_order` | `self, field_order` | `` |  |
| `set_custom_permissions` | `self` | `` | Reset `permissions` with Custom DocPerm if exists |
| `get_fieldnames_with_value` | `self, with_field_meta, with_virtual_fields` | `` |  |
| `get_fields_to_check_permissions` | `self, user_permission_doctypes` | `` |  |
| `get_high_permlevel_fields` | `self` | `` | Build list of fields with high perm level and all the higher perm levels defined. |
| `high_permlevel_fields` | `self` | `cached_property` |  |
| `get_permitted_fieldnames` | `self, parenttype` | `` | Build list of `fieldname` with read perm level and all the higher perm levels defined.

Note: If permissions are not defined for DocType, return all the fields with value. |
| `get_permlevel_access` | `self, permission_type, parenttype` | `` |  |
| `get_permissions` | `self, parenttype` | `` |  |
| `get_dashboard_data` | `self` | `` | Return dashboard setup related to this doctype.

This method will return the `data` property in the `[doctype]_dashboard.py`
file in the doctype's folder, along with any overrides or extensions
implemented in other Frappe applications via hooks. |
| `add_doctype_links` | `self, data` | `` | add `links` child table in standard link dashboard format |
| `get_row_template` | `self` | `` |  |
| `get_list_template` | `self` | `` |  |
| `get_web_template` | `self, suffix` | `` | Return the relative path of the row template for this doctype. |
| `is_nested_set` | `self` | `` |  |





## Functions

### `get_meta`
**Arguments:** `doctype, cached`
**Decorators:** ``

**Docstring:**
```
Get metadata for a doctype.

Args:
    doctype: The doctype as a string object.
    cached: Whether to use cached metadata (default: True).

Returns:
    Meta object for the given doctype.
```
### `clear_meta_cache`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `load_meta`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_table_columns`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `load_doctype_from_file`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_parent_dt`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `set_fieldname`
**Arguments:** `field_id, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `get_field_currency`
**Arguments:** `df, doc`
**Decorators:** ``

**Docstring:**
```
get currency based on DocField options and fieldvalue in doc
```
### `get_field_precision`
**Arguments:** `df, doc, currency`
**Decorators:** ``

**Docstring:**
```
get precision based on DocField options and fieldvalue in doc
```
### `get_default_df`
**Arguments:** `fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `trim_tables`
**Arguments:** `doctype, dry_run, quiet`
**Decorators:** ``

**Docstring:**
```
Removes database fields that don't exist in the doctype (json or custom field). This may be needed
as maintenance since removing a field in a DocType doesn't automatically
delete the db field.
```
### `trim_table`
**Arguments:** `doctype, dry_run`
**Decorators:** ``

**Docstring:**
```

```
### `_update_field_order_based_on_insert_after`
**Arguments:** `field_order, insert_after_map`
**Decorators:** ``

**Docstring:**
```
Update the field order based on insert_after_map
```
### `_serialize`
**Arguments:** `doc, no_nulls`
**Decorators:** ``

**Docstring:**
```

```

