# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/permissions.py`

## Classes

### `InsightsPermissions`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, user` | `` |  |
| `is_admin` | `self` | `cached_property` |  |
| `team_permissions_enabled` | `self` | `cached_property` |  |
| `get_permission_query_conditions` | `self, doctype` | `` |  |
| `_build_name_in_condition` | `self, doctype, items` | `` |  |
| `has_doc_permission` | `self, doc, ptype` | `` |  |
| `_get_ptype_access_docs_query` | `self, doctype, ptype` | `` | Returns a query to get docs with `ptype`  permission |
| `_get_ptype_access_workbooks_query` | `self, ptype` | `` |  |
| `_get_ptype_access_dashboards_query` | `self, ptype` | `` |  |
| `_get_ptype_access_charts_query` | `self, ptype` | `` |  |
| `_get_ptype_access_queries_query` | `self, ptype` | `` |  |
| `_get_ptype_access_alerts_query` | `self, ptype` | `` |  |





## Functions

### `has_doc_permission`
**Arguments:** `doc, ptype, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_query_conditions`
**Arguments:** `user, doctype`
**Decorators:** ``

**Docstring:**
```

```
### `check_app_permission`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

