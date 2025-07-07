# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_team/insights_team.py`

## Classes

### `InsightsTeam`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `on_change` | `self` | `` |  |
| `prevent_admin_team_deletion` | `self` | `` |  |
| `set_admin_roles` | `self` | `` |  |
| `get_members` | `self` | `` |  |
| `get_sources` | `self` | `` |  |
| `get_tables` | `self` | `` |  |
| `get_allowed_resources` | `self, resource_type` | `` |  |
| `get_allowed_sources` | `self` | `` |  |
| `get_allowed_tables` | `self` | `` |  |





## Functions

### `update_admin_team`
**Arguments:** `user, method`
**Decorators:** ``

**Docstring:**
```

```
### `clear_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_teams`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `admin_team_members`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_admin`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_allowed_resources_for_user`
**Arguments:** `resource_type, user`
**Decorators:** ``

**Docstring:**
```

```
### `_get_allowed_resources_for_user`
**Arguments:** `resource_type, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_filter`
**Arguments:** `resource_type, user`
**Decorators:** ``

**Docstring:**
```

```
### `check_data_source_permission`
**Arguments:** `source_name, user, raise_error`
**Decorators:** ``

**Docstring:**
```

```
### `check_table_permission`
**Arguments:** `data_source, table, user, raise_error`
**Decorators:** ``

**Docstring:**
```

```
### `get_table_restrictions`
**Arguments:** `data_source, table, user`
**Decorators:** ``

**Docstring:**
```

```
### `apply_table_restrictions`
**Arguments:** `table, data_source, table_name`
**Decorators:** ``

**Docstring:**
```

```
### `remove_admin_role`
**Arguments:** `users`
**Decorators:** ``

**Docstring:**
```

```
### `give_admin_role`
**Arguments:** `users`
**Decorators:** ``

**Docstring:**
```

```
### `has_admin_role`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

