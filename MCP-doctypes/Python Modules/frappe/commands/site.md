# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/commands/site.py`

## Classes

No classes found in this file.


## Functions

### `new_site`
**Arguments:** `site, db_root_username, db_root_password, admin_password, verbose, source_sql, force, no_mariadb_socket, mariadb_user_host_login_scope, install_app, db_name, db_password, db_type, db_socket, db_host, db_port, db_user, set_default, setup_db`
**Decorators:** ``

**Docstring:**
```
Create a new site
```
### `restore`
**Arguments:** `context, sql_file_path, encryption_key, db_root_username, db_root_password, db_name, verbose, install_app, admin_password, force, with_public_files, with_private_files`
**Decorators:** `pass_context`

**Docstring:**
```
Restore site database from an sql file
```
### `_restore`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `restore_backup`
**Arguments:** `sql_file_path, site, db_root_username, db_root_password, verbose, install_app, admin_password, force`
**Decorators:** ``

**Docstring:**
```

```
### `partial_restore`
**Arguments:** `context, sql_file_path, verbose, encryption_key`
**Decorators:** `pass_context`

**Docstring:**
```

```
### `reinstall`
**Arguments:** `context, admin_password, db_root_username, db_root_password, yes`
**Decorators:** `pass_context`

**Docstring:**
```
Reinstall site ie. wipe all data and start over
```
### `_reinstall`
**Arguments:** `site, admin_password, db_root_username, db_root_password, yes, verbose`
**Decorators:** ``

**Docstring:**
```

```
### `install_app`
**Arguments:** `context, apps, force`
**Decorators:** `pass_context`

**Docstring:**
```
Install a new app to site, supports multiple apps
```
### `list_apps`
**Arguments:** `context, format`
**Decorators:** `pass_context`

**Docstring:**
```
List apps in site.
```
### `add_db_index`
**Arguments:** `context, doctype, column`
**Decorators:** `pass_context`

**Docstring:**
```
Adds a new DB index and creates a property setter to persist it.
```
### `describe_database_table`
**Arguments:** `context, doctype, column`
**Decorators:** `pass_context`

**Docstring:**
```
Describes various statistics about the table.
This is useful to build integration like
This includes:
1. Schema
2. Indexes
3. stats - total count of records
4. if column is specified then extra stats are generated for column:
        Distinct values count in column
```
### `add_system_manager`
**Arguments:** `context, email, first_name, last_name, send_welcome_email, password`
**Decorators:** `pass_context`

**Docstring:**
```
Add a new system manager to a site
```
### `add_user_for_sites`
**Arguments:** `context, email, first_name, last_name, user_type, send_welcome_email, password, add_role`
**Decorators:** `pass_context`

**Docstring:**
```
Add user to a site
```
### `disable_user`
**Arguments:** `context, email`
**Decorators:** `pass_context`

**Docstring:**
```
Disable a user account on site.
```
### `migrate`
**Arguments:** `context, skip_failing, skip_search_index`
**Decorators:** `pass_context`

**Docstring:**
```
Run patches, sync schema and rebuild files/translations
```
### `migrate_to`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Migrates site to the specified provider
```
### `run_patch`
**Arguments:** `context, module, force`
**Decorators:** `pass_context`

**Docstring:**
```
Run a particular patch
```
### `reload_doc`
**Arguments:** `context, module, doctype, docname`
**Decorators:** `pass_context`

**Docstring:**
```
Reload schema for a DocType
```
### `reload_doctype`
**Arguments:** `context, doctype`
**Decorators:** `pass_context`

**Docstring:**
```
Reload schema for a DocType
```
### `add_to_hosts`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Add site to hosts
```
### `_use`
**Arguments:** `site, sites_path`
**Decorators:** ``

**Docstring:**
```
Set a default site
```
### `use`
**Arguments:** `site, sites_path`
**Decorators:** ``

