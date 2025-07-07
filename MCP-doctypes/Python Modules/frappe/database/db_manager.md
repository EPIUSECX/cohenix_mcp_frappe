# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/db_manager.py`

## Classes

### `DbManager`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, db` | `` | Pass root_conn here for access to all databases. |
| `get_current_host` | `self` | `` |  |
| `create_user` | `self, user, password, host` | `` |  |
| `delete_user` | `self, target, host` | `` |  |
| `create_database` | `self, target` | `` |  |
| `drop_database` | `self, target` | `` |  |
| `grant_all_privileges` | `self, target, user, host` | `` |  |
| `flush_privileges` | `self` | `` |  |
| `get_database_list` | `self` | `` |  |
| `restore_database` | `verbose, target, source, user, password` | `staticmethod` | Function to restore the given SQL file to the target database.
:param target: The database to restore to.
:param source: The SQL dump to restore
:param user: The database username
:param password: The database password
:return: Nothing |





## Functions

No top-level functions found in this file.
