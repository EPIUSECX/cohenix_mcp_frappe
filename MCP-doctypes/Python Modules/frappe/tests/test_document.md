# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_document.py`

## Classes

### `CustomTestNote`
**Inherits:** `Note`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `age` | `self` | `property` |  |


### `CustomNoteWithoutProperty`
**Inherits:** `Note`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `age` | `self` | `` |  |


### `TestDocument`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_return_empty_list_for_table_field_if_none` | `self` | `` |  |
| `test_load` | `self` | `` |  |
| `test_load_single` | `self` | `` |  |
| `test_insert` | `self` | `` |  |
| `test_website_route_default` | `self` | `` |  |
| `test_insert_with_child` | `self` | `` |  |
| `test_update` | `self` | `` |  |
| `test_discard_transitions` | `self` | `` |  |
| `test_save_on_discard_throws` | `self` | `` |  |
| `test_value_changed` | `self` | `` |  |
| `test_mandatory` | `self` | `` |  |
| `test_text_editor_field` | `self` | `` |  |
| `test_conflict_validation` | `self` | `` |  |
| `test_conflict_validation_single` | `self` | `` |  |
| `test_permission` | `self` | `` |  |
| `test_permission_single` | `self` | `` |  |
| `test_link_validation` | `self` | `` |  |
| `test_validate` | `self` | `` |  |
| `test_db_set_no_query_on_new_docs` | `self` | `` |  |
| `test_new_doc_with_fields` | `self` | `` |  |
| `test_update_after_submit` | `self` | `` |  |
| `test_varchar_length` | `self` | `` |  |
| `test_xss_filter` | `self` | `` |  |
| `test_naming_series` | `self` | `` |  |
| `test_non_negative_check` | `self` | `` |  |
| `test_get_formatted` | `self` | `` |  |
| `test_limit_for_get` | `self` | `` |  |
| `test_virtual_fields` | `self` | `` | Virtual fields are accessible via API and Form views, whenever .as_dict is invoked |
| `test_run_method` | `self` | `` |  |
| `test_extend` | `self` | `` |  |
| `test_set` | `self` | `` |  |
| `test_doc_events` | `self` | `` | validate that all present doc events are correct methods |
| `test_realtime_notify` | `self` | `` |  |
| `test_error_on_saving_new_doc_with_name` | `self` | `` | Trying to save a new doc with name should raise DoesNotExistError |
| `test_validate_from_to_dates` | `self` | `` |  |
| `test_db_set_singles` | `self` | `` |  |


### `TestDocumentWebView`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get` | `self, path, user` | `` |  |
| `test_web_view_link_authentication` | `self` | `` |  |
| `test_base_class_set_correctly_on_has_web_view_change` | `self` | `` |  |
| `test_bulk_inserts` | `self` | `` |  |


### `TestLazyDocument`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_lazy_documents` | `self` | `` |  |
| `test_lazy_doc_efficient_saves` | `self` | `` |  |
| `test_lazy_magic` | `self` | `` |  |
| `test_append_extend_update` | `self` | `` |  |
| `test_for_update` | `self` | `` |  |





## Functions

No top-level functions found in this file.
