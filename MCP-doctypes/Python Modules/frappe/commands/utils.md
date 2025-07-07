# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/commands/utils.py`

## Classes

No classes found in this file.


## Functions

### `build`
**Arguments:** `app, apps, hard_link, production, verbose, force, save_metafiles, using_cached`
**Decorators:** ``

**Docstring:**
```
Compile JS and CSS source files
```
### `watch`
**Arguments:** `apps`
**Decorators:** ``

**Docstring:**
```
Watch and compile JS and CSS files as and when they change
```
### `clear_cache`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Clear cache, doctype cache and defaults
```
### `clear_website_cache`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Clear website cache
```
### `destroy_all_sessions`
**Arguments:** `context, reason`
**Decorators:** `pass_context`

**Docstring:**
```
Clear sessions of all users (logs them out)
```
### `show_config`
**Arguments:** `context, format`
**Decorators:** `pass_context`

**Docstring:**
```
Print configuration file to STDOUT in specified format
```
### `reset_perms`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Reset permissions for all doctypes
```
### `execute`
**Arguments:** `context, method, args, kwargs, profile`
**Decorators:** `pass_context`

**Docstring:**
```
Execute a function
```
### `add_to_email_queue`
**Arguments:** `context, email_path`
**Decorators:** `pass_context`

**Docstring:**
```
Add an email to the Email Queue
```
### `export_doc`
**Arguments:** `context, doctype, docname`
**Decorators:** `pass_context`

**Docstring:**
```
Export a single document to csv
```
### `export_json`
**Arguments:** `context, doctype, path, name`
**Decorators:** `pass_context`

**Docstring:**
```
Export doclist as json to the given path, use '-' as name for Singles.
```
### `export_csv`
**Arguments:** `context, doctype, path`
**Decorators:** `pass_context`

**Docstring:**
```
Export data import template with data for DocType
```
### `export_fixtures`
**Arguments:** `context, app`
**Decorators:** `pass_context`

**Docstring:**
```
Export fixtures
```
### `import_doc`
**Arguments:** `context, path, force`
**Decorators:** `pass_context`

**Docstring:**
```
Import (insert/update) doclist. If the argument is a directory, all files ending with .json are imported
```
### `data_import`
**Arguments:** `context, file_path, doctype, import_type, submit_after_import, mute_emails`
**Decorators:** `pass_context`

**Docstring:**
```
Import documents in bulk from CSV or XLSX using data import
```
### `bulk_rename`
**Arguments:** `context, doctype, path`
**Decorators:** `pass_context`

**Docstring:**
```
Rename multiple records via CSV file
```
### `database`
**Arguments:** `context, extra_args`
**Decorators:** `pass_context`

**Docstring:**
```
Enter into the Database console for given site.
```
### `mariadb`
**Arguments:** `context, extra_args`
**Decorators:** `pass_context`

**Docstring:**
```
Enter into mariadb console for a given site.
```
### `postgres`
**Arguments:** `context, extra_args`
**Decorators:** `pass_context`

**Docstring:**
```
Enter into postgres console for a given site.
```
### `sqlite`
**Arguments:** `context, extra_args`
**Decorators:** `pass_context`

**Docstring:**
```
Enter into sqlite console for a given site.
```
### `_enter_console`
**Arguments:** `extra_args`
**Decorators:** ``

**Docstring:**
```

```
### `jupyter`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Start an interactive jupyter notebook
```
### `_console_cleanup`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `store_logs`
**Arguments:** `terminal`
**Decorators:** ``

**Docstring:**
```

```
### `console`
**Arguments:** `context, autoreload`
**Decorators:** `pass_context`

**Docstring:**
```
Start ipython console for a site
```
### `transform_database`
**Arguments:** `context, table, engine, row_format, failfast`
**Decorators:** `pass_context`

**Docstring:**
```
Transform site database through given parameters
```
### `serve`
**Arguments:** `context, port, profile, proxy, no_reload, no_threading, sites_path, site, with_coverage`
**Decorators:** `pass_context`

**Docstring:**
```
Start development web server
```
### `request`
**Arguments:** `context, args, path`
**Decorators:** `pass_context`

**Docstring:**
```
Run a request as an admin
```
### `make_app`
**Arguments:** `destination, app_name, no_git`
**Decorators:** ``

**Docstring:**
```
Creates a boilerplate app
```
### `create_patch`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Creates a new patch interactively
```
### `set_config`
**Arguments:** `context, key, value, global_, parse`
**Decorators:** `pass_context`

**Docstring:**
```
Insert/Update a value in site_config.json
```
### `get_version`
**Arguments:** `output`
**Decorators:** ``

**Docstring:**
```
Show the versions of all the installed apps.
```
### `rebuild_global_search`
**Arguments:** `context, static_pages`
**Decorators:** `pass_context`

**Docstring:**
```
Setup help table in the current site (called after migrate)
```
### `list_sites`
**Arguments:** `context, output_json`
**Decorators:** `pass_context`

**Docstring:**
```
List all the sites in current bench
```

