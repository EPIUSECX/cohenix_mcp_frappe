# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/workflow/doctype/workflow_action/workflow_action.py`

## Classes

### `WorkflowAction`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_query_conditions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `process_workflow_actions`
**Arguments:** `doc, state`
**Decorators:** ``

**Docstring:**
```

```
### `apply_action`
**Arguments:** `action, doctype, docname, current_state, user, last_modified`
**Decorators:** ``

**Docstring:**
```

```
### `confirm_action`
**Arguments:** `doctype, docname, user, action`
**Decorators:** ``

**Docstring:**
```

```
### `return_success_page`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `return_action_confirmation_page`
**Arguments:** `doc, action, action_link, alert_doc_change`
**Decorators:** ``

**Docstring:**
```

```
### `return_link_expired_page`
**Arguments:** `doc, doc_workflow_state`
**Decorators:** ``

**Docstring:**
```

```
### `update_completed_workflow_actions`
**Arguments:** `doc, user, workflow, workflow_state`
**Decorators:** ``

**Docstring:**
```

```
### `get_allowed_roles`
**Arguments:** `user, workflow, workflow_state`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow_action_by_role`
**Arguments:** `doc, allowed_roles`
**Decorators:** ``

**Docstring:**
```

```
### `update_completed_workflow_actions_using_role`
**Arguments:** `user, workflow_action`
**Decorators:** ``

**Docstring:**
```

```
### `get_next_possible_transitions`
**Arguments:** `workflow_name, state, doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_users_next_action_data`
**Arguments:** `transitions, doc`
**Decorators:** ``

**Docstring:**
```

```
### `create_workflow_actions_for_roles`
**Arguments:** `roles, doc`
**Decorators:** ``

**Docstring:**
```

```
### `send_workflow_action_email`
**Arguments:** `doc, transitions`
**Decorators:** ``

**Docstring:**
```

```
### `deduplicate_actions`
**Arguments:** `action_list`
**Decorators:** ``

**Docstring:**
```

```
### `get_workflow_action_url`
**Arguments:** `action, doc, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_confirm_workflow_action_url`
**Arguments:** `doc, action, user`
**Decorators:** ``

**Docstring:**
```

```
### `is_workflow_action_already_created`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `clear_workflow_actions`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_doc_workflow_state`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_common_email_args`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_email_template_from_workflow`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Return next_action_email_template for workflow state (if available) based on doc current workflow state.
```
### `get_state_optional_field_value`
**Arguments:** `workflow_name, state`
**Decorators:** ``

**Docstring:**
```

```

