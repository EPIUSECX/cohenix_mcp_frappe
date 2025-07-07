# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/installer.py`

## Classes

No classes found in this file.


## Functions

### `_is_scheduler_enabled`
**Arguments:** `site`
**Decorators:** ``

**Docstring:**
```

```
### `_new_site`
**Arguments:** `db_name, site, db_root_username, db_root_password, admin_password, verbose, install_apps, source_sql, force, db_password, db_type, db_socket, db_host, db_port, db_user, setup_db, rollback_callback, mariadb_user_host_login_scope`
**Decorators:** ``

**Docstring:**
```
Install a new Frappe site
```
### `install_db`
**Arguments:** `root_login, root_password, db_name, source_sql, admin_password, verbose, force, site_config, db_password, db_type, db_socket, db_host, db_port, db_user, setup, rollback_callback, mariadb_user_host_login_scope`
**Decorators:** ``

**Docstring:**
```

```
### `find_org`
**Arguments:** `org_repo`
**Decorators:** ``

**Docstring:**
```
find the org a repo is in

find_org()
ref -> https://github.com/frappe/bench/blob/develop/bench/utils/__init__.py#L390

:param org_repo:
:type org_repo: str

:raises InvalidRemoteException: if the org is not found

:return: organisation and repository
:rtype: Tuple[str, str]
```
### `fetch_details_from_tag`
**Arguments:** `_tag`
**Decorators:** ``

**Docstring:**
```
parse org, repo, tag from string

fetch_details_from_tag()
ref -> https://github.com/frappe/bench/blob/develop/bench/utils/__init__.py#L403

:param _tag: input string
:type _tag: str

:return: organisation, repostitory, tag
:rtype: Tuple[str, str, str]
```
### `parse_app_name`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
parse repo name from name

__setup_details_from_git()
ref -> https://github.com/frappe/bench/blob/develop/bench/app.py#L114


:param name: git tag
:type name: str

:return: repository name
:rtype: str
```
### `install_app`
**Arguments:** `name, verbose, set_as_patched, force`
**Decorators:** ``

**Docstring:**
```

```
### `add_to_installed_apps`
**Arguments:** `app_name, rebuild_website`
**Decorators:** ``

**Docstring:**
```

```
### `remove_from_installed_apps`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `remove_app`
**Arguments:** `app_name, dry_run, yes, no_backup, force`
**Decorators:** ``

**Docstring:**
```
Remove app and all linked to the app's module with the app from a site.
```
### `_delete_modules`
**Arguments:** `modules, dry_run`
**Decorators:** ``

**Docstring:**
```
Delete modules belonging to the app and all related doctypes.

Note: All record linked linked to Module Def are also deleted.

Return: list of deleted doctypes.
```
### `_delete_linked_documents`
**Arguments:** `module_name, doctype_linkfield_map, dry_run`
**Decorators:** ``

**Docstring:**
```
Deleted all records linked with module def
```
### `_get_module_linked_doctype_field_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get all the doctypes which have module linked with them.

Return ordered dictionary with doctype->link field mapping.
```
### `_delete_doctypes`
**Arguments:** `doctypes, dry_run`
**Decorators:** ``

**Docstring:**
```

```
### `post_install`
**Arguments:** `rebuild_website`
**Decorators:** ``

**Docstring:**
```

```
### `set_all_patches_as_completed`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `init_singles`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `make_conf`
**Arguments:** `db_name, db_password, site_config, db_type, db_socket, db_host, db_port, db_user`
**Decorators:** ``

**Docstring:**
```

```
### `make_site_config`
**Arguments:** `db_name, db_password, site_config, db_type, db_socket, db_host, db_port, db_user`
**Decorators:** ``

**Docstring:**
```

```
### `update_site_config`
**Arguments:** `key, value, validate, site_config_path`
**Decorators:** ``

**Docstring:**
```
Update a value in site_config
```
### `_update_config_file`
**Arguments:** `key, value, config_file`
**Decorators:** ``

**Docstring:**
```
Updates site or common config
```
### `get_site_config_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_conf_params`
**Arguments:** `db_name, db_password`
**Decorators:** ``

**Docstring:**
```

```
### `make_site_dirs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_module_defs`
**Arguments:** `app, ignore_if_duplicate`
**Decorators:** ``

**Docstring:**
```

```
### `remove_missing_apps`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `convert_archive_content`
**Arguments:** `sql_file_path`
**Decorators:** ``

**Docstring:**
```

```
### `_guess_mariadb_version`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `extract_files`
**Arguments:** `site_name, file_path`
**Decorators:** ``

**Docstring:**
```

```
### `is_downgrade`
**Arguments:** `sql_file_path, verbose`
**Decorators:** ``

**Docstring:**
```
Check if input db backup will get downgraded on current bench

This function is only tested with mariadb.
TODO: Add postgres support
```
### `get_old_backup_version`
**Arguments:** `sql_file_path`
**Decorators:** ``

**Docstring:**
```
Return the frappe version used to create the specified database dump.

This methods supports older versions of Frappe wich used a different format.
```
### `get_backup_version`
**Arguments:** `sql_file_path`
**Decorators:** ``

**Docstring:**
```
Return the frappe version used to create the specified database dump.
```
### `is_partial`
**Arguments:** `sql_file_path`
**Decorators:** ``

**Docstring:**
```
Function to return whether the database dump is a partial backup or not

:param sql_file_path: path to the database dump file
:return: True if the database dump is a partial backup, False otherwise
```
### `partial_restore`
**Arguments:** `sql_file_path, verbose`
**Decorators:** ``

**Docstring:**
```

```
### `validate_database_sql`
**Arguments:** `path, _raise`
**Decorators:** ``

**Docstring:**
```
Check if file has contents and if `__Auth` table exists

Args:
        path (str): Path of the decompressed SQL file
        _raise (bool, optional): Raise exception if invalid file. Defaults to True.
```
### `get_db_dump_header`
**Arguments:** `file_path, file_bytes`
**Decorators:** ``

**Docstring:**
```
Get the header of a database dump file

:param file_path: path to the database dump file
:param file_bytes: number of bytes to read from the file
:return: The first few bytes of the file as requested
```

