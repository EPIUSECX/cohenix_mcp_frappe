# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/appointment/appointment.py`

## Classes

### `Appointment`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `find_lead_by_email` | `self` | `` |  |
| `find_customer_by_email` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `send_confirmation_email` | `self` | `` |  |
| `on_change` | `self` | `` |  |
| `set_verified` | `self, email` | `` |  |
| `create_lead_and_link` | `self` | `` |  |
| `auto_assign` | `self` | `` |  |
| `get_assignee_from_latest_opportunity` | `self` | `` |  |
| `create_calendar_event` | `self` | `` |  |
| `_get_verify_url` | `self` | `` |  |
| `assign_agent` | `self, agent` | `` |  |





## Functions

### `_get_agents_sorted_by_asc_workload`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```

```
### `_get_agent_list_as_strings`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_check_agent_availability`
**Arguments:** `agent_email, scheduled_time`
**Decorators:** ``

**Docstring:**
```

```
### `_get_employee_from_user`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

