# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/projects/doctype/project/project.py`

## Classes

### `Project`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `before_print` | `self, settings` | `` |  |
| `validate` | `self` | `` |  |
| `copy_from_template` | `self` | `` | Copy tasks from template |
| `create_task_from_template` | `self, task_details` | `` |  |
| `calculate_start_date` | `self, task_details` | `` |  |
| `calculate_end_date` | `self, task_details` | `` |  |
| `update_if_holiday` | `self, date` | `` |  |
| `dependency_mapping` | `self, template_tasks, project_tasks` | `` |  |
| `check_depends_on_value` | `self, template_task, project_task, project_tasks` | `` |  |
| `check_for_parent_tasks` | `self, template_task, project_task, project_tasks` | `` |  |
| `is_row_updated` | `self, row, existing_task_data, fields` | `` |  |
| `update_project` | `self` | `` | Called externally by Task |
| `after_insert` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `update_percent_complete` | `self` | `` |  |
| `update_costing` | `self` | `` |  |
| `calculate_gross_margin` | `self` | `` |  |
| `update_purchase_costing` | `self` | `` |  |
| `update_sales_amount` | `self` | `` |  |
| `update_billed_amount` | `self` | `` |  |
| `get_billed_amount_from_parent` | `self` | `` |  |
| `get_billed_amount_from_child` | `self` | `` |  |
| `after_rename` | `self, old_name, new_name, merge` | `` |  |
| `send_welcome_email` | `self` | `` |  |





## Functions

### `get_timeline_data`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Return timeline for attendance
```
### `get_project_list`
**Arguments:** `doctype, txt, filters, limit_start, limit_page_length, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_users_for_project`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_cost_center_name`
**Arguments:** `project`
**Decorators:** ``

**Docstring:**
```

```
### `hourly_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `project_status_update_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `daily_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `twice_daily_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `weekly_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `allow_to_make_project_update`
**Arguments:** `project, time, frequency`
**Decorators:** ``

**Docstring:**
```

```
### `create_duplicate_project`
**Arguments:** `prev_doc, project_name`
**Decorators:** ``

**Docstring:**
```
Create duplicate project based on the old project
```
### `get_projects_for_collect_progress`
**Arguments:** `frequency, fields`
**Decorators:** ``

**Docstring:**
```

```
### `send_project_update_email_to_users`
**Arguments:** `project`
**Decorators:** ``

**Docstring:**
```

```
### `collect_project_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_project_status_email_to_users`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_project_sales_billing`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_kanban_board_if_not_exists`
**Arguments:** `project`
**Decorators:** ``

**Docstring:**
```

```
### `set_project_status`
**Arguments:** `project, status`
**Decorators:** ``

**Docstring:**
```
set status for project and all related tasks
```
### `get_holiday_list`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_users_email`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_total_purchase_cost`
**Arguments:** `project`
**Decorators:** ``

**Docstring:**
```

```
### `recalculate_project_total_purchase_cost`
**Arguments:** `project`
**Decorators:** ``

**Docstring:**
```

```

