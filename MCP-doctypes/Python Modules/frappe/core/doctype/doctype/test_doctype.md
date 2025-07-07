# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/doctype/test_doctype.py`

## Classes

### `TestDocType`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `tearDown` | `self` | `` |  |
| `test_validate_name` | `self` | `` |  |
| `test_making_sequence_on_change` | `self` | `` |  |
| `test_doctype_unique_constraint_dropped` | `self` | `` |  |
| `test_validate_search_fields` | `self` | `` |  |
| `test_depends_on_fields` | `self` | `` |  |
| `test_all_depends_on_fields_conditions` | `self` | `` |  |
| `test_sync_field_order` | `self` | `` |  |
| `test_unique_field_name_for_two_fields` | `self` | `` |  |
| `test_fieldname_is_not_name` | `self` | `` |  |
| `test_illegal_mandatory_validation` | `self` | `` |  |
| `test_link_with_wrong_and_no_options` | `self` | `` |  |
| `test_hidden_and_mandatory_without_default` | `self` | `` |  |
| `test_field_can_not_be_indexed_validation` | `self` | `` |  |
| `test_cancel_link_doctype` | `self` | `` |  |
| `test_ignore_cancelation_of_linked_doctype_during_cancel` | `self` | `` |  |
| `test_links_table_fieldname_validation` | `self` | `` |  |
| `test_create_virtual_doctype` | `self` | `` | Test virtual DocType. |
| `test_create_virtual_doctype_as_child_table` | `self` | `` | Test virtual DocType as Child Table below a normal DocType. |
| `test_default_fieldname` | `self` | `` |  |
| `test_autoincremented_doctype_transition` | `self` | `` |  |
| `test_json_field` | `self` | `` | Test json field. |
| `test_no_delete_doc` | `self` | `` |  |
| `test_export_types` | `self` | `` | Export python types. |
| `test_custom_field_deletion` | `self` | `` | Custom child tables whose doctype doesn't exist should be auto deleted. |
| `test_delete_doctype_with_customization` | `self` | `` |  |
| `test_delete_orphaned_doctypes` | `self` | `` |  |
| `test_not_in_list_view_for_not_allowed_mandatory_field` | `self` | `` |  |
| `test_no_recursive_fetch` | `self` | `` |  |
| `test_meta_serialization` | `self` | `` |  |
| `test_row_compression` | `self` | `` |  |





## Functions

### `new_doctype`
**Arguments:** `name, unique, depends_on, fields, custom, default`
**Decorators:** ``

**Docstring:**
```

```

