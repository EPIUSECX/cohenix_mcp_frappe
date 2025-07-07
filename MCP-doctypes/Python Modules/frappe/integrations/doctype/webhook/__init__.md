# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/webhook/__init__.py`

## Classes

No classes found in this file.


## Functions

### `get_all_webhooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `run_webhooks`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Run webhooks for this method
```
### `_add_webhook_to_queue`
**Arguments:** `webhook, doc`
**Decorators:** ``

**Docstring:**
```

```
### `flush_webhook_execution_queue`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Enqueue all pending webhook executions.

Each webhook can trigger multiple times on same document or even different instance of same
document. We assume that last enqueued version of document is the final document for this DB
transaction.
```

