# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/modules/import_file.py`

## Classes

No classes found in this file.


## Functions

### `calculate_hash`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Calculate and return md5 hash of the file in binary mode.

Args:
        path (str): Path to the file to be hashed
```
### `import_files`
**Arguments:** `module, dt, dn, force, pre_process, reset_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `import_file`
**Arguments:** `module, dt, dn, force, pre_process, reset_permissions`
**Decorators:** ``

**Docstring:**
```
Sync a file from txt if modifed, return false if not updated
```
### `get_file_path`
**Arguments:** `module, dt, dn`
**Decorators:** ``

**Docstring:**
```

```
### `import_file_by_path`
**Arguments:** `path, force, data_import, pre_process, ignore_version, reset_permissions`
**Decorators:** ``

**Docstring:**
```
Import file from the given path.

Some conditions decide if a file should be imported or not.
Evaluation takes place in the order they are mentioned below.

- Check if `force` is true. Import the file. If not, move ahead.
- Get `db_modified_timestamp`(value of the modified field in the database for the file).
        If the return is `none,` this file doesn't exist in the DB, so Import the file. If not, move ahead.
- Check if there is a hash in DB for that file. If there is, Calculate the Hash of the file to import and compare it with the one in DB if they are not equal.
        Import the file. If Hash doesn't exist, move ahead.
- Check if `db_modified_timestamp` is older than the timestamp in the file; if it is, we import the file.

If timestamp comparison happens for doctypes, that means the Hash for it doesn't exist.
So, even if the timestamp is newer on DB (When comparing timestamps), we import the file and add the calculated Hash to the DB.
So in the subsequent imports, we can use hashes to compare. As a precautionary measure, the timestamp is updated to the current time as well.

Args:
        path (str): Path to the file.
        force (bool, optional): Load the file without checking any conditions. Defaults to False.
        data_import (bool, optional): [description]. Defaults to False.
        pre_process ([type], optional): Any preprocesing that may need to take place on the doc. Defaults to None.
        ignore_version (bool, optional): ignore current version. Defaults to None.
        reset_permissions (bool, optional): reset permissions for the file. Defaults to False.

Return True if import takes place, False if it wasn't imported.
```
### `read_doc_from_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `update_modified`
**Arguments:** `original_modified, doc`
**Decorators:** ``

**Docstring:**
```

```
### `import_doc`
**Arguments:** `docdict, data_import, pre_process, ignore_version, reset_permissions, path`
**Decorators:** ``

**Docstring:**
```

```
### `load_code_properties`
**Arguments:** `doc, path`
**Decorators:** ``

**Docstring:**
```
Load code files stored in separate files with extensions
```
### `delete_old_doc`
**Arguments:** `doc, reset_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `reset_tree_properties`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```

