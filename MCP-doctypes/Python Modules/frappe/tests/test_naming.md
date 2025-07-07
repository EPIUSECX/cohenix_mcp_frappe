# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_naming.py`

## Classes

### `TestNaming`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_append_number_if_name_exists` | `self` | `` | Append number to name based on existing values
if Bottle exists
        Bottle -> Bottle-1
if Bottle-1 exists
        Bottle -> Bottle-2 |
| `test_field_autoname_name_sync` | `self` | `` |  |
| `test_child_table_naming` | `self` | `` |  |
| `test_format_autoname` | `self` | `` | Test if braced params are replaced in format autoname |
| `test_format_autoname_for_datetime_field` | `self` | `` | Test if datetime, date and time objects get converted to strings for naming. |
| `test_format_autoname_for_consecutive_week_number` | `self` | `` | Test if braced params are replaced for consecutive week number in format autoname |
| `test_revert_series` | `self` | `` |  |
| `test_naming_for_cancelled_and_amended_doc` | `self` | `` |  |
| `test_determine_consecutive_week_number` | `self` | `` |  |
| `test_naming_validations` | `self` | `` |  |
| `test_autoincremented_naming` | `self` | `` |  |
| `test_naming_series_prefix` | `self` | `` |  |
| `test_naming_series_validation` | `self` | `` |  |
| `test_naming_using_fields` | `self` | `` |  |
| `test_naming_with_empty_part` | `self` | `` |  |
| `test_naming_with_unsupported_part` | `self` | `` |  |
| `test_naming_with_empty_field` | `self` | `` |  |
| `test_hash_collision` | `self` | `` |  |
| `test_custom_parser` | `self` | `` |  |
| `test_hash_naming_is_roughly_sequential` | `self` | `` | hash naming is supposed to be sequential *most of the time* |
| `test_uuid_naming` | `self` | `` |  |





## Functions

### `parse_naming_series_variable`
**Arguments:** `doc, variable`
**Decorators:** ``

**Docstring:**
```

```
### `make_invalid_todo`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

