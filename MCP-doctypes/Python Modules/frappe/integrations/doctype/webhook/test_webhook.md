# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/webhook/test_webhook.py`

## Classes

### `TestWebhook`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `create_sample_webhooks` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_webhook_trigger_with_enabled_webhooks` | `self` | `` | Test webhook trigger for enabled webhooks |
| `test_validate_doc_events` | `self` | `` | Test creating a submit-related webhook for a non-submittable DocType |
| `test_validate_request_url` | `self` | `` | Test validation for the webhook request URL |
| `test_validate_headers` | `self` | `` | Test validation for request headers |
| `test_validate_request_body_form` | `self` | `` | Test validation of Form URL-Encoded request body |
| `test_validate_request_body_json` | `self` | `` | Test validation of JSON request body |
| `test_webhook_req_log_creation` | `self` | `` |  |
| `test_webhook_with_array_body` | `self` | `` | Check if array request body are supported. |
| `test_webhook_with_dynamic_url_enabled` | `self` | `` |  |
| `test_webhook_with_dynamic_url_disabled` | `self` | `` |  |





## Functions

### `get_test_webhook`
**Arguments:** `config`
**Decorators:** `contextmanager`

**Docstring:**
```

```

