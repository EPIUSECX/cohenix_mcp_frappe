# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/backups.py`

## Classes

### `BackupGenerator`


**Docstring:**
```
This class contains methods to perform On Demand Backup

To initialize, specify (db_name, user, password, db_file_name=None, db_host="127.0.0.1")
If specifying db_file_name, also append ".sql.gz"
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, db_name, user, password, backup_path, backup_path_db, backup_path_files, backup_path_private_files, db_socket, db_host, db_port, db_type, backup_path_conf, ignore_conf, compress_files, include_doctypes, exclude_doctypes, verbose, old_backup_metadata, rollback_callback` | `` |  |
| `setup_backup_directory` | `self` | `` |  |
| `_set_existing_tables` | `self` | `` | Ensure self._existing_tables is set. |
| `setup_backup_tables` | `self` | `` | Set self.backup_includes, self.backup_excludes based on include_doctypes, exclude_doctypes |
| `set_backup_tables_from_config` | `self` | `` | Set self.backup_includes, self.backup_excludes based on site config |
| `site_config_backup_path` | `self` | `property` |  |
| `get_backup` | `self, older_than, ignore_files, force` | `` | Takes a new dump if existing file is old
and sends the link to the file as email |
| `set_backup_file_name` | `self` | `` |  |
| `backup_encryption` | `self` | `` | Encrypt all the backups created using gpg. |
| `get_recent_backup` | `self, older_than, partial` | `` |  |
| `zip_files` | `self` | `` |  |
| `get_summary` | `self` | `` |  |
| `print_summary` | `self` | `` |  |
| `backup_files` | `self` | `` |  |
| `copy_site_config` | `self` | `` |  |
| `take_dump` | `self` | `` |  |
| `send_email` | `self` | `` | Sends the link to backup file located at erpnext/backups |
| `add_to_rollback` | `self, func` | `` | Adds the given callable to the rollback CallbackManager stack

:param func: The callable to add to the rollback stack
:return: Nothing |
| `delete_if_step_fails` | `self, step` | `` | Deletes the given path if the given step fails

:param step: The step to execute
:param paths: The paths to delete
:return: Nothing |





## Functions

### `_get_tables`
**Arguments:** `doctypes, existing_tables`
**Decorators:** ``

**Docstring:**
```
Return a list of tables for the given doctypes that exist in the database.
```
### `fetch_latest_backups`
**Arguments:** `partial`
**Decorators:** ``

**Docstring:**
```
Fetch paths of the latest backup taken in the last 30 days.

Note: Only for System Managers

Return:
        dict: relative Backup Paths
```
### `scheduled_backup`
**Arguments:** `older_than, ignore_files, backup_path, backup_path_db, backup_path_files, backup_path_private_files, backup_path_conf, ignore_conf, include_doctypes, exclude_doctypes, compress, force, verbose, old_backup_metadata, rollback_callback`
**Decorators:** ``

**Docstring:**
```
this function is called from scheduler
deletes backups older than 7 days
takes backup
```
### `new_backup`
**Arguments:** `older_than, ignore_files, backup_path, backup_path_db, backup_path_files, backup_path_private_files, backup_path_conf, ignore_conf, include_doctypes, exclude_doctypes, compress, force, verbose, old_backup_metadata, rollback_callback`
**Decorators:** ``

**Docstring:**
```

```
### `delete_temp_backups`
**Arguments:** `older_than`
**Decorators:** ``

**Docstring:**
```
Cleans up the backup_link_path directory by deleting older files
```
### `is_file_old`
**Arguments:** `file_path, older_than`
**Decorators:** ``

**Docstring:**
```
Return True if file exists and is older than specified hours.
```
### `get_backup_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_backup_encryption_key`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_or_generate_backup_encryption_key`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `decrypt_backup`
**Arguments:** `file_path, passphrase`
**Decorators:** ``

**Docstring:**
```

```
### `backup`
**Arguments:** `with_files, backup_path_db, backup_path_files, backup_path_private_files, backup_path_conf`
**Decorators:** ``

**Docstring:**
```
Backup
```

