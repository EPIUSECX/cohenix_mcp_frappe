# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/migrate.py`

## Classes

### `SiteMigration`


**Docstring:**
```
Migrate all apps to the current version, will:
- run before migrate hooks
- run patches
- sync doctypes (schema)
- sync dashboards
- sync jobs
- sync fixtures
- sync customizations
- sync languages
- sync web pages (from /www)
- run after migrate hooks
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, skip_failing, skip_search_index` | `` |  |
| `setUp` | `self` | `` | Complete setup required for site migration |
| `tearDown` | `self` | `` | Run operations that should be run post schema updation processes
This should be executed irrespective of outcome |
| `pre_schema_updates` | `self` | `atomic` | Executes `before_migrate` hooks |
| `run_schema_updates` | `self` | `atomic` | Run patches as defined in patches.txt, sync schema changes as defined in the {doctype}.json files |
| `post_schema_updates` | `self` | `atomic` | Execute pending migration tasks post patches execution & schema sync
This includes:
* Sync `Scheduled Job Type` and scheduler events defined in hooks
* Sync fixtures & custom scripts
* Sync in-Desk Module Dashboards
* Sync customizations: Custom Fields, Property Setters, Custom Permissions
* Sync Frappe's internal language master
* Flush deferred inserts made during maintenance mode.
* Sync Portal Menu Items
* Sync Installed Applications Version History
* Execute `after_migrate` hooks |
| `required_services_running` | `self` | `` | Return True if all required services are running. Return False and print
instructions to stdout when required services are not available. |
| `lower_lock_timeout` | `self` | `` | Lower timeout for table metadata locks, default is 1 day, reduce it to 5 minutes.

This is required to avoid indefinitely waiting for metadata lock. |
| `kill_idle_connections` | `self, idle_limit` | `` | Assuming migrate has highest priority, kill everything else.

If someone has connected to mariadb using DB console or ipython console and then acquired
certain locks we won't be able to migrate. |
| `run` | `self, site` | `` | Run Migrate operation on site specified. This method initializes
and destroys connections to the site database. |





## Functions

### `atomic`
**Arguments:** `method`
**Decorators:** ``

**Docstring:**
```

```

