# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/query.py`

## Classes

### `Engine`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_query` | `self, table, fields, filters, order_by, group_by, limit, offset, distinct, for_update, update, into, delete` | `` |  |
| `validate_doctype` | `self` | `` |  |
| `apply_fields` | `self, fields` | `` |  |
| `apply_filters` | `self, filters` | `` |  |
| `apply_list_filters` | `self, filter` | `` |  |
| `apply_dict_filters` | `self, filters` | `` |  |
| `_apply_filter` | `self, field, value, operator, doctype` | `` | Applies a simple filter condition to the query. |
| `_build_criterion_for_simple_filter` | `self, field, value, operator, doctype` | `` | Builds a pypika Criterion object for a simple filter condition. |
| `_parse_nested_filters` | `self, nested_list` | `` | Parses a nested filter list like [cond1, 'and', cond2, 'or', cond3, ...] into a pypika Criterion. |
| `_condition_to_criterion` | `self, condition` | `` | Converts a single condition (simple filter list or nested list) into a pypika Criterion. |
| `_validate_and_prepare_filter_field` | `self, field, doctype` | `` | Validate field name for filters and return a pypika Field object. Handles dynamic fields. |
| `_check_field_permission` | `self, doctype, fieldname, parent_doctype` | `` | Check if the user has permission to access the given field |
| `parse_string_field` | `self, field` | `` | Parses a field string into a pypika Field object.

Handles:
- *
- simple_field
- `quoted_field`
- tabDocType.simple_field
- `tabDocType`.`quoted_field`
- `tabTable Name`.`quoted_field`
- Aliases for all above formats (e.g., field as alias) |
| `parse_fields` | `self, fields` | `` |  |
| `_parse_single_field_item` | `self, field` | `` | Parses a single item from the fields list/tuple. Assumes comma-separated strings have already been split. |
| `apply_group_by` | `self, group_by` | `` |  |
| `apply_order_by` | `self, order_by` | `` |  |
| `_validate_and_parse_field_for_clause` | `self, field_name, clause_name` | `` | Common helper to validate and parse field names for GROUP BY and ORDER BY clauses.

Args:
        field_name: The field name to validate and parse
        clause_name: Name of the SQL clause (for error messages) - 'Group By' or 'Order By'

Returns:
        Parsed Field object ready for use in pypika query |
| `_validate_group_by` | `self, group_by` | `` | Validate the group_by string argument, apply joins for dynamic fields, and return parsed Field objects. |
| `_validate_order_by` | `self, order_by` | `` | Validate the order_by string argument, apply joins for dynamic fields, and return parsed Field objects with directions. |
| `check_read_permission` | `self` | `` | Check if user has read permission on the doctype |
| `apply_field_permissions` | `self` | `` | Filter the list of fields based on permlevel. |
| `get_user_permission_conditions` | `self, role_permissions` | `` | Build conditions for user permissions and return tuple of (conditions, fetch_shared_docs) |
| `get_doctype_link_fields` | `self` | `` |  |
| `add_permission_conditions` | `self` | `` |  |
| `get_permission_query_conditions` | `self` | `` | Add permission query conditions from hooks and server scripts |
| `get_permission_type` | `self, doctype` | `` | Get permission type (select/read) based on user permissions |
| `requires_owner_constraint` | `self, role_permissions` | `` | Return True if "select" or "read" isn't available without being creator. |


### `Permission`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `check_permissions` | `cls, query` | `classmethod` |  |
| `get_tables_from_query` | `query` | `staticmethod` |  |


### `DynamicTableField`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, fieldname, parent_doctype, alias` | `` |  |
| `__str__` | `self` | `` |  |
| `parse` | `field, doctype, allow_tab_notation` | `staticmethod` |  |
| `apply_select` | `self, query` | `` |  |


### `ChildTableField`
**Inherits:** `DynamicTableField`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, fieldname, parent_doctype, parent_fieldname, alias` | `` |  |
| `apply_select` | `self, query` | `` |  |
| `apply_join` | `self, query` | `` |  |


### `LinkTableField`
**Inherits:** `DynamicTableField`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, fieldname, parent_doctype, link_fieldname, alias` | `` |  |
| `apply_select` | `self, query` | `` |  |
| `apply_join` | `self, query` | `` |  |


### `ChildQuery`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, fieldname, fields, parent_doctype` | `` |  |
| `get_query` | `self, parent_names` | `` |  |


### `RawCriterion`
**Inherits:** `Term`


**Docstring:**
```
A class to represent raw SQL string as a criterion.

Allows using raw SQL strings in pypika queries:
        frappe.qb.from_("DocType").where(RawCriterion("name like 'a%'"))
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, sql_string` | `` |  |
| `get_sql` | `self` | `` |  |
| `__and__` | `self, other` | `` |  |
| `__or__` | `self, other` | `` |  |
| `__invert__` | `self` | `` |  |


### `CombinedRawCriterion`
**Inherits:** `RawCriterion`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, left, right, operator` | `` |  |
| `get_sql` | `self` | `` |  |


### `SQLFunctionParser`


**Docstring:**
```
Parser for SQL function dictionaries in query builder fields.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, engine` | `` |  |
| `is_function_dict` | `self, field_dict` | `` | Check if a dictionary represents a SQL function definition. |
| `parse_function` | `self, function_dict` | `` | Parse a SQL function dictionary into a pypika function call. |
| `_parse_and_validate_argument` | `self, arg` | `` | Parse and validate a single function argument against SQL injection. |
| `_validate_string_argument` | `self, arg` | `` | Validate string arguments to prevent SQL injection. |
| `_is_string_literal` | `self, arg` | `` | Check if argument is a properly quoted string literal. |
| `_validate_string_literal` | `self, literal` | `` | Validate a string literal for SQL injection attacks. |
| `_is_valid_field_name` | `self, name` | `` | Check if a string is a valid field name. |
| `_validate_alias` | `self, alias` | `` | Validate alias name for SQL injection. |
| `_validate_function_field_arg` | `self, field_name` | `` | Validate a field name used as a function argument. |





## Functions

### `get_nested_set_hierarchy_result`
**Arguments:** `doctype, name, hierarchy`
**Decorators:** ``

**Docstring:**
```
Get matching nodes based on operator.
```
### `_validate_select_field`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```
Validate a field string intended for use in a SELECT clause.
```
### `_sanitize_field`
**Arguments:** `field, is_mariadb`
**Decorators:** ``

**Docstring:**
```
Validate and sanitize a field string for SELECT clause by stripping comments.
```

