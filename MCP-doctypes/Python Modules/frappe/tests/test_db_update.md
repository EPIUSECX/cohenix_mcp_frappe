# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_db_update.py`

## Classes

### `TestDBUpdate`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_db_update` | `self` | `` |  |
| `test_index_and_unique_constraints` | `self` | `` |  |
| `check_unique_indexes` | `self, doctype, field` | `` |  |
| `test_bigint_conversion` | `self` | `` |  |
| `test_unique_index_on_install` | `self` | `` | Only one unique index should be added |
| `test_unique_index_on_alter` | `self` | `` | Only one unique index should be added |
| `test_uuid_varchar_migration` | `self` | `` |  |
| `test_uuid_link_field` | `self` | `` |  |


### `TestDBUpdateSanityChecks`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_no_unnecessary_migrates` | `self` | `` |  |





## Functions

### `get_fieldtype_from_def`
**Arguments:** `field_def`
**Decorators:** ``

**Docstring:**
```

```
### `get_field_defs`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_other_fields_meta`
**Arguments:** `meta`
**Decorators:** ``

**Docstring:**
```

```
### `get_table_column`
**Arguments:** `doctype, fieldname`
**Decorators:** ``

**Docstring:**
```

```

