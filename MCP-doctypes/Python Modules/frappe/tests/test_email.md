# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_email.py`

## Classes

### `TestEmail`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_email_queue` | `self, send_after` | `` |  |
| `test_send_after` | `self` | `` |  |
| `test_flush` | `self` | `` |  |
| `test_cc_header` | `self` | `` |  |
| `test_cc_footer` | `self` | `` |  |
| `test_expose` | `self` | `` |  |
| `test_sender` | `self` | `` |  |
| `test_unsubscribe` | `self` | `` |  |
| `test_image_parsing` | `self` | `` |  |


### `TestVerifiedRequests`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_round_trip` | `self` | `` |  |


### `TestEmailIntegrationTest`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```
Sends email to local SMTP server and verifies correctness.

SMTP4Dev runs as a service in unit test CI job.
If you need to run this test locally, you must setup SMTP4dev locally.

WARNING: SMTP4dev doesn't have stable API, it can break anytime.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `get_last_sent_emails` | `cls` | `classmethod` |  |
| `get_message` | `cls, message_id` | `classmethod` |  |
| `test_send_email` | `self` | `` |  |
| `test_store_attachments` | `self` | `` | "attach print" feature just tells email queue which document to attach, this is not
actually stored unless system setting says so. |





## Functions

No top-level functions found in this file.
