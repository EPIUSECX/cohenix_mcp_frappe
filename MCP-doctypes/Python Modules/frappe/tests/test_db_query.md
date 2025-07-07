# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_db_query.py`

## Classes

### `TestDBQuery`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_basic` | `self` | `` |  |
| `test_extract_tables` | `self` | `` |  |
| `test_child_table_field_syntax` | `self` | `` |  |
| `test_child_table_join` | `self` | `` |  |
| `test_link_field_syntax` | `self` | `` |  |
| `test_build_match_conditions` | `self` | `` |  |
| `test_fields` | `self` | `` |  |
| `test_filters_1` | `self` | `` |  |
| `test_filters_2` | `self` | `` |  |
| `test_filters_3` | `self` | `` |  |
| `test_filters_4` | `self` | `` |  |
| `test_in_not_in_filters` | `self` | `` |  |
| `test_string_as_field` | `self` | `` |  |
| `test_none_filter` | `self` | `` |  |
| `test_or_filters` | `self` | `` |  |
| `test_between_filters` | `self` | `` | test case to check between filter for date fields |
| `test_between_filters_date_bounds` | `self` | `` |  |
| `test_ignore_permissions_for_get_filters_cond` | `self` | `` |  |
| `test_query_fields_sanitizer` | `self` | `` |  |
| `test_nested_permission` | `self` | `` |  |
| `test_filter_sanitizer` | `self` | `` |  |
| `test_order_by_group_by_sanitizer` | `self` | `` |  |
| `test_of_not_of_descendant_ancestors` | `self` | `` |  |
| `test_is_set_is_not_set` | `self` | `` |  |
| `test_set_field_tables` | `self` | `` |  |
| `test_virtual_field_get_list` | `self` | `` |  |
| `test_pluck_name` | `self` | `` |  |
| `test_pluck_any_field` | `self` | `` |  |
| `test_prepare_select_args` | `self` | `` |  |
| `test_column_comparison` | `self` | `` | Test DatabaseQuery.execute to test column comparison |
| `test_permlevel_fields` | `self` | `` |  |
| `test_cast_name` | `self` | `` |  |
| `test_fieldname_starting_with_int` | `self` | `` |  |
| `test_permission_query_condition` | `self` | `` |  |
| `test_virtual_doctype` | `self` | `` | Test that virtual doctypes can be queried using get_all |
| `test_coalesce_with_in_ops` | `self` | `` |  |
| `test_coalesce_with_datetime_ops` | `self` | `` |  |
| `test_ambiguous_linked_tables` | `self` | `` |  |
| `test_select_star_expansion` | `self` | `` |  |
| `test_ifnull_none` | `self` | `` |  |
| `test_ifnull_fallback_types` | `self` | `` |  |


### `TestReportView`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_count` | `self` | `` |  |
| `test_reportview_get` | `self` | `` |  |
| `test_reportview_get_aggregation` | `self` | `` |  |
| `test_reportview_get_permlevel_system_users` | `self` | `` |  |
| `test_reportview_get_admin` | `self` | `` |  |
| `test_db_filter_not_set` | `self` | `` | Test if the 'not set' filter always translates correctly with/without qb under the hood. |





## Functions

### `setup_test_user`
**Arguments:** `set_user`
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `setup_patched_blog_post`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `add_child_table_to_blog_post`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_event`
**Arguments:** `subject, starts_on`
**Decorators:** ``

**Docstring:**
```
create a test event
```
### `create_nested_doctype`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_nested_doctype_records`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Create a structure like:
- Root
        - Level 1 A
                - Level 2 A
                        - Level 3 A
        - Level 1 B
                - Level 2 B
```

