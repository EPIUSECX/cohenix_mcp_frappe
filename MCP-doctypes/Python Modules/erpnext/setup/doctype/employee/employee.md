# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/employee/employee.py`

## Classes

### `EmployeeUserDisabledError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InactiveEmployeeStatusError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Employee`
**Inherits:** `NestedSet`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `after_rename` | `self, old, new, merge` | `` |  |
| `set_employee_name` | `self` | `` |  |
| `validate_user_details` | `self` | `` |  |
| `update_nsm_model` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `update_user_permissions` | `self` | `` |  |
| `update_user` | `self` | `` |  |
| `validate_date` | `self` | `` |  |
| `validate_email` | `self` | `` |  |
| `set_preferred_email` | `self` | `` |  |
| `validate_status` | `self` | `` |  |
| `validate_for_enabled_user_id` | `self, enabled` | `` |  |
| `validate_duplicate_user_id` | `self` | `` |  |
| `validate_reports_to` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_preferred_email` | `self` | `` |  |
| `reset_employee_emails_cache` | `self` | `` |  |





## Functions

### `validate_employee_role`
**Arguments:** `doc, method, ignore_emp_check`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_email`
**Arguments:** `employee_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_holiday_list_for_employee`
**Arguments:** `employee, raise_exception`
**Decorators:** ``

**Docstring:**
```

```
### `is_holiday`
**Arguments:** `employee, date, raise_exception, only_non_weekly, with_description`
**Decorators:** ``

**Docstring:**
```
Returns True if given Employee has an holiday on the given date
        :param employee: Employee `name`
        :param date: Date to check. Will check for today if None
        :param raise_exception: Raise an exception if no holiday list found, default is True
        :param only_non_weekly: Check only non-weekly holidays, default is False
```
### `deactivate_sales_person`
**Arguments:** `status, employee`
**Decorators:** ``

**Docstring:**
```

```
### `create_user`
**Arguments:** `employee, user, email`
**Decorators:** ``

**Docstring:**
```

```
### `get_all_employee_emails`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```
Returns list of employee emails either based on user_id or company_email
```
### `get_employee_emails`
**Arguments:** `employee_list`
**Decorators:** ``

**Docstring:**
```
Returns list of employee emails either based on user_id or company_email
```
### `get_children`
**Arguments:** `doctype, parent, company, is_root, is_tree`
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
### `has_user_permission_for_employee`
**Arguments:** `user_name, employee_name`
**Decorators:** ``

**Docstring:**
```

```
### `has_upload_permission`
**Arguments:** `doc, ptype, user`
**Decorators:** ``

**Docstring:**
```

```

