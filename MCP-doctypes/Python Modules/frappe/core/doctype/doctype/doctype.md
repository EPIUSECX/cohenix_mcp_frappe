# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/doctype/doctype.py`

## Classes

### `InvalidFieldNameError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UniqueFieldnameError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `IllegalMandatoryError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DoctypeLinkError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WrongOptionsDoctypeLinkError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `HiddenAndMandatoryWithoutDefaultError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NonUniqueError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CannotIndexedError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CannotCreateStandardDoctypeError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocType`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` | Validate DocType before saving.

- Check if developer mode is set.
- Validate series
- Check fieldnames (duplication etc)
- Clear permission table for child tables
- Add `amended_from` and `amended_by` if Amendable
- Add custom field `auto_repeat` if Repeatable
- Check if links point to valid fieldnames |
| `validate_field_name_conflicts` | `self` | `` | Check if field names dont conflict with controller properties and methods |
| `set_defaults_for_single_and_table` | `self` | `` |  |
| `set_default_in_list_view` | `self` | `` | Set default in-list-view for first 4 mandatory fields |
| `set_default_translatable` | `self` | `` | Ensure that non-translatable never will be translatable |
| `check_indexing_for_dashboard_links` | `self` | `` | Enable indexing for outgoing links used in dashboard |
| `check_developer_mode` | `self` | `` | Throw exception if not developer mode or via patch |
| `setup_fields_to_fetch` | `self` | `` | Setup query to update values for newly set fetch values |
| `update_fields_to_fetch` | `self` | `` | Update fetch values based on queries setup |
| `validate_document_type` | `self` | `` |  |
| `validate_website` | `self` | `` | Ensure that website generator has field 'route' |
| `validate_virtual_doctype_methods` | `self` | `` |  |
| `ensure_minimum_max_attachment_limit` | `self` | `` | Ensure that max_attachments is *at least* bigger than number of attach fields. |
| `change_modified_of_parent` | `self` | `` | Change the timestamp of parent DocType if the current one is a child to clear caches. |
| `scrub_field_names` | `self` | `` | Sluggify fieldnames if not set from Label. |
| `get_permission_log_options` | `self, event` | `` |  |
| `on_update` | `self` | `` | Update database schema, make controller templates if `custom` is not set and clear cache. |
| `sync_doctype_layouts` | `self` | `` | Sync Doctype Layout |
| `setup_autoincrement_and_sequence` | `self` | `` | Changes name type and makes sequence on change (if required) |
| `sync_global_search` | `self` | `` | If global search settings are changed, rebuild search properties for this table |
| `set_base_class_for_controller` | `self` | `` | If DocType.has_web_view has been changed, updates the controller class and import
from `WebsiteGenertor` to `Document` or viceversa |
| `run_module_method` | `self, method` | `` |  |
| `before_rename` | `self, old, new, merge` | `` | Throw exception if merge. DocTypes cannot be merged. |
| `after_rename` | `self, old, new, merge` | `` | Change table name using `RENAME TABLE` if table exists. Or update
`doctype` property for Single type. |
| `after_delete` | `self` | `` |  |
| `rename_files_and_folders` | `self, old, new` | `` |  |
| `rename_inside_controller` | `self, new, old, new_path` | `` |  |
| `before_reload` | `self` | `` | Preserve naming series changes in Property Setter. |
| `preserve_naming_series_options_in_property_setter` | `self` | `` | Preserve naming_series as property setter if it does not exist |
| `before_export` | `self, docdict` | `` |  |
| `prepare_for_import` | `docdict` | `staticmethod` |  |
| `export_doc` | `self` | `` | Export to standard folder `[module]/doctype/[name]/[name].json`. |
| `make_controller_template` | `self` | `` | Make boilerplate controller template. |
| `export_types_to_controller` | `self` | `` |  |
| `make_amendable` | `self` | `` | If is_submittable is set, add amended_from docfields. |
| `make_repeatable` | `self` | `` | If allow_auto_repeat is set, add auto_repeat custom field. |
| `validate_nestedset` | `self` | `` |  |
| `add_nestedset_fields` | `self` | `` | If is_tree is set, add parent_field, lft, rgt, is_group fields. |
| `validate_child_table` | `self` | `` |  |
| `add_child_table_fields` | `self` | `` |  |
| `get_max_idx` | `self` | `` | Return the highest `idx`. |
| `validate_name` | `self, name` | `` |  |
| `check_pending_migration` | `self` | `` | Checks if all migrations are applied on doctype. |





## Functions

### `validate_series`
**Arguments:** `dt, autoname, name`
**Decorators:** ``

**Docstring:**
```
Validate if `autoname` property is correctly set.
```
### `validate_empty_name`
**Arguments:** `dt, autoname`
**Decorators:** ``

**Docstring:**
```

```
### `validate_autoincrement_autoname`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```
Checks if can doctype can change to/from autoincrement autoname
```
### `change_name_column_type`
**Arguments:** `doctype_name, type`
**Decorators:** ``

**Docstring:**
```
Changes name column type
```
### `validate_links_table_fieldnames`
**Arguments:** `meta`
**Decorators:** ``

**Docstring:**
```
Validate fieldnames in Links table
```
### `_test_connection_query`
**Arguments:** `doctype, field, idx`
**Decorators:** ``

**Docstring:**
```
Make sure that connection can be queried.

This function executes query similar to one that would be executed for
finding count on dashboard and hence validates if fieldname/doctype are
correct.
```
### `validate_fields_for_doctype`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `validate_fields`
**Arguments:** `meta`
**Decorators:** ``

**Docstring:**
```
Validate doctype fields. Checks
1. There are no illegal characters in fieldnames
2. If fieldnames are unique.
3. Validate column length.
4. Fields that do have database columns are not mandatory.
5. `Link` and `Table` options are valid.
6. **Hidden** and **Mandatory** are not set simultaneously.
7. `Check` type field has default as 0 or 1.
8. `Dynamic Links` are correctly defined.
9. Precision is set in numeric fields and is between 1 & 6.
10. Fold is not at the end (if set).
11. `search_fields` are valid.
12. `title_field` and title field pattern are valid.
13. `unique` check is only valid for Data, Link and Read Only fieldtypes.
14. `unique` cannot be checked if there exist non-unique values.

:param meta: `frappe.model.meta.Meta` object to check.
```
### `get_fields_not_allowed_in_list_view`
**Arguments:** `meta`
**Decorators:** ``

**Docstring:**
```

```
### `validate_permissions_for_doctype`
**Arguments:** `doctype, for_remove, alert`
**Decorators:** ``

**Docstring:**
```
Validates if permissions are set correctly.
```
### `clear_permissions_cache`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `validate_permissions`
**Arguments:** `doctype, for_remove, alert`
**Decorators:** ``

**Docstring:**
```

```
### `make_module_and_roles`
**Arguments:** `doc, perm_fieldname`
**Decorators:** ``

**Docstring:**
```
Make `Module Def` and `Role` records if already not made. Called while installing.
```
### `check_fieldname_conflicts`
**Arguments:** `docfield`
**Decorators:** ``

**Docstring:**
```
Checks if fieldname conflicts with methods or properties
```
### `clear_linked_doctype_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_email_append_to`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_field`
**Arguments:** `doc, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `get_row_size_utilization`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Get row size utilization in percentage
```

