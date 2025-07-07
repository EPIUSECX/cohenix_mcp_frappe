# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/commands/test_commands.py`

## Classes

### `BaseTestCommands`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `execute` | `self, command, kwargs` | `classmethod` |  |
| `setup_test_site` | `cls` | `classmethod` |  |
| `_formatMessage` | `self, msg, standardMsg` | `` |  |


### `TestCommands`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_execute` | `self` | `` |  |
| `test_restore` | `self` | `` |  |
| `test_partial_restore` | `self` | `` |  |
| `test_recorder` | `self` | `` |  |
| `test_remove_from_installed_apps` | `self` | `` |  |
| `test_list_apps` | `self` | `` |  |
| `test_show_config` | `self` | `` |  |
| `test_get_bench_relative_path` | `self` | `` |  |
| `test_frappe_site_env` | `self` | `` |  |
| `test_version` | `self` | `` |  |
| `test_set_password` | `self` | `` |  |
| `test_bench_drop_site_should_archive_site` | `self` | `` |  |
| `test_force_install_app` | `self` | `` |  |
| `test_set_global_conf` | `self` | `` |  |
| `test_different_db_username` | `self` | `` |  |
| `test_existing_db_username` | `self` | `` |  |


### `TestBackups`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_backup_no_options` | `self` | `` | Take a backup without any options |
| `test_backup_extract_restore` | `self` | `` | Restore a backup after extracting |
| `test_old_backup_restore` | `self` | `` | Restore a backup after extracting |
| `test_backup_fails_with_exit_code` | `self` | `` | Provide incorrect options to check if exit code is 1 |
| `test_backup_with_files` | `self` | `` | Take a backup with files (--with-files) |
| `test_clear_log_table` | `self` | `` |  |
| `test_backup_with_custom_path` | `self` | `` | Backup to a custom path (--backup-path) |
| `test_backup_with_different_file_paths` | `self` | `` | Backup with different file paths (--backup-path-db, --backup-path-files, --backup-path-private-files, --backup-path-conf) |
| `test_backup_compress_files` | `self` | `` | Take a compressed backup (--compress) |
| `test_backup_verbose` | `self` | `` | Take a verbose backup (--verbose) |
| `test_backup_only_specific_doctypes` | `self` | `` | Take a backup with (include) backup options set in the site config `frappe.conf.backup.includes` |
| `test_backup_excluding_specific_doctypes` | `self` | `` | Take a backup with (exclude) backup options set (`frappe.conf.backup.excludes`, `--exclude`) |
| `test_selective_backup_priority_resolution` | `self` | `` | Take a backup with conflicting backup options set (`frappe.conf.excludes`, `--include`) |
| `test_dont_backup_conf` | `self` | `` | Take a backup ignoring frappe.conf.backup settings (with --ignore-backup-conf option) |


### `TestRemoveApp`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_delete_modules` | `self` | `` |  |
| `test_dry_run` | `self` | `` | Check if dry run in not destructive. |


### `TestSiteMigration`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_migrate_cli` | `self` | `` |  |


### `TestAddNewUser`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_create_user` | `self` | `` |  |


### `TestBenchBuild`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_build_assets_size_check` | `self` | `` |  |


### `TestDBUtils`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_db_add_index` | `self` | `` |  |


### `TestSchedulerUtils`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_ready_for_migrate` | `self` | `` |  |


### `TestCommandUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_bench_helper` | `self` | `` |  |


### `TestDBCli`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_db_cli` | `self` | `` |  |
| `test_db_cli_with_sql` | `self` | `` |  |


### `TestSchedulerCLI`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_scheduler_status` | `self` | `` |  |
| `test_scheduler_enable_disable` | `self` | `` |  |
| `test_scheduler_pause_resume` | `self` | `` |  |


### `TestCLIImplementation`
**Inherits:** `BaseTestCommands`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_missing_commands` | `self` | `` |  |


### `TestGunicornWorker`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `spawn_gunicorn` | `self, args` | `` |  |
| `kill_gunicorn` | `self` | `` |  |
| `test_gunicorn_ping_sync` | `self` | `` |  |
| `test_gunicorn_ping_gthread` | `self` | `` |  |
| `test_gunicorn_idle_cpu_usage` | `self` | `` |  |


### `TestRQWorker`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `spawn_rq` | `self, args, pool` | `` |  |
| `kill_rq` | `self` | `` |  |
| `get_total_usage` | `self` | `` |  |
| `test_rq_idle_cpu_usage` | `self` | `` |  |
| `test_rq_pool_idle_cpu_usage` | `self` | `` |  |





## Functions

### `clean`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```
Strip and convert bytes to str.
```
### `missing_in_backup`
**Arguments:** `doctypes, file`
**Decorators:** ``

**Docstring:**
```
Return list of missing doctypes in the backup.

Args:
        doctypes (list): List of DocTypes to be checked
        file (str): Path of the database file

Return:
        doctypes(list): doctypes that are missing in backup
```
### `exists_in_backup`
**Arguments:** `doctypes, file`
**Decorators:** ``

**Docstring:**
```
Check if the list of doctypes exist in the database.sql.gz file supplied.

Args:
        doctypes (list): List of DocTypes to be checked
        file (str): Path of the database file

Return True if all tables exist.
```
### `maintain_locals`
**Arguments:** ``
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `pass_test_context`
**Arguments:** `f`
**Decorators:** ``

**Docstring:**
```

```
### `cli`
**Arguments:** `cmd, args`
**Decorators:** `contextmanager`

**Docstring:**
```

```

