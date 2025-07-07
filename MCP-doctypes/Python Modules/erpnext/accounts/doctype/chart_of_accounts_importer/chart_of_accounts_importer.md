# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/chart_of_accounts_importer/chart_of_accounts_importer.py`

## Classes

### `ChartofAccountsImporter`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |





## Functions

### `validate_columns`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```

```
### `validate_company`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `import_coa`
**Arguments:** `file_name, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_file`
**Arguments:** `file_name`
**Decorators:** ``

**Docstring:**
```

```
### `generate_data_from_csv`
**Arguments:** `file_doc, as_dict`
**Decorators:** ``

**Docstring:**
```
read csv file and return the generated nested tree
```
### `generate_data_from_excel`
**Arguments:** `file_doc, extension, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_coa`
**Arguments:** `doctype, parent, is_root, file_name, for_validate`
**Decorators:** ``

**Docstring:**
```
called by tree view (to fetch node's children)
```
### `build_forest`
**Arguments:** `data`
**Decorators:** ``

**Docstring:**
```
converts list of list into a nested tree
if a = [[1,1], [1,2], [3,2], [4,4], [5,4]]
tree = {
        1: {
                2: {
                        3: {}
                }
        },
        4: {
                5: {}
        }
}
```
### `build_response_as_excel`
**Arguments:** `writer`
**Decorators:** ``

**Docstring:**
```

```
### `download_template`
**Arguments:** `file_type, template_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_template`
**Arguments:** `template_type, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_sample_template`
**Arguments:** `writer, company`
**Decorators:** ``

**Docstring:**
```

```
### `validate_accounts`
**Arguments:** `file_doc, extension`
**Decorators:** ``

**Docstring:**
```

```
### `validate_root`
**Arguments:** `accounts`
**Decorators:** ``

**Docstring:**
```

```
### `validate_missing_roots`
**Arguments:** `roots`
**Decorators:** ``

**Docstring:**
```

```
### `get_root_types`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_report_type`
**Arguments:** `root_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_mandatory_group_accounts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_mandatory_account_types`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `unset_existing_data`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `set_default_accounts`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```

