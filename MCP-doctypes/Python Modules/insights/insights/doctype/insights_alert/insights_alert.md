# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_alert/insights_alert.py`

## Classes

### `InsightsAlert`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `send_alert` | `self, force` | `` |  |
| `send_telegram_alert` | `self, message` | `` |  |
| `send_email_alert` | `self, message` | `` |  |
| `evaluate_condition` | `self` | `` |  |
| `evaluate_message` | `self` | `` |  |
| `get_message_context` | `self` | `` |  |
| `get_recipients` | `self` | `` |  |
| `next_execution` | `self` | `property` |  |
| `get_next_execution` | `self` | `` |  |
| `is_event_due` | `self` | `` |  |
| `test_alert` | `self` | `` |  |


### `TelegramAlert`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, chat_id` | `` |  |
| `send` | `self, message` | `` |  |
| `bot` | `self` | `property` |  |





## Functions

### `send_alerts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

