# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/email_body.py`

## Classes

### `EMail`


**Docstring:**
```
Wrapper on the email module. Email object represents emails to be sent to the client.
Also provides a clean way to add binary `FileData` attachments
Also sets all messages as multipart/alternative for cleaner reading in text-only clients
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, sender, recipients, subject, alternative, reply_to, cc, bcc, email_account, expose_recipients, x_priority` | `` |  |
| `set_html` | `self, message, text_content, footer, print_html, formatted, inline_images, header` | `` | Attach message in the html portion of multipart/alternative |
| `set_text` | `self, message` | `` | Attach message in the text portion of multipart/alternative |
| `set_part_html` | `self, message, inline_images` | `` |  |
| `set_html_as_text` | `self, html` | `` | Set plain text from HTML |
| `set_message` | `self, message, mime_type, as_attachment, filename` | `` | Append the message with MIME content to the root node (as attachment) |
| `attach_file` | `self, n` | `` | attach a file from the `FileData` table |
| `add_attachment` | `self, fname, fcontent, content_type, parent, content_id, inline` | `` | add attachment |
| `add_pdf_attachment` | `self, name, html, options` | `` |  |
| `validate` | `self` | `` | validate the Email Addresses |
| `replace_sender` | `self` | `` |  |
| `replace_sender_name` | `self` | `` |  |
| `set_message_id` | `self, message_id, is_notification` | `` |  |
| `set_in_reply_to` | `self, in_reply_to` | `` | Used to send the Message-Id of a received email back as In-Reply-To |
| `add_headers` | `self, headers` | `` | Add custom headers to the email |
| `make` | `self` | `` | build into msg_root |
| `set_header` | `self, key, value` | `` |  |
| `as_string` | `self` | `` | validate, build message and convert to string |





## Functions

### `get_email`
**Arguments:** `recipients, sender, msg, subject, text_content, footer, print_html, formatted, attachments, content, reply_to, cc, bcc, email_account, expose_recipients, inline_images, header, x_priority`
**Decorators:** ``

**Docstring:**
```
Prepare an email with the following format:
- multipart/mixed
        - multipart/alternative
                - text/plain
                - multipart/related
                        - text/html
                        - inline image
                - attachment
```
### `get_formatted_html`
**Arguments:** `subject, message, footer, print_html, email_account, header, unsubscribe_link, sender, with_container`
**Decorators:** ``

**Docstring:**
```

```
### `get_email_html`
**Arguments:** `template, args, subject, header, with_container`
**Decorators:** ``

**Docstring:**
```

```
### `inline_style_in_html`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```
Convert email.css and html to inline-styled html.
```
### `add_attachment`
**Arguments:** `fname, fcontent, content_type, parent, content_id, inline`
**Decorators:** ``

**Docstring:**
```
Add attachment to parent which must an email object
```
### `get_message_id`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return Message ID created from doctype and name.
```
### `get_signature`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_footer`
**Arguments:** `email_account, footer`
**Decorators:** ``

**Docstring:**
```
append a footer (signature)
```
### `replace_filename_with_cid`
**Arguments:** `message`
**Decorators:** ``

**Docstring:**
```
Replaces <img embed="assets/frappe/images/filename.jpg" ...> with
<img src="cid:content_id" ...> and return the modified message and
a list of inline_images with {filename, filecontent, content_id}
```
### `get_filecontent_from_path`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `get_header`
**Arguments:** `header`
**Decorators:** ``

**Docstring:**
```
Build header from template
```
### `sanitize_email_header`
**Arguments:** `header`
**Decorators:** ``

**Docstring:**
```
Removes all line boundaries in the headers.

Email Policy (python's std) has some bugs in it which uses splitlines
and raises ValueError (ref: https://github.com/python/cpython/blob/main/Lib/email/policy.py#L143).
Hence removing all line boundaries while sanitization of headers to prevent such faliures.
The line boundaries which are removed can be found here: https://docs.python.org/3/library/stdtypes.html#str.splitlines
```
### `get_brand_logo`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```

```