**Docstring:**
```

```
### `backup`
**Arguments:** `context, with_files, backup_path, backup_path_db, backup_path_files, backup_path_private_files, backup_path_conf, ignore_backup_conf, verbose, compress, include, exclude, old_backup_metadata`
**Decorators:** `pass_context`

**Docstring:**
```
Backup
```
### `remove_from_installed_apps`
**Arguments:** `context, app`
**Decorators:** `pass_context`

**Docstring:**
```
Remove app from site's installed-apps list
```
### `uninstall`
**Arguments:** `context, app, dry_run, yes, no_backup, force`
**Decorators:** `pass_context`

**Docstring:**
```
Remove app and linked modules from site
```
### `drop_site`
**Arguments:** `site, db_root_username, db_root_password, archived_sites_path, force, no_backup`
**Decorators:** ``

**Docstring:**
```
Remove a site from database and filesystem.
```
### `_drop_site`
**Arguments:** `site, db_root_username, db_root_password, archived_sites_path, force, no_backup`
**Decorators:** ``

**Docstring:**
```

```
### `move`
**Arguments:** `dest_dir, site`
**Decorators:** ``

**Docstring:**
```

```
### `set_password`
**Arguments:** `context, user, password, logout_all_sessions`
**Decorators:** `pass_context`

**Docstring:**
```
Set password for a user on a site
```
### `set_admin_password`
**Arguments:** `context, admin_password, logout_all_sessions`
**Decorators:** `pass_context`

**Docstring:**
```
Set Administrator password for a site
```
### `set_user_password`
**Arguments:** `site, user, password, logout_all_sessions`
**Decorators:** ``

**Docstring:**
```

```
### `set_last_active_for_user`
**Arguments:** `context, user`
**Decorators:** `pass_context`

**Docstring:**
```
Set users last active date to current datetime
```
### `publish_realtime`
**Arguments:** `context, event, message, room, user, doctype, docname, after_commit`
**Decorators:** `pass_context`

**Docstring:**
```
Publish realtime event from bench
```
### `browse`
**Arguments:** `context, site, user, session_end, user_for_audit`
**Decorators:** `pass_context`

**Docstring:**
```
Opens the site on web browser
```
### `start_recording`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Start Frappe Recorder.
```
### `stop_recording`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Stop Frappe Recorder.
```
### `start_ngrok`
**Arguments:** `context, bind_tls, use_default_authtoken`
**Decorators:** `pass_context`

**Docstring:**
```
Start a ngrok tunnel to your local development server.
```
### `build_search_index`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Rebuild search index used by global search.
```
### `clear_log_table`
**Arguments:** `context, doctype, days, no_backup`
**Decorators:** `pass_context`

**Docstring:**
```
If any logtype table grows too large then clearing it with DELETE query
is not feasible in reasonable time. This command copies recent data to new
table and replaces current table with new smaller table.


ref: https://mariadb.com/kb/en/big-deletes/#deleting-more-than-half-a-table
```
### `trim_database`
**Arguments:** `context, dry_run, format, no_backup, yes`
**Decorators:** `pass_context`

**Docstring:**
```
Remove database tables for deleted DocTypes.
```
### `get_standard_tables`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `trim_tables`
**Arguments:** `context, dry_run, format, no_backup`
**Decorators:** `pass_context`

**Docstring:**
```
Remove columns from tables where fields are deleted from doctypes.
```
### `handle_data`
**Arguments:** `data, format`
**Decorators:** ``

**Docstring:**
```

```
### `add_new_user`
**Arguments:** `email, first_name, last_name, user_type, send_welcome_email, password, role`
**Decorators:** ``

**Docstring:**
```

```
### `ensure_app_not_frappe`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Ensure that the app name passed is not 'frappe'

:param app: Name of the app
:return: Nothing
```
### `bypass_patch`
**Arguments:** `context, patch_name, yes`
**Decorators:** `pass_context`

**Docstring:**
```
Bypass a patch permanently instead of migrating using the --skip-failing flag.
```

