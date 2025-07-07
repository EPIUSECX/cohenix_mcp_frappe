# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_account/email_account.py`

## Classes

### `SentEmailInInbox`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `EmailAccount`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` | Set name as `email_account_name` or make title from Email Address. |
| `validate` | `self` | `` | Validate Email Address and check POP3/IMAP and SMTP connections is enabled. |
| `validate_frappe_mail_settings` | `self` | `` |  |
| `validate_smtp_conn` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_update` | `self` | `` | Check there is only one default of each type. |
| `clear_cache` | `self` | `` |  |
| `there_must_be_only_one_default` | `self` | `` | If current Email Account is default, un-default all other accounts. |
| `get_domain_values` | `self, domain` | `` |  |
| `get_incoming_server` | `self, in_receive, email_sync_rule` | `` | Return logged in POP3/IMAP connection object. |
| `check_email_server_connection` | `self, email_server, in_receive` | `` |  |
| `_password` | `self` | `property` |  |
| `default_sender` | `self` | `property` |  |
| `is_exists_in_db` | `self` | `` | Some of the Email Accounts we create from configs and those doesn't exists in DB.
This is is to check the specific email account exists in DB or not. |
| `from_record` | `cls, record` | `classmethod` |  |
| `find` | `cls, name` | `classmethod` |  |
| `find_one_by_filters` | `cls` | `classmethod` |  |
| `find_from_config` | `cls` | `classmethod` |  |
| `create_dummy` | `cls` | `classmethod` |  |
| `find_outgoing` | `cls, match_by_email, match_by_doctype, _raise_error` | `classmethod` | Find the outgoing Email account to use.

:param match_by_email: Find account using emailID
:param match_by_doctype: Find account by matching `Append To` doctype
:param _raise_error: This is used by raise_error_on_no_output decorator to raise error. |
| `find_default_outgoing` | `cls` | `classmethod` | Find default outgoing account. |
| `find_incoming` | `cls, match_by_email, match_by_doctype` | `classmethod` | Find the incoming Email account to use.
:param match_by_email: Find account using emailID
:param match_by_doctype: Find account by matching `Append To` doctype |
| `find_default_incoming` | `cls` | `classmethod` |  |
| `get_account_details_from_site_config` | `cls` | `classmethod` |  |
| `get_access_token` | `self` | `` |  |
| `sendmail_config` | `self` | `` |  |
| `get_smtp_server` | `self` | `` | Get SMTPServer (wrapper around actual smtplib object) for this account.

Implementation Detail: Since SMTPServer is same for each email connection, the same *instance*
is returned every time this function is called from same EmailAccount object.
This enables reusabilty of connection for better performance. |
| `_smtp_server_instance` | `self` | `` |  |
| `get_frappe_mail_client` | `self` | `` |  |
| `_frappe_mail_client` | `self` | `` |  |
| `remove_unpicklable_values` | `self, state` | `` |  |
| `handle_incoming_connect_error` | `self, description` | `` |  |
| `_disable_broken_incoming_account` | `self, description` | `` |  |
| `set_failed_attempts_count` | `self, value` | `` |  |
| `get_failed_attempts_count` | `self` | `` |  |
| `receive` | `self` | `` | Called by scheduler to receive emails from this EMail account using POP3/IMAP. |
| `get_inbound_mails` | `self` | `` | retrive and return inbound mails. |
| `handle_bad_emails` | `self, uid, raw, reason` | `` | Save the email in Unhandled Email doctype.

The excessive encoding and decoding is done to handle the case where the
email contains invalid characters. This should fail when parsing, not
when storing the email in the database. |
| `send_auto_reply` | `self, communication, email` | `` | Send auto reply if set. |
| `get_unreplied_notification_emails` | `self` | `` | Return list of emails listed |
| `on_trash` | `self` | `` | Clear communications where email account is linked |
| `after_rename` | `self, old, new, merge` | `` |  |
| `build_email_sync_rule` | `self` | `` |  |
| `check_automatic_linking_email_account` | `self` | `` |  |
| `append_email_to_sent_folder` | `self, message` | `` |  |
| `get_oauth_token` | `self` | `` |  |





## Functions

### `cache_email_account`
**Arguments:** `cache_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_append_to`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `notify_unreplied`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Sends email notifications if there are unreplied Communications
and `notify_if_unreplied` is set as true.
```
### `pull`
**Arguments:** `now`
**Decorators:** ``

**Docstring:**
```
Will be called via scheduler, pull emails from all enabled Email accounts.
```
### `pull_emails`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
Pull emails from given email account.
```
### `pull_from_email_account`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
Runs within a worker process
```
### `get_max_email_uid`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
get maximum uid of emails
```
### `setup_user_email_inbox`
**Arguments:** `email_account, awaiting_password, email_id, enable_outgoing, used_oauth`
**Decorators:** ``

**Docstring:**
```
setup email inbox for user
```
### `remove_user_email_inbox`
**Arguments:** `email_account`
**Decorators:** ``

**Docstring:**
```
remove user email inbox settings if email account is deleted
```
### `set_email_password`
**Arguments:** `email_account, password`
**Decorators:** ``

**Docstring:**
```

```
### `get_automatic_email_link`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

