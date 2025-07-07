# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/appraisal_cycle/appraisal_cycle.py`

## Classes

### `AppraisalCycle`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_evaluation_method_change` | `self` | `` |  |
| `check_if_appraisals_exist` | `self` | `` |  |
| `set_employees` | `self` | `` | Pull employees in appraisee list based on selected filters |
| `get_employees_for_appraisal` | `self` | `` |  |
| `get_appraisal_template_map` | `self` | `` |  |
| `create_appraisals` | `self` | `` |  |
| `show_missing_template_message` | `self, raise_exception` | `` |  |
| `complete_cycle` | `self` | `` |  |





## Functions

### `create_appraisals_for_cycle`
**Arguments:** `appraisal_cycle, publish_progress`
**Decorators:** ``

**Docstring:**
```
Creates appraisals for employees in the appraisee list of appraisal cycle,
if not already created
```
### `validate_active_appraisal_cycle`
**Arguments:** `appraisal_cycle`
**Decorators:** ``

**Docstring:**
```

```
### `get_appraisal_cycle_summary`
**Arguments:** `cycle_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_employees_without_goals`
**Arguments:** `cycle_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_employees_without_feedback`
**Arguments:** `cycle_name`
**Decorators:** ``

**Docstring:**
```

```

