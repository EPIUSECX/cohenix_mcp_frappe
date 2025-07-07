# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/connected_app/connected_app.py`

## Classes

### `ConnectedApp`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `get_oauth2_session` | `self, user, init` | `` | Return an auto-refreshing OAuth2 session which is an extension of a requests.Session() |
| `initiate_web_application_flow` | `self, user, success_uri` | `` | Return an authorization URL for the user. Save state in Token Cache. |
| `get_user_token` | `self, user, success_uri` | `` | Return an existing user token or initiate a Web Application Flow. |
| `get_token_cache` | `self, user` | `` |  |
| `get_scopes` | `self` | `` |  |
| `get_query_params` | `self` | `` |  |
| `get_active_token` | `self, user` | `` |  |
| `get_backend_app_token` | `self, include_client_id` | `` | Get an Access Token for the Cloud-Registered Service Principal |





## Functions

### `callback`
**Arguments:** `code, state`
**Decorators:** ``

**Docstring:**
```
Handle client's code.

Called during the oauthorization flow by the remote oAuth2 server to
transmit a code that can be used by the local server to obtain an access
token.
```
### `has_token`
**Arguments:** `connected_app, connected_user`
**Decorators:** ``

**Docstring:**
```

```

