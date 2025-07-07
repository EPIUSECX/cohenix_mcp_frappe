# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/quality_inspection/quality_inspection.py`

## Classes

### `QualityInspection`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `set_company` | `self` | `` |  |
| `set_child_row_reference` | `self` | `` |  |
| `distribute_child_row_reference` | `self, child_row_references` | `` |  |
| `validate_inspection_required` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `get_item_specification_details` | `self` | `` |  |
| `get_quality_inspection_template` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_readings_status_mandatory` | `self` | `` |  |
| `update_qc_reference` | `self, remove_reference` | `` |  |
| `inspect_and_set_status` | `self` | `` |  |
| `set_status_based_on_acceptance_values` | `self, reading` | `` |  |
| `min_max_criteria_passed` | `self, reading` | `` | Determine whether all readings fall in the acceptable range. |
| `set_status_based_on_acceptance_formula` | `self, reading` | `` |  |
| `get_formula_evaluation_data` | `self, reading` | `` |  |
| `calculate_mean` | `self, reading` | `` | Calculate mean of all non-empty readings. |





## Functions

### `item_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `quality_inspection_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `make_quality_inspection`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `parse_float`
**Arguments:** `num`
**Decorators:** ``

**Docstring:**
```
Since reading_# fields are `Data` field they might contain number which
is representation in user's prefered number format instead of machine
readable format. This function converts them to machine readable format.
```

