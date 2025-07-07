# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/notification/notification.py`

## Classes

### `Notification`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` | load message |
| `autoname` | `self` | `` |  |
| `preview_meets_condition` | `self, preview_document` | `` |  |
| `preview_message` | `self, preview_document` | `` |  |
| `preview_subject` | `self, preview_document` | `` |  |
| `validate` | `self` | `` |  |
| `clear_cache` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `validate_standard` | `self` | `` |  |
| `validate_condition` | `self` | `` |  |
| `validate_forbidden_document_types` | `self` | `` |  |
| `get_documents_for_today` | `self` | `` | get list of documents that will be triggered today |
| `get_documents_for_this_moment` | `self` | `` | Get list of documents that will be triggered at this moment.

This method retrieves documents based on the specified datetime field and minutes offset.
It considers documents that fall within the time range from the last run time plus the offset
up to the current time plus the offset.

Returns:
        list: A list of document objects that meet the criteria for notification. |
| `queue_send` | `self, doc, enqueue_after_commit` | `` | Enqueue the process to build recipients and send notifications.

This method is particularly useful for sending notifications, especially 'Custom'-type,
without the additional overhead associated with `Document.queue_action`.

Args:
              doc (Document): The document object for which the notification is being sent.
              enqueue_after_commit (bool, optional): If True, the task will be enqueued after
                the current transaction is committed. Defaults to True.

Note:
              This method is the recommended way to send 'Custom'-type notifications.

Example:
              To queue a notification from a server script:

              ```python
              notification = frappe.get_doc("Notification", "My Notification", ignore_permissions=True)
              notification.queue_send(customer)
              ```

              This example queues the "My Notification" to be sent for the specified customer document. |
| `send` | `self, doc` | `` | Build recipients and send Notification |
| `send_notification_by_channel` | `self, doc, context` | `` | Send notification based on the specified channel. |
| `create_system_notification` | `self, doc, context` | `` |  |
| `send_an_email` | `self, doc, context` | `` |  |
| `send_a_slack_msg` | `self, doc, context` | `` |  |
| `send_sms` | `self, doc, context` | `` |  |
| `get_mobile_no` | `doc, field` | `staticmethod` |  |
| `get_list_of_recipients` | `self, doc, context` | `` |  |
| `get_receiver_list` | `self, doc, context, field_on_user, recipient_extractor_func` | `` | return receiver list based on the doc field and role specified |
| `get_attachment` | `self, doc` | `` | check print settings are attach the pdf |
| `get_template` | `self, md_as_html` | `` |  |
| `load_standard_properties` | `self, context` | `` | load templates and run get_context |
| `on_trash` | `self` | `` |  |





## Functions

### `clear_notification_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_documents_for_today`
**Arguments:** `notification`
**Decorators:** ``

**Docstring:**
```

```
### `trigger_offset_alerts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `trigger_daily_alerts`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `trigger_notifications`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `evaluate_alert`
**Arguments:** `doc, alert, event`
**Decorators:** ``

**Docstring:**
```

```
### `get_context`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_assignees`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_emails_from_template`
**Arguments:** `template, context`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_doctype`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_reference_name`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `_parse_receiver_by_document_field`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```

```

