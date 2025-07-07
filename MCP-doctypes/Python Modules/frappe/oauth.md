# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/oauth.py`

## Classes

### `OAuthWebRequestValidator`
**Inherits:** `RequestValidator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate_client_id` | `self, client_id, request` | `` |  |
| `validate_redirect_uri` | `self, client_id, redirect_uri, request` | `` |  |
| `get_default_redirect_uri` | `self, client_id, request` | `` |  |
| `validate_scopes` | `self, client_id, scopes, client, request` | `` |  |
| `get_default_scopes` | `self, client_id, request` | `` |  |
| `validate_response_type` | `self, client_id, response_type, client, request` | `` |  |
| `save_authorization_code` | `self, client_id, code, request` | `` |  |
| `authenticate_client` | `self, request` | `` |  |
| `authenticate_client_id` | `self, client_id, request` | `` |  |
| `validate_code` | `self, client_id, code, client, request` | `` |  |
| `confirm_redirect_uri` | `self, client_id, code, redirect_uri, client` | `` |  |
| `validate_grant_type` | `self, client_id, grant_type, client, request` | `` |  |
| `save_bearer_token` | `self, token, request` | `` |  |
| `invalidate_authorization_code` | `self, client_id, code, request` | `` |  |
| `validate_bearer_token` | `self, token, scopes, request` | `` |  |
| `get_original_scopes` | `self, refresh_token, request` | `` |  |
| `revoke_token` | `self, token, token_type_hint, request` | `` | Revoke an access or refresh token.

:param token: The token string.
:param token_type_hint: access_token or refresh_token.
:param request: The HTTP Request (oauthlib.common.Request)

Method is used by:
- Revocation Endpoint |
| `validate_refresh_token` | `self, refresh_token, client, request` | `` | Ensure the Bearer token is valid and authorized access to scopes.

OBS! The request.user attribute should be set to the resource owner
associated with this refresh token.

:param refresh_token: Unicode refresh token
:param client: Client object set by you, see authenticate_client.
:param request: The HTTP Request (oauthlib.common.Request)
:rtype: True or False

Method is used by:
- Authorization Code Grant (indirectly by issuing refresh tokens)
- Resource Owner Password Credentials Grant (also indirectly)
- Refresh Token Grant |
| `finalize_id_token` | `self, id_token, token, token_handler, request` | `` |  |
| `get_authorization_code_nonce` | `self, client_id, code, redirect_uri, request` | `` |  |
| `get_authorization_code_scopes` | `self, client_id, code, redirect_uri, request` | `` |  |
| `get_jwt_bearer_token` | `self, token, token_handler, request` | `` |  |
| `get_userinfo_claims` | `self, request` | `` |  |
| `validate_id_token` | `self, token, scopes, request` | `` |  |
| `validate_jwt_bearer_token` | `self, token, scopes, request` | `` |  |
| `validate_silent_authorization` | `self, request` | `` | Ensure the logged in user has authorized silent OpenID authorization.

Silent OpenID authorization allows access tokens and id tokens to be
granted to clients without any user prompt or interaction.

:param request: The HTTP Request (oauthlib.common.Request)
:rtype: True or False

Method is used by:
- OpenIDConnectAuthCode
- OpenIDConnectImplicit
- OpenIDConnectHybrid |
| `validate_silent_login` | `self, request` | `` | Ensure session user has authorized silent OpenID login.

If no user is logged in or has not authorized silent login, this
method should return False.

If the user is logged in but associated with multiple accounts and
not selected which one to link to the token then this method should
raise an oauthlib.oauth2.AccountSelectionRequired error.

:param request: The HTTP Request (oauthlib.common.Request)
:rtype: True or False

Method is used by:
- OpenIDConnectAuthCode
- OpenIDConnectImplicit
- OpenIDConnectHybrid |
| `validate_user_match` | `self, id_token_hint, scopes, claims, request` | `` | Ensure client supplied user id hint matches session user.

If the sub claim or id_token_hint is supplied then the session
user must match the given ID.

:param id_token_hint: User identifier string.
:param scopes: List of OAuth 2 scopes and OpenID claims (strings).
:param claims: OpenID Connect claims dict.
:param request: The HTTP Request (oauthlib.common.Request)
:rtype: True or False

Method is used by:
- OpenIDConnectAuthCode
- OpenIDConnectImplicit
- OpenIDConnectHybrid |
| `validate_user` | `self, username, password, client, request` | `` | Ensure the username and password is valid.

Method is used by:
- Resource Owner Password Credentials Grant |





## Functions

### `get_cookie_dict_from_headers`
**Arguments:** `r`
**Decorators:** ``

**Docstring:**
```

```
### `calculate_at_hash`
**Arguments:** `access_token, hash_alg`
**Decorators:** ``

**Docstring:**
```
Helper method for calculating an access token
hash, as described in http://openid.net/specs/openid-connect-core-1_0.html#CodeIDToken
Its value is the base64url encoding of the left-most half of the hash of the octets
of the ASCII representation of the access_token value, where the hash algorithm
used is the hash algorithm used in the alg Header Parameter of the ID Token's JOSE
Header. For instance, if the alg is RS256, hash the access_token value with SHA-256,
then take the left-most 128 bits and base64url encode them. The at_hash value is a
case sensitive string.
Args:
access_token (str): An access token string.
hash_alg (callable): A callable returning a hash object, e.g. hashlib.sha256
```
### `delete_oauth2_data`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_client_scopes`
**Arguments:** `client_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_userinfo`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_url_delimiter`
**Arguments:** `separator_character`
**Decorators:** ``

**Docstring:**
```

```
### `generate_json_error_response`
**Arguments:** `e`
**Decorators:** ``

**Docstring:**
```

```
### `get_server_url`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

