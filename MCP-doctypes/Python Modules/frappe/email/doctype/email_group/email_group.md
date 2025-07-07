# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/email_group/email_group.py`

## Classes

### `EmailGroup`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `import_from` | `self, doctype` | `` | Extract Email Addresses from given doctype and add them to the current list |
| `update_total_subscribers` | `self` | `` |  |
| `get_total_subscribers` | `self` | `` |  |
| `preview_welcome_url` | `self, email` | `` | Get Welcome URL for the email group. |
| `get_welcome_url` | `self, email` | `` | Get Welcome URL for the email group. |
| `on_trash` | `self` | `` |  |





## Functions

### `import_from`
**Arguments:** `name, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `add_subscribers`
**Arguments:** `name, email_list`
**Decorators:** ``

**Docstring:**
```

```
### `send_welcome_email`
**Arguments:** `welcome_email, email, email_group`
**Decorators:** ``

**Docstring:**
```
Send welcome email for the subscribers of a given email group.
```
### `add_query_params`
**Arguments:** `url, params`
**Decorators:** ``

**Docstring:**
```

```

