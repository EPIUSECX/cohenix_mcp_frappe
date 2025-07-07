# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/subscription_utils.py`

## Classes

No classes found in this file.


## Functions

### `get_add_on_details`
**Arguments:** `plan`
**Decorators:** ``

**Docstring:**
```
Returns the number of employees to be billed under add-ons for SAAS subscription
site_details = {
        "country": "India",
        "plan": "Basic",
        "credit_balance": 1000,
        "add_ons": {
                "employee": 2,
        },
        "expiry_date": "2021-01-01", # as per current usage
}
```
### `get_active_employees`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `subscription_updated`
**Arguments:** `app, plan`
**Decorators:** ``

**Docstring:**
```

```
### `update_erpnext_access`
**Arguments:** `user_input`
**Decorators:** ``

**Docstring:**
```
Called from hooks after setup wizard completion, ignored if user has no hrms subscription
enables erpnext workspaces and roles if user has subscribed to both hrms and erpnext
disables erpnext workspaces and roles if user has subscribed to hrms but not erpnext
```
### `update_erpnext_workspaces`
**Arguments:** `disable`
**Decorators:** ``

**Docstring:**
```

```
### `update_erpnext_roles`
**Arguments:** `disable`
**Decorators:** ``

**Docstring:**
```

```
### `set_app_logo`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_erpnext_roles`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_roles_for_app`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_modules_by_app`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_doctypes_by_modules`
**Arguments:** `modules`
**Decorators:** ``

**Docstring:**
```

```
### `roles_by_doctype`
**Arguments:** `doctypes`
**Decorators:** ``

**Docstring:**
```

```
### `hide_erpnext`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_subscription`
**Arguments:** `secret_key`
**Decorators:** ``

**Docstring:**
```

```

