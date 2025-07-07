# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/document_naming_settings/document_naming_settings.py`

## Classes

### `NamingSeriesNotSetError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `DocumentNamingSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_transactions_and_prefixes` | `self` | `` |  |
| `_get_transactions` | `self` | `` |  |
| `_get_prefixes` | `self, doctypes` | `` | Get all prefixes for naming series.

- For all templates prefix is evaluated considering today's date
- All existing prefix in DB are shared as is. |
| `_evaluate_and_clean_templates` | `self, series_templates` | `` |  |
| `get_options_list` | `self, options` | `` |  |
| `update_series` | `self` | `` | update series list |
| `validate_set_series` | `self` | `` |  |
| `set_series_options_in_meta` | `self, doctype, options` | `` |  |
| `update_naming_series_property_setter` | `self, doctype, property, value` | `` |  |
| `check_duplicate` | `self` | `` |  |
| `validate_series_name` | `self, series` | `` |  |
| `get_options` | `self, doctype` | `` |  |
| `get_current` | `self` | `` | get series current |
| `update_amendment_rule` | `self` | `` |  |
| `update_series_start` | `self` | `` |  |
| `create_version_log_for_change` | `self, series, old, new` | `` |  |
| `preview_series` | `self` | `` | Preview what the naming series will generate. |
| `_fetch_last_doc_if_available` | `self` | `` | Fetch last doc for evaluating naming series with fields. |





## Functions

No top-level functions found in this file.
