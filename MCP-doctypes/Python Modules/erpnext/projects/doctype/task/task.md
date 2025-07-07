# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/task/task.py`

## Classes

### `CircularReferenceError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Task`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_customer_details` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_dates` | `self` | `` |  |
| `set_default_end_date_if_missing` | `self` | `` |  |
| `validate_parent_expected_end_date` | `self` | `` |  |
| `validate_parent_project_dates` | `self` | `` |  |
| `validate_status` | `self` | `` |  |
| `validate_progress` | `self` | `` |  |
| `validate_dependencies_for_template_task` | `self` | `` |  |
| `validate_parent_template_task` | `self` | `` |  |
| `validate_depends_on_tasks` | `self` | `` |  |
| `validate_completed_on` | `self` | `` |  |
| `update_depends_on` | `self` | `` |  |
| `update_nsm_model` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `unassign_todo` | `self` | `` |  |
| `update_time_and_costing` | `self` | `` |  |
| `update_project` | `self` | `` |  |
| `check_recursion` | `self` | `` |  |
| `reschedule_dependent_tasks` | `self` | `` |  |
| `has_webform_permission` | `self` | `` |  |
| `populate_depends_on` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `after_delete` | `self` | `` |  |
| `update_status` | `self` | `` |  |





## Functions

### `check_if_child_exists`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_project`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `set_multiple_status`
**Arguments:** `names, status`
**Decorators:** ``

**Docstring:**
```

```
### `set_tasks_as_overdue`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_timesheet`
**Arguments:** `source_name, target_doc, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `get_children`
**Arguments:** `doctype, parent, task, project, is_root`
**Decorators:** ``

**Docstring:**
```

```
### `add_node`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_multiple_tasks`
**Arguments:** `data, parent`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

