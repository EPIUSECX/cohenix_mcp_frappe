# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/data_import/exporter.py`

## Classes

### `Exporter`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, export_fields, export_data, export_filters, export_page_length, file_type` | `` | Exports records of a DocType for use with Importer
        :param doctype: Document Type to export
        :param export_fields=None: One of 'All', 'Mandatory' or {'DocType': ['field1', 'field2'], 'Child DocType': ['childfield1']}
        :param export_data=False: Whether to export data as well
        :param export_filters=None: The filters (dict or list) which is used to query the records
        :param file_type: One of 'Excel' or 'CSV' |
| `get_all_exportable_fields` | `self` | `` |  |
| `serialize_exportable_fields` | `self` | `` |  |
| `get_exportable_fields` | `self, doctype, fieldnames` | `` |  |
| `get_data_to_export` | `self` | `` |  |
| `add_data_row` | `self, doctype, parentfield, doc, rows, row_idx` | `` |  |
| `get_data_as_docs` | `self` | `` |  |
| `add_header` | `self` | `` |  |
| `add_data` | `self` | `` |  |
| `get_csv_array` | `self` | `` |  |
| `get_csv_array_for_export` | `self` | `` |  |
| `build_response` | `self` | `` |  |
| `group_children_data_by_parent` | `self, children_data` | `` |  |





## Functions

No top-level functions found in this file.
