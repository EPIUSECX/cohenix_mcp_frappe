# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/frappemail.py`

## Classes

### `FrappeMail`


**Docstring:**
```
Class to interact with the Frappe Mail API.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, site, email, api_key, api_secret, access_token` | `` |  |
| `get_client` | `site, email, api_key, api_secret, access_token` | `staticmethod` | Returns a FrappeClient or FrappeOAuth2Client instance. |
| `request` | `self, method, endpoint, params, data, json, files, headers, timeout` | `` | Makes a request to the Frappe Mail API. |
| `validate` | `self` | `` | Validates if the user is allowed to send or receive emails. |
| `send_raw` | `self, sender, recipients, message, is_newsletter` | `` | Sends an email using the Frappe Mail API. |
| `pull_raw` | `self, limit, last_synced_at` | `` | Pulls emails for the email using the Frappe Mail API. |





## Functions

### `add_or_update_tzinfo`
**Arguments:** `date_time, timezone`
**Decorators:** ``

**Docstring:**
```
Adds or updates timezone to the datetime.
```

