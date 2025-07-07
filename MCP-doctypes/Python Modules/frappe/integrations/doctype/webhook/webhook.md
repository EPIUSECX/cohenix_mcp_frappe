# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/webhook/webhook.py`

## Classes

### `Webhook`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_docevent` | `self` | `` |  |
| `validate_condition` | `self` | `` |  |
| `validate_request_url` | `self` | `` |  |
| `validate_request_body` | `self` | `` |  |
| `validate_repeating_fields` | `self` | `` | Error when Same Field is entered multiple times in webhook_data |
| `validate_secret` | `self` | `` |  |
| `preview_meets_condition` | `self, preview_document` | `` |  |
| `preview_request_body` | `self, preview_document` | `` |  |





## Functions

### `get_context`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_webhook`
**Arguments:** `doc, webhook`
**Decorators:** ``

**Docstring:**
```

```
### `log_request`
**Arguments:** `webhook, doctype, docname, url, headers, data, res`
**Decorators:** ``

**Docstring:**
```

```
### `get_webhook_headers`
**Arguments:** `doc, webhook`
**Decorators:** ``

**Docstring:**
```

```
### `get_webhook_data`
**Arguments:** `doc, webhook`
**Decorators:** ``

**Docstring:**
```

```
### `get_all_queues`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Fetches all workers and returns a list of available queue names.
```

