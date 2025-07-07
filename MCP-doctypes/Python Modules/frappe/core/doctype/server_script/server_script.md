# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/server_script/server_script.py`

## Classes

### `ServerScript`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `clear_cache` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `get_code_fields` | `self` | `` |  |
| `scheduled_jobs` | `self` | `property` |  |
| `sync_scheduled_job_type` | `self` | `` | Create or update Scheduled Job Type documents for Scheduler Event Server Scripts |
| `check_if_compilable_in_restricted_context` | `self` | `` | Check compilation errors and send them back as warnings. |
| `execute_method` | `self` | `` | Specific to API endpoint Server Scripts.

Raise:
        frappe.DoesNotExistError: If self.script_type is not API.
        frappe.PermissionError: If self.allow_guest is unset for API accessed by Guest user.

Return:
        dict: Evaluate self.script with frappe.utils.safe_exec.safe_exec and return the flags set in its safe globals. |
| `execute_doc` | `self, doc` | `` | Specific to Document Event triggered Server Scripts

Args:
        doc (Document): Executes script with for a certain document's events |
| `execute_scheduled_method` | `self` | `` | Specific to Scheduled Jobs via Server Scripts

Raises:
        frappe.DoesNotExistError: If script type is not a scheduler event |
| `get_permission_query_conditions` | `self, user` | `` | Specific to Permission Query Server Scripts.

Args:
        user (str): Take user email to execute script and return list of conditions.

Return:
        list: Return list of conditions defined by rules in self.script. |





## Functions

### `get_autocompletion_items`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Generate a list of autocompletion strings from the context dict
that is used while executing a Server Script.

e.g., ["frappe.utils.cint", "frappe.get_all", ...]
```
### `execute_api_server_script`
**Arguments:** `script`
**Decorators:** ``

**Docstring:**
```

```
### `enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

