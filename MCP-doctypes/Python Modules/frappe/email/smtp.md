# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/smtp.py`

## Classes

### `InvalidEmailCredentials`


**Docstring:**
```

```

**Methods:**
No methods found.

### `SMTPServer`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, server, login, email_account, password, port, use_tls, use_ssl, use_oauth, access_token` | `` |  |
| `port` | `self` | `property` |  |
| `server` | `self` | `property` |  |
| `secure_session` | `self, conn` | `` | Secure the connection incase of TLS. |
| `session` | `self` | `property` | Get SMTP session.

We make best effort to revive connection if it's disconnected by checking the connection
health before returning it to user. |
| `_enqueue_connection_closure` | `self` | `` |  |
| `is_session_active` | `self` | `` |  |
| `quit` | `self` | `` |  |
| `throw_invalid_credentials_exception` | `cls` | `classmethod` |  |





## Functions

No top-level functions found in this file.
