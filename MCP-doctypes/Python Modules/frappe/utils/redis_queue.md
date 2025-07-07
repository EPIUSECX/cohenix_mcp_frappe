# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/redis_queue.py`

## Classes

### `RedisQueue`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, conn` | `` |  |
| `add_user` | `self, username, password` | `` | Create or update the user. |
| `get_connection` | `cls, username, password` | `classmethod` |  |
| `new` | `cls, username, password` | `classmethod` |  |
| `set_admin_password` | `cls, cur_password, new_password, reset_passwords` | `classmethod` |  |
| `get_new_user_settings` | `cls, username, password` | `classmethod` |  |
| `get_acl_key_rules` | `cls, include_key_prefix` | `classmethod` | FIXME: Find better way |
| `get_acl_command_rules` | `cls` | `classmethod` |  |
| `gen_acl_list` | `cls, set_admin_password` | `classmethod` | Generate list of ACL users needed for this branch.

This list contains default ACL user and the bench ACL user(used by all sites incase of ACL is enabled). |





## Functions

No top-level functions found in this file.
