# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_queue/email_queue.py`

## Classes

### `EmailQueue`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `set_recipients` | `self, recipients` | `` |  |
| `on_trash` | `self` | `` |  |
| `prevent_email_queue_delete` | `self` | `` |  |
| `get_duplicate` | `self, recipients` | `` |  |
| `new` | `cls, doc_data, ignore_permissions` | `classmethod` |  |
| `find` | `cls, name` | `classmethod` |  |
| `find_one_by_filters` | `cls` | `classmethod` |  |
| `update_db` | `self, commit` | `` |  |
| `update_status` | `self, status, commit` | `` |  |
| `cc` | `self` | `property` |  |
| `to` | `self` | `property` |  |
| `attachments_list` | `self` | `property` |  |
| `get_email_account` | `self, raise_error` | `` |  |
| `is_to_be_sent` | `self` | `` |  |
| `can_send_now` | `self` | `` |  |
| `send` | `self, smtp_server_instance, frappe_mail_client, force_send` | `` | Send emails to recipients. |
| `clear_old_logs` | `days` | `staticmethod` | Remove low priority older than 31 days in Outbox or configured in Log Settings.
Note: Used separate query to avoid deadlock |


### `SendMailContext`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, queue_doc, smtp_server_instance, frappe_mail_client` | `` |  |
| `fetch_outgoing_server` | `self` | `` |  |
| `__enter__` | `self` | `` |  |
| `__exit__` | `self, exc_type, exc_val, exc_tb` | `` |  |
| `notify_failed_email` | `self` | `` |  |
| `update_recipient_status_to_sent` | `self, recipient` | `` |  |
| `get_message_object` | `self, message` | `` |  |
| `message_placeholder` | `self, placeholder_key` | `` |  |
| `build_message` | `self, recipient_email` | `` | Build message specific to the recipient. |
| `get_tracker_str` | `self, recipient_email` | `` |  |
| `get_unsubscribe_str` | `self, recipient_email` | `` |  |
| `get_receivers_str` | `self` | `` |  |
| `get_recipient_str` | `self, recipient_email` | `` |  |
| `include_attachments` | `self, message` | `` |  |
| `_store_file` | `self, file_name, content` | `` |  |


### `QueueBuilder`


**Docstring:**
```
Builds Email Queue from the given data
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, recipients, sender, subject, message, text_content, reference_doctype, reference_name, unsubscribe_method, unsubscribe_params, unsubscribe_message, attachments, reply_to, cc, bcc, message_id, in_reply_to, send_after, expose_recipients, send_priority, communication, read_receipt, queue_separately, is_notification, add_unsubscribe_link, inline_images, header, print_letterhead, with_container, email_read_tracker_url, x_priority, email_headers` | `` | Add email to sending queue (Email Queue)

:param recipients: List of recipients.
:param sender: Email sender.
:param subject: Email subject.
:param message: Email message.
:param text_content: Text version of email message.
:param reference_doctype: Reference DocType of caller document.
:param reference_name: Reference name of caller document.
:param send_priority: Priority for Email Queue, default 1.
:param unsubscribe_method: URL method for unsubscribe. Default is `/api/method/frappe.email.queue.unsubscribe`.
:param unsubscribe_params: additional params for unsubscribed links. default are name, doctype, email
:param attachments: Attachments to be sent.
:param reply_to: Reply to be captured here (default inbox)
:param in_reply_to: Used to send the Message-Id of a received email back as In-Reply-To.
:param send_after: Send this email after the given datetime. If value is in integer, then `send_after` will be the automatically set to no of days from current date.
:param communication: Communication link to be set in Email Queue record
:param queue_separately: Queue each email separately
:param is_notification: Marks email as notification so will not trigger notifications from system
:param add_unsubscribe_link: Send unsubscribe link in the footer of the Email, default 1.
:param inline_images: List of inline images as {"filename", "filecontent"}. All src properties will be replaced with random Content-Id
:param header: Append header in email (boolean)
:param with_container: Wraps email inside styled container
:param email_read_tracker_url: A URL for tracking whether an email is read by the recipient.
:param x_priority: 1 = HIGHEST, 3 = NORMAL, 5 = LOWEST
:param email_headers: Additional headers to be added in the email, e.g. {"X-Custom-Header": "value"} or {"Custom-Header": "value"}. Automatically prepends "X-" to the header name if not present. |
| `unsubscribe_method` | `self` | `property` |  |
| `_get_emails_list` | `self, emails` | `` |  |
| `recipients` | `self` | `property` |  |
| `cc` | `self` | `property` |  |
| `bcc` | `self` | `property` |  |
| `send_after` | `self` | `property` |  |
| `sender` | `self` | `property` |  |
| `email_text_content` | `self` | `` |  |
| `email_html_content` | `self` | `` |  |
| `should_include_unsubscribe_link` | `self` | `` |  |
| `unsubscribe_message` | `self` | `` |  |
| `get_outgoing_email_account` | `self` | `` |  |
| `get_unsubscribed_user_emails` | `self` | `` |  |
| `final_recipients` | `self` | `` |  |
| `final_cc` | `self` | `` |  |
| `get_attachments` | `self` | `` |  |
| `prepare_email_content` | `self` | `` |  |
| `process` | `self, send_now` | `` | Build and return the email queues those are created.

Sends email incase if it is requested to send now. |
| `send_emails` | `self, queue_data, final_recipients` | `` |  |
| `as_dict` | `self, include_recipients` | `` |  |





## Functions

### `retry_sending`
**Arguments:** `queues`
**Decorators:** ``

**Docstring:**
```

```
### `send_now`
**Arguments:** `name, force_send`
**Decorators:** ``

**Docstring:**
```

```
### `toggle_sending`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Add index in `tabCommunication` for `(reference_doctype, reference_name)`
```
### `get_email_retry_limit`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

