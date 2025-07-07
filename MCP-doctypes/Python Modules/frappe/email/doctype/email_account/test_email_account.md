# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_account/test_email_account.py`

## Classes

### `TestEmailAccount`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `get_test_mail` | `self, fname` | `` |  |
| `test_incoming` | `self` | `` |  |
| `test_unread_notification` | `self` | `` |  |
| `test_incoming_with_attach` | `self` | `` |  |
| `test_incoming_attached_email_from_outlook_plain_text_only` | `self` | `` |  |
| `test_incoming_attached_email_from_outlook_layers` | `self` | `` |  |
| `test_outgoing` | `self` | `` |  |
| `test_sendmail` | `self` | `` |  |
| `test_print_format` | `self` | `` |  |
| `test_threading` | `self` | `` |  |
| `test_threading_by_subject` | `self` | `` |  |
| `test_threading_by_message_id` | `self` | `` |  |
| `test_auto_reply` | `self` | `` |  |
| `test_handle_bad_emails` | `self` | `` |  |
| `test_handle_bad_encoding` | `self` | `` | If the email has invalid encoding, it should still be saved as an Unhandled Email. |
| `test_imap_folder` | `self` | `` |  |
| `test_imap_folder_missing` | `self` | `` |  |
| `test_append_to` | `self` | `` |  |
| `test_append_to_with_imap_folders` | `self` | `` |  |
| `mocked_get_inbound_mails` | `email_account, messages, mocked_logout, mocked_select_imap_folder` | `` |  |
| `mocked_email_receive` | `email_account, messages, mocked_logout, mocked_select_imap_folder` | `` |  |


### `TestInboundMail`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `setUp` | `self` | `` |  |
| `get_test_mail` | `self, fname` | `` |  |
| `new_doc` | `self, doctype` | `` |  |
| `new_communication` | `self` | `` |  |
| `new_email_queue` | `self` | `` |  |
| `new_todo` | `self` | `` |  |
| `test_self_sent_mail` | `self` | `` | Check that we raise SentEmailInInboxError if the inbound mail is self sent mail. |
| `test_mail_exist_validation` | `self` | `` | Do not create communication record if the mail is already downloaded into the system. |
| `test_find_parent_email_queue` | `self` | `` | If the mail is reply to the already sent mail, there will be a email queue record. |
| `test_find_parent_communication_through_queue` | `self` | `` | Find parent communication of an inbound mail.
Cases where parent communication does exist:
1. No parent communication is the mail is not a reply.

Cases where parent communication does not exist:
2. If mail is not a reply to system sent mail, then there can exist co |
| `test_find_parent_communication_for_self_reply` | `self` | `` | If the inbound email is a reply but not reply to system sent mail.

Ex: User replied to his/her mail. |
| `test_find_parent_communication_from_header` | `self` | `` | Incase of header contains parent communication name |
| `test_reference_document` | `self` | `` |  |
| `test_reference_document_by_record_name_in_subject` | `self` | `` |  |
| `test_reference_document_by_subject_match` | `self` | `` |  |
| `test_reference_document_by_subject_match_with_accents` | `self` | `` |  |
| `test_create_communication_from_mail` | `self` | `` |  |





## Functions

### `cleanup`
**Arguments:** `sender`
**Decorators:** ``

**Docstring:**
```

```

