# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/receive.py`

## Classes

### `EmailSizeExceededError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `LoginLimitExceeded`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SentEmailInInboxError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmailServer`


**Docstring:**
```
Wrapper for POP server to pull emails.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, args` | `` |  |
| `connect` | `self` | `` | Connect to **Email Account**. |
| `connect_imap` | `self` | `` | Connect to IMAP |
| `connect_pop` | `self` | `` |  |
| `select_imap_folder` | `self, folder` | `` |  |
| `logout` | `self` | `` |  |
| `get_messages` | `self, folder` | `` | Return new email messages. |
| `get_new_mails` | `self, folder` | `` | Return list of new mails |
| `check_imap_uidvalidity` | `self, folder` | `` |  |
| `parse_imap_response` | `self, cmd, response` | `` |  |
| `retrieve_message` | `self, uid, msg_num, folder` | `` |  |
| `get_email_seen_status` | `self, uid, flag_string` | `` | parse the email FLAGS response |
| `has_login_limit_exceeded` | `self, e` | `` |  |
| `_post_retrieve_cleanup` | `self, uid, msg_num` | `` |  |
| `is_temporary_system_problem` | `self, e` | `` |  |
| `make_error_msg` | `self, uid, msg_num` | `` |  |
| `update_flag` | `self, folder, uid_list` | `` | set all uids mails the flag as seen |


### `Email`


**Docstring:**
```
Wrapper for an email.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, content` | `` | Parses headers, content, attachments from given raw message.

:param content: Raw message. |
| `in_reply_to` | `self` | `property` |  |
| `parse` | `self` | `` | Walk and process multi-part email. |
| `set_subject` | `self` | `` | Parse and decode `Subject` header. |
| `set_from` | `self` | `` |  |
| `decode_email` | `email` | `staticmethod` |  |
| `set_content_and_type` | `self` | `` |  |
| `process_part` | `self, part` | `` | Parse email `part` and set it to `text_content`, `html_content` or `attachments`. |
| `show_attached_email_headers_in_content` | `self, part` | `` |  |
| `get_charset` | `self, part` | `` |  |
| `get_payload` | `self, part` | `` |  |
| `get_attachment` | `self, part` | `` |  |
| `save_attachments_in_doc` | `self, doc` | `` | Save email attachments in given document. |
| `get_thread_id` | `self` | `` | Extract thread ID from `[]` |
| `is_reply` | `self` | `` |  |


### `InboundMail`
**Inherits:** `Email`


**Docstring:**
```
Class representation of incoming mail along with mail handlers.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, content, email_account, uid, seen_status, append_to` | `` |  |
| `get_content` | `self` | `` |  |
| `process` | `self` | `` | Create communication record from email. |
| `_build_communication_doc` | `self` | `` |  |
| `replace_inline_images` | `self, attachments` | `` |  |
| `is_notification` | `self` | `` |  |
| `is_exist_in_system` | `self` | `` | Check if this email already exists in the system(as communication document). |
| `is_sender_same_as_receiver` | `self` | `` |  |
| `is_reply_to_system_sent_mail` | `self` | `` | Is it a reply to already sent mail. |
| `parent_email_queue` | `self` | `` | Get parent record from `Email Queue`.

If it is a reply to already sent mail, then there will be a parent record in EMail Queue. |
| `parent_communication` | `self` | `` | Find a related communication so that we can prepare a mail thread.

The way it happens is by using in-reply-to header, and we can't make thread if it does not exist.

Here are the cases to handle:
1. If mail is a reply to already sent mail, then we can get parent communicaion from
        Email Queue record or message_id on communication.
2. Sometimes we send communication name in message-ID directly, use that to get parent communication.
3. Sender sent a reply but reply is on top of what (s)he sent before,
        then parent record exists directly in communication. |
| `reference_document` | `self` | `` | Reference document is a document to which mail relate to.

We can get reference document from Parent record(EmailQueue | Communication) if exists.
Otherwise we do subject match to find reference document if we know the reference(append_to) doctype. |
| `get_reference_name_from_subject` | `self` | `` | Ex: "Re: Your email (#OPP-2020-2334343)" |
| `match_record_by_subject_and_sender` | `self, doctype` | `` | Find a record in the given doctype that matches with email subject and sender.

Cases:
1. Sometimes record name is part of subject. We can get document by parsing name from subject
2. Find by matching sender and subject
3. Find by matching subject alone (Special case)
        Ex: when a System User is using Outlook and replies to an email from their own client,
        it reaches the Email Account with the threading info lost and the (sender + subject match)
        doesn't work because the sender in the first communication was someone different to whom
        the system user is replying to via the common email account in Frappe. This fix bypasses
        the sender match when the sender is a system user and subject is atleast 10 chars long
        (for additional safety)

NOTE: We consider not to match by subject if match record is very old. |
| `_create_reference_document` | `self, doctype` | `` | Create reference document if it does not exist in the system. |
| `get_doc` | `doctype, docname, ignore_error` | `staticmethod` |  |
| `get_relative_dt` | `days` | `staticmethod` | Get relative to current datetime. Only relative days are supported. |
| `get_users_linked_to_account` | `email_account` | `staticmethod` | Get list of users who linked to Email account. |
| `clean_subject` | `subject` | `staticmethod` | Remove Prefixes like 'fw', FWD', 're' etc from subject. |
| `get_email_fields` | `doctype` | `staticmethod` | Return Email related fields of a doctype. |
| `get_document` | `self, doctype, name` | `staticmethod` | Is same as frappe.get_doc but suppresses the DoesNotExist error. |
| `as_dict` | `self` | `` |  |





## Functions

No top-level functions found in this file.
