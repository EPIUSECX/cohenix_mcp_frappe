# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_query.py`

## Classes

### `TestQuery`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_multiple_tables_in_filters` | `self` | `` |  |
| `test_string_fields` | `self` | `` |  |
| `test_qb_fields` | `self` | `` |  |
| `test_field_validation_select` | `self` | `` | Test validation for fields in SELECT clause. |
| `test_field_validation_filters` | `self` | `` | Test validation for fields used in filters (WHERE clause). |
| `test_field_validation_group_by` | `self` | `` | Test validation for fields in GROUP BY clause. |
| `test_field_validation_order_by` | `self` | `` | Test validation for fields in ORDER BY clause. |
| `test_aliasing` | `self` | `` |  |
| `test_filters` | `self` | `` |  |
| `test_nested_filters` | `self` | `` | Test nested filter conditions with AND/OR logic. |
| `test_invalid_nested_filters` | `self` | `` | Test invalid formats for nested filters. |
| `test_implicit_join_query` | `self` | `` |  |
| `test_nestedset` | `self` | `` |  |
| `test_child_field_syntax` | `self` | `` |  |
| `test_build_match_conditions` | `self` | `` |  |
| `test_ignore_permissions_for_query` | `self` | `` |  |
| `test_permlevel_fields` | `self` | `` | Test permission level check when querying fields |
| `test_child_table_access_with_select_permission` | `self` | `` | Test that child table fields are inaccessible if user only has select perm on parent. |
| `test_nested_permission` | `self` | `` | Test permission on nested doctypes |
| `test_is_set_is_not_set` | `self` | `` | Test is set and is not set filters |
| `test_permission_query_condition` | `self` | `` | Test permission query condition being applied from hooks and server script |
| `test_link_field_target_permission` | `self` | `` | Test that accessing link_field.target_field respects target field's permlevel. |
| `test_filter_direct_field_permission` | `self` | `` | Test that filtering is only allowed on permitted direct fields. |
| `test_filter_linked_field_permission` | `self` | `` | Test that filtering is only allowed on permitted linked fields. |
| `test_dynamic_fields_in_group_by` | `self` | `` | Test dynamic field support in GROUP BY clause. |
| `test_dynamic_fields_in_order_by` | `self` | `` | Test dynamic field support in ORDER BY clause. |
| `test_multiple_dynamic_fields_group_order` | `self` | `` | Test multiple dynamic fields in GROUP BY and ORDER BY. |
| `test_group_by_order_by_permission_checks` | `self` | `` | Test permission checks for dynamic fields in GROUP BY and ORDER BY. |
| `test_child_table_group_by_order_by_permissions` | `self` | `` | Test permission checks for child table fields in GROUP BY and ORDER BY. |
| `test_group_by_order_by_validation_errors` | `self` | `` | Test validation errors for invalid GROUP BY and ORDER BY fields. |
| `test_backtick_rejection_group_order` | `self` | `` | Test that backticks are properly rejected in GROUP BY and ORDER BY. |
| `test_sql_functions_in_fields` | `self` | `` | Test SQL function support in fields with various syntaxes. |





## Functions

### `create_tree_docs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_permission_hook_condition`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

