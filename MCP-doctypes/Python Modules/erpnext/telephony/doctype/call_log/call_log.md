# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/telephony/doctype/call_log/call_log.py`

## Classes

### `CallLog`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `before_insert` | `self` | `` | Add lead(third party person) links to the document. |
| `after_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `is_incoming_call` | `self` | `` |  |
| `add_link` | `self, link_type, link_name` | `` |  |
| `trigger_call_popup` | `self` | `` |  |
| `update_received_by` | `self` | `` |  |





## Functions

### `add_call_summary_and_call_type`
**Arguments:** `call_log, summary, call_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_employees_with_number`
**Arguments:** `number`
**Decorators:** ``

**Docstring:**
```

```
### `link_existing_conversations`
**Arguments:** `doc, state`
**Decorators:** ``

**Docstring:**
```
Called from hooks on creation of Contact or Lead to link all the existing conversations.
```
### `get_linked_call_logs`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

