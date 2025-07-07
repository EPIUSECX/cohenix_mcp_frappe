# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/communication/email.py`

## Classes

No classes found in this file.


## Functions

### `make`
**Arguments:** `doctype, name, content, subject, sent_or_received, sender, sender_full_name, recipients, communication_medium, send_email, print_html, print_format, attachments, send_me_a_copy, cc, bcc, read_receipt, print_letterhead, email_template, communication_type, send_after, print_language, now`
**Decorators:** ``

**Docstring:**
```
Make a new communication. Checks for email permissions for specified Document.

:param doctype: Reference DocType.
:param name: Reference Document name.
:param content: Communication body.
:param subject: Communication subject.
:param sent_or_received: Sent or Received (default **Sent**).
:param sender: Communcation sender (default current user).
:param recipients: Communication recipients as list.
:param communication_medium: Medium of communication (default **Email**).
:param send_email: Send via email (default **False**).
:param print_html: HTML Print format to be sent as attachment.
:param print_format: Print Format name of parent document to be sent as attachment.
:param attachments: List of File names or dicts with keys "fname" and "fcontent"
:param send_me_a_copy: Send a copy to the sender (default **False**).
:param email_template: Template which is used to compose mail .
:param send_after: Send after the given datetime.
```
### `_make`
**Arguments:** `doctype, name, content, subject, sent_or_received, sender, sender_full_name, recipients, communication_medium, send_email, print_html, print_format, attachments, send_me_a_copy, cc, bcc, read_receipt, print_letterhead, email_template, communication_type, add_signature, send_after, print_language, now`
**Decorators:** ``

**Docstring:**
```
Internal method to make a new communication that ignores Permission checks.
```
### `validate_email`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Validate Email Addresses of Recipients and CC
```
### `set_incoming_outgoing_accounts`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `add_attachments`
**Arguments:** `name, attachments`
**Decorators:** ``

**Docstring:**
```
Add attachments to the given Communication

:param name: Communication name
:param attachments: File names or dicts with keys "fname" and "fcontent"
```
### `mark_email_as_seen`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `_mark_email_as_seen`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `update_communication_as_read`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```

