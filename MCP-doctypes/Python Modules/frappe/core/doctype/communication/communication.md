# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/communication/communication.py`

## Classes

### `Communication`
**Inherits:** `Document, CommunicationEmailMixin`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` | create email flag queue |
| `validate` | `self` | `` |  |
| `validate_reference` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `set_signature_in_email_content` | `self` | `` | Set sender's User.email_signature or default outgoing's EmailAccount.signature to the email |
| `before_save` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `sender_mailid` | `self` | `property` |  |
| `_get_emails_list` | `emails, exclude_displayname` | `staticmethod` | Return list of emails from given email string.

* Removes duplicate mailids
* Removes display name from email address if exclude_displayname is True |
| `to_list` | `self, exclude_displayname` | `` | Return `to` list. |
| `cc_list` | `self, exclude_displayname` | `` | Return `cc` list. |
| `bcc_list` | `self, exclude_displayname` | `` | Return `bcc` list. |
| `get_attachments` | `self` | `` |  |
| `notify_change` | `self, action` | `` |  |
| `set_status` | `self` | `` |  |
| `mark_email_as_spam` | `self` | `` |  |
| `find` | `cls, name, ignore_error` | `classmethod` |  |
| `find_one_by_filters` | `cls` | `classmethod` |  |
| `update_db` | `self` | `` |  |
| `set_sender_full_name` | `self` | `` |  |
| `set_delivery_status` | `self, commit` | `` | Look into the status of Email Queue linked to this Communication and set the Delivery Status of this Communication |
| `parse_email_for_timeline_links` | `self` | `` |  |
| `set_timeline_links` | `self` | `` |  |
| `deduplicate_timeline_links` | `self` | `` |  |
| `add_link` | `self, link_doctype, link_name, autosave` | `` |  |
| `get_links` | `self` | `` |  |
| `remove_link` | `self, link_doctype, link_name, autosave, ignore_permissions` | `` |  |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Add indexes in `tabCommunication`
```
### `has_permission`
**Arguments:** `doc, ptype, user, debug`
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_query_conditions_for_communication`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_contacts`
**Arguments:** `email_strings, auto_create_contact`
**Decorators:** ``

**Docstring:**
```

```
### `get_emails`
**Arguments:** `email_strings`
**Decorators:** ``

**Docstring:**
```

```
### `add_contact_links_to_communication`
**Arguments:** `communication, contact_name`
**Decorators:** ``

**Docstring:**
```

```
### `parse_email`
**Arguments:** `email_strings`
**Decorators:** ``

**Docstring:**
```
Parse email to add timeline links.
When automatic email linking is enabled, an email from email_strings can contain
a doctype and docname ie in the format `admin+doctype+docname@example.com` or `admin+doctype=docname@example.com`,
the email is parsed and doctype and docname is extracted.

see: RFC5233
```
### `get_email_without_link`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```
Return email address without doctype links.

e.g. 'admin@example.com' is returned for email 'admin+doctype+docname@example.com'

see: RFC5233
```
### `update_parent_document_on_communication`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Update mins_to_first_communication of parent document based on who is replying.
```
### `update_first_response_time`
**Arguments:** `parent, communication`
**Decorators:** ``

**Docstring:**
```

```
### `set_avg_response_time`
**Arguments:** `parent, communication`
**Decorators:** ``

**Docstring:**
```

```

