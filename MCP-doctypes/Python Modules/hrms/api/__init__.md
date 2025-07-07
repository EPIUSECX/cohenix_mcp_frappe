# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/api/__init__.py`

## Classes

No classes found in this file.


## Functions

### `get_current_user_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_current_employee_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_all_employees`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_hr_settings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_unread_notifications_count`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `mark_all_notifications_as_read`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `are_push_notifications_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_calendar_events`
**Arguments:** `employee, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_for_calendar`
**Arguments:** `employee, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_holidays_for_calendar`
**Arguments:** `employee, from_date, to_date`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_requests`
**Arguments:** `employee, approver_id, for_approval, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendance_requests`
**Arguments:** `employee, for_approval, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_filters`
**Arguments:** `doctype, employee, approver_id, for_approval`
**Decorators:** ``

**Docstring:**
```

```
### `get_shift_request_approvers`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_shifts`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_applications`
**Arguments:** `employee, approver_id, for_approval, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_balance_map`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```
Returns a map of leave type and balance details like:
{
        'Casual Leave': {'allocated_leaves': 10.0, 'balance_leaves': 5.0},
        'Earned Leave': {'allocated_leaves': 3.0, 'balance_leaves': 3.0},
}
```
### `get_holidays_for_employee`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_approval_details`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_department_approvers`
**Arguments:** `department, parentfield`
**Decorators:** ``

**Docstring:**
```

```
### `get_leave_types`
**Arguments:** `employee, date`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claims`
**Arguments:** `employee, approver_id, for_approval, limit`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claim_summary`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_type_description`
**Arguments:** `expense_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_claim_types`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_expense_approval_details`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_employee_advance_balance`
**Arguments:** `employee`
**Decorators:** ``

**Docstring:**
```

```
### `get_advance_account`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_currencies`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_currency_symbols`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_company_cost_center_and_expense_account`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctype_fields`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctype_states`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_attachments`
**Arguments:** `dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `upload_base64_file`
**Arguments:** `content, filename, dt, dn, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `delete_attachment`
**Arguments:** `filename`
**Decorators:** ``

**Docstring:**
```

```
### `download_salary_slip`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow_state_field`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_allowed_states_for_workflow`
**Arguments:** `workflow, user_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_permitted_fields_for_write`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```

