# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/customize_form/customize_form.py`

## Classes

### `CustomizeForm`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `on_update` | `self` | `` |  |
| `fetch_to_customize` | `self` | `` |  |
| `validate_doctype` | `self, meta` | `` | Check if the doctype is allowed to be customized. |
| `load_properties` | `self, meta` | `` | Load the customize object (this) with the metadata properties |
| `create_auto_repeat_custom_field_if_required` | `self, meta` | `` | Create auto repeat custom field if it's not already present |
| `get_name_translation` | `self` | `` | Get translation object if exists of current doctype name in the default language |
| `set_name_translation` | `self` | `` | Create, update custom translation for this doctype |
| `clear_existing_doc` | `self` | `` |  |
| `save_customization` | `self` | `` |  |
| `set_property_setters` | `self` | `` |  |
| `set_property_setter_for_field_order` | `self, meta` | `` |  |
| `set_property_setters_for_doctype` | `self, meta` | `` |  |
| `set_property_setters_for_docfield` | `self, meta, df, meta_df` | `` |  |
| `allow_property_change` | `self, prop, meta_df, df` | `` |  |
| `set_property_setters_for_actions_and_links` | `self, meta` | `` | Apply property setters or create custom records for DocType Action and DocType Link |
| `update_order_property_setter` | `self, has_custom, fieldname` | `` | We need to maintain the order of the link/actions if the user has shuffled them.
So we create a new property (ex `links_order`) to keep a list of items. |
| `clear_removed_items` | `self, doctype, items` | `` | Clear rows that do not appear in `items`. These have been removed by the user. |
| `update_custom_fields` | `self` | `` |  |
| `add_custom_field` | `self, df, i` | `` |  |
| `update_in_custom_field` | `self, df, i` | `` |  |
| `delete_custom_fields` | `self` | `` |  |
| `make_property_setter` | `self, prop, value, property_type, fieldname, apply_on, row_name` | `` |  |
| `get_existing_property_value` | `self, property_name, fieldname` | `` |  |
| `validate_fieldtype_change` | `self, df, old_value, new_value` | `` |  |
| `validate_fieldtype_length` | `self` | `` |  |
| `reset_to_defaults` | `self` | `` |  |
| `reset_layout` | `self` | `` |  |
| `trim_table` | `self` | `` | Removes database fields that don't exist in the doctype.

This may be needed as maintenance since removing a field in a DocType
doesn't automatically delete the db field. |
| `allow_fieldtype_change` | `self, old_type, new_type` | `classmethod` | allow type change, if both old_type and new_type are in same field group.
field groups are defined in ALLOWED_FIELDTYPE_CHANGE variables. |





## Functions

### `get_orphaned_columns`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `reset_customization`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `is_standard_or_system_generated_field`
**Arguments:** `df`
**Decorators:** ``

**Docstring:**
```

```
### `get_link_filters_from_doc_without_customisations`
**Arguments:** `doctype, fieldname`
**Decorators:** ``

**Docstring:**
```
Get the filters of a link field from a doc without customisations
In backend the customisations are not applied.
Customisations are applied in the client side.
```

