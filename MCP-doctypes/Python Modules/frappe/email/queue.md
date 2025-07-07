# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/queue.py`

## Classes

No classes found in this file.


## Functions

### `get_emails_sent_this_month`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
Get count of emails sent from a specific email account.

:param email_account: name of the email account used to send mail

if email_account=None, email account filter is not applied while counting
```
### `get_emails_sent_today`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
Get count of emails sent from a specific email account.

:param email_account: name of the email account used to send mail

if email_account=None, email account filter is not applied while counting
```
### `get_unsubscribe_message`
**Arguments:** `unsubscribe_message, expose_recipients`
**Decorators:** ``

**Docstring:**
```

```
### `get_unsubcribed_url`
**Arguments:** `reference_doctype, reference_name, email, unsubscribe_method, unsubscribe_params`
**Decorators:** ``

**Docstring:**
```

```
### `unsubscribe`
**Arguments:** `doctype, name, email`
**Decorators:** ``

**Docstring:**
```

```
### `return_unsubscribed_page`
**Arguments:** `email, doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `flush`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
flush email queue, every time: called from scheduler.

This should not be called outside of background jobs.
```
### `get_queue`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

