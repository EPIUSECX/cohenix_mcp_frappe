# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/automation/doctype/assignment_rule/assignment_rule.py`

## Classes

### `AssignmentRule`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `clear_cache` | `self` | `` |  |
| `validate_document_types` | `self` | `` |  |
| `validate_assignment_days` | `self` | `` |  |
| `apply_unassign` | `self, doc, assignments` | `` |  |
| `apply_assign` | `self, doc` | `` |  |
| `do_assignment` | `self, doc` | `` |  |
| `clear_assignment` | `self, doc` | `` | Clear assignments |
| `close_assignments` | `self, doc` | `` | Close assignments |
| `get_user` | `self, doc` | `` | Get the next user for assignment |
| `get_user_round_robin` | `self` | `` | Get next user based on round robin |
| `get_user_load_balancing` | `self` | `` | Assign to the user with least number of open assignments |
| `get_user_based_on_field` | `self, doc` | `` |  |
| `safe_eval` | `self, fieldname, doc` | `` |  |
| `get_assignment_days` | `self` | `` |  |
| `is_rule_not_applicable_today` | `self` | `` |  |





## Functions

### `get_assignments`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `bulk_apply`
**Arguments:** `doctype, docnames`
**Decorators:** ``

**Docstring:**
```

```
### `reopen_closed_assignment`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `apply`
**Arguments:** `doc, method, doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `update_due_date`
**Arguments:** `doc, state`
**Decorators:** ``

**Docstring:**
```
Run on_update on every Document (via hooks.py)
```
### `get_assignment_rules`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_repeated`
**Arguments:** `values`
**Decorators:** ``

**Docstring:**
```

```

