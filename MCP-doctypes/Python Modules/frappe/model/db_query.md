# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/db_query.py`

## Classes

### `DatabaseQuery`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, user` | `` |  |
| `doctype_meta` | `self` | `cached_property` |  |
| `get_meta` | `self, doctype` | `` |  |
| `query_tables` | `self` | `property` |  |
| `execute` | `self, fields, filters, or_filters, docstatus, group_by, order_by, limit_start, limit_page_length, as_list, with_childnames, debug, ignore_permissions, user, with_comment_count, join, distinct, start, page_length, limit, ignore_ifnull, save_user_settings, save_user_settings_fields, update, user_settings, reference_doctype, run, strict, pluck, ignore_ddl` | `` |  |
| `build_and_run` | `self` | `` |  |
| `prepare_args` | `self` | `` |  |
| `prepare_select_args` | `self, args` | `` |  |
| `parse_args` | `self` | `` | Convert fields and filters from strings to list, dicts. |
| `sanitize_fields` | `self` | `` | regex : ^.*[,();].*
purpose : The regex will look for malicious patterns like `,`, '(', ')', '@', ;' in each
                field which may leads to sql injection.
example :
        field = "`DocType`.`issingle`, version()"
As field contains `,` and mysql function `version()`, with the help of regex
the system will filter out this field. |
| `extract_tables` | `self` | `` | extract tables from fields |
| `append_table` | `self, table_name` | `` |  |
| `append_link_table` | `self, doctype, fieldname` | `` |  |
| `check_read_permission` | `self, doctype, parent_doctype` | `` |  |
| `_set_permission_map` | `self, doctype, parent_doctype` | `` |  |
| `set_field_tables` | `self` | `` | If there are more than one table, the fieldname must not be ambiguous.
If the fieldname is not explicitly mentioned, set the default table |
| `cast_name_fields` | `self` | `` |  |
| `get_table_columns` | `self` | `` |  |
| `set_optional_columns` | `self` | `` | Removes optional columns like `_user_tags`, `_comments` etc. if not in table |
| `build_conditions` | `self` | `` |  |
| `build_filter_conditions` | `self, filters, conditions, ignore_permissions` | `` | build conditions from user filters |
| `remove_field` | `self, idx` | `` |  |
| `apply_fieldlevel_read_permissions` | `self` | `` | Apply fieldlevel read permissions to the query

Note: Does not apply to `frappe.model.core_doctype_list`

Remove fields that user is not allowed to read. If `fields=["*"]` is passed, only permitted fields will
be returned.

Example:
        - User has read permission only on `title` for DocType `Note`
        - Query: fields=["*"]
        - Result: fields=["title", ...] // will also include Frappe's meta field like `name`, `owner`, etc. |
| `prepare_filter_condition` | `self, ft` | `` | Return a filter condition in the format:

ifnull(`tabDocType`.`fieldname`, fallback) operator "value" |
| `build_match_conditions` | `self, as_condition` | `` | add match conditions if applicable |
| `get_share_condition` | `self` | `` |  |
| `add_user_permissions` | `self, user_permissions` | `` |  |
| `get_permission_query_conditions` | `self` | `` |  |
| `set_order_by` | `self, args` | `` |  |
| `validate_order_by_and_group_by` | `self, parameters` | `` | Check order by, group by so that atleast one column is selected and does not have subquery |
| `add_limit` | `self` | `` |  |
| `add_comment_count` | `self, result` | `` |  |
| `update_user_settings` | `self` | `` |  |





## Functions

### `cast_name`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
Casts name field to varchar for postgres

Handles majorly 4 cases:
1. locate
2. strpos
3. ifnull
4. coalesce

Uses regex substitution.

Example:
input - "ifnull(`tabBlog Post`.`name`, '')=''"
output - "ifnull(cast(`tabBlog Post`.`name` as varchar), '')=''" 
```
### `check_parent_permission`
**Arguments:** `parent, child_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_order_by`
**Arguments:** `doctype, meta`
**Decorators:** ``

**Docstring:**
```

```
### `has_any_user_permission_for_doctype`
**Arguments:** `doctype, user, applicable_for`
**Decorators:** ``

**Docstring:**
```

```
### `get_between_date_filter`
**Arguments:** `value, df`
**Decorators:** ``

**Docstring:**
```
Handle datetime filter bounds for between filter values.

If date is passed but fieldtype is datetime then
        from part is converted to start of day and to part is converted to end of day.
If any of filter part (to or from) are missing then:
        start or end of current day is assumed as fallback.
If fieldtypes match with filter values then:
        no change is applied.
```
### `_convert_type_for_between_filters`
**Arguments:** `value, set_time`
**Decorators:** ``

**Docstring:**
```

```
### `get_additional_filter_field`
**Arguments:** `additional_filters_config, f, value`
**Decorators:** ``

**Docstring:**
```

```
### `get_date_range`
**Arguments:** `operator, value`
**Decorators:** ``

**Docstring:**
```

```
### `requires_owner_constraint`
**Arguments:** `role_permissions`
**Decorators:** ``

**Docstring:**
```
Return True if "select" or "read" isn't available without being creator.
```
### `wrap_grave_quotes`
**Arguments:** `table`
**Decorators:** ``

**Docstring:**
```

```
### `is_plain_field`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```

```
### `in_function`
**Arguments:** `substr, field`
**Decorators:** ``

**Docstring:**
```

```
### `strip_alias`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```

```

