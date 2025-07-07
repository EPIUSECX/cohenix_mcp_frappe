# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/communication/mixins.py`

## Classes

### `CommunicationEmailMixin`


**Docstring:**
```
Mixin class to handle communication mails.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `is_email_communication` | `self` | `` |  |
| `get_owner` | `self` | `` | Get owner of the communication docs parent. |
| `get_all_email_addresses` | `self, exclude_displayname` | `` | Get all Email addresses mentioned in the doc along with display name. |
| `get_email_with_displayname` | `self, email_address` | `` | Return email address after adding displayname. |
| `mail_recipients` | `self, is_inbound_mail_communcation` | `` | Build to(recipient) list to send an email. |
| `get_mail_recipients_with_displayname` | `self, is_inbound_mail_communcation` | `` | Build to(recipient) list to send an email including displayname in email. |
| `mail_cc` | `self, is_inbound_mail_communcation, include_sender` | `` | Build cc list to send an email.

* if email copy is requested by sender, then add sender to CC.
* If this doc is created through inbound mail, then add doc owner to cc list
* remove all the thread_notify disabled users.
* Remove standard users from email list |
| `get_mail_cc_with_displayname` | `self, is_inbound_mail_communcation, include_sender` | `` |  |
| `mail_bcc` | `self, is_inbound_mail_communcation` | `` | * Thread_notify check
* Email unsubscribe list
* remove standard users. |
| `get_mail_bcc_with_displayname` | `self, is_inbound_mail_communcation` | `` |  |
| `mail_sender` | `self` | `` |  |
| `mail_sender_fullname` | `self` | `` |  |
| `get_mail_sender_with_displayname` | `self` | `` |  |
| `get_content` | `self, print_format` | `` |  |
| `get_attach_link` | `self, print_format` | `` | Return public link for the attachment via `templates/emails/print_link.html`. |
| `get_outgoing_email_account` | `self` | `` |  |
| `get_incoming_email_account` | `self` | `` |  |
| `mail_attachments` | `self, print_format, print_html, print_language` | `` |  |
| `get_unsubscribe_message` | `self` | `` |  |
| `exclude_emails_list` | `self, is_inbound_mail_communcation, include_sender` | `` | List of mail id's excluded while sending mail. |
| `get_assignees` | `self` | `` | Get owners of the reference document. |
| `filter_thread_notification_disbled_users` | `emails` | `staticmethod` | Filter users based on notifications for email threads setting is disabled. |
| `filter_disabled_users` | `emails` | `staticmethod` |  |
| `sendmail_input_dict` | `self, print_html, print_format, send_me_a_copy, print_letterhead, is_inbound_mail_communcation, print_language` | `` |  |
| `send_email` | `self, print_html, print_format, send_me_a_copy, print_letterhead, is_inbound_mail_communcation, print_language, now` | `` |  |





## Functions

No top-level functions found in this file.
