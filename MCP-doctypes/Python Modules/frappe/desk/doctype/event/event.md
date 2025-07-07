# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/event/event.py`

## Classes

### `Event`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `sync_communication` | `self` | `` |  |
| `create_communication` | `self, participant` | `` |  |
| `update_communication` | `self, participant, communication` | `` |  |
| `add_participant` | `self, doctype, docname` | `` | Add a single participant to event participants

Args:
        doctype (string): Reference Doctype
        docname (string): Reference Docname |
| `add_participants` | `self, participants` | `` | Add participant entry

Args:
        participants ([Array]): Array of a dict with doctype and docname |
| `set_participants_email` | `self` | `` |  |





## Functions

### `delete_communication`
**Arguments:** `event, reference_doctype, reference_docname`
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
### `send_event_digest`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_events`
**Arguments:** `start, end, user, for_reminder, filters`
**Decorators:** ``

**Docstring:**
```

```
### `delete_events`
**Arguments:** `ref_type, ref_name, delete_event`
**Decorators:** ``

**Docstring:**
```

```
### `set_status_of_events`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

