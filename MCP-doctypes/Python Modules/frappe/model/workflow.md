# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/workflow.py`

## Classes

### `WorkflowStateError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WorkflowTransitionError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `WorkflowPermissionError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `get_workflow_name`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_transitions`
**Arguments:** `doc, workflow, raise_exception`
**Decorators:** ``

**Docstring:**
```
Return list of possible transitions for the given doc
```
### `get_workflow_safe_globals`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_transition_condition_satisfied`
**Arguments:** `transition, doc`
**Decorators:** ``

**Docstring:**
```

```
### `apply_workflow`
**Arguments:** `doc, action`
**Decorators:** ``

**Docstring:**
```
Allow workflow action on the current doc
```
### `can_cancel_document`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `validate_workflow`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Validate Workflow State and Transition for the current user.

- Check if user is allowed to edit in current state
- Check if user is allowed to transition to the next state (if changed)
```
### `get_workflow`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `has_approval_access`
**Arguments:** `user, doc, transition`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow_state_field`
**Arguments:** `workflow_name`
**Decorators:** ``

**Docstring:**
```

```
### `send_email_alert`
**Arguments:** `workflow_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow_field_value`
**Arguments:** `workflow_name, field`
**Decorators:** ``

**Docstring:**
```

```
### `bulk_workflow_approval`
**Arguments:** `docnames, doctype, action`
**Decorators:** ``

**Docstring:**
```

```
### `_bulk_workflow_action`
**Arguments:** `docnames, doctype, action`
**Decorators:** ``

**Docstring:**
```

```
### `print_workflow_log`
**Arguments:** `messages, title, doctype, indicator`
**Decorators:** ``

**Docstring:**
```

```
### `get_common_transition_actions`
**Arguments:** `docs, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `show_progress`
**Arguments:** `docnames, message, i, description`
**Decorators:** ``

**Docstring:**
```

```
### `set_workflow_state_on_action`
**Arguments:** `doc, workflow_name, action`
**Decorators:** ``

**Docstring:**
```

```

