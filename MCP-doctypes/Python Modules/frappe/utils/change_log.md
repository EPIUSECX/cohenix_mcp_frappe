# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/change_log.py`

## Classes

No classes found in this file.


## Functions

### `get_change_log`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_change_log_for_app`
**Arguments:** `app, from_version, to_version`
**Decorators:** ``

**Docstring:**
```

```
### `update_last_known_versions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_versions`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get versions of all installed apps.

Example:

        {
                "frappe": {
                        "title": "Frappe Framework",
                        "version": "5.0.0"
                }
        }
```
### `get_app_branch`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Return branch of an app.
```
### `get_app_last_commit_ref`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `check_for_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_app_update_notifications`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `parse_latest_non_beta_release`
**Arguments:** `response, current_version`
**Decorators:** ``

**Docstring:**
```
Parse the response JSON for all the releases and return the latest non prerelease.

Args:

response (list): response object returned by github

Return a json object pertaining to the latest non-beta release
```
### `check_release_on_github`
**Arguments:** `owner, repo, current_version`
**Decorators:** ``

**Docstring:**
```
Check the latest release for a repo URL on GitHub.
```
### `security_issues_count`
**Arguments:** `owner, repo, current_version, target_version`
**Decorators:** ``

**Docstring:**
```

```
### `_get_latest_releases`
**Arguments:** `owner, repo`
**Decorators:** ``

**Docstring:**
```

```
### `_get_security_issues`
**Arguments:** `owner, repo`
**Decorators:** ``

**Docstring:**
```

```
### `parse_github_url`
**Arguments:** `remote_url`
**Decorators:** ``

**Docstring:**
```
Parse the remote URL to get the owner and repo name.
```
### `get_source_url`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Get the remote URL of the app.
```
### `add_message_to_redis`
**Arguments:** `update_json`
**Decorators:** ``

**Docstring:**
```

```
### `show_update_popup`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_pyproject`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```

