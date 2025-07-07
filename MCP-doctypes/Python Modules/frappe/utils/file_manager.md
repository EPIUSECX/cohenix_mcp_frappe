# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/file_manager.py`

## Classes

### `MaxFileSizeReachedError`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `safe_b64decode`
**Arguments:** `binary`
**Decorators:** ``

**Docstring:**
```
Adds padding if doesn't already exist before decoding.

This attempts to avoid the `binascii.Error: Incorrect padding` error raised
when the number of trailing = is simply not enough :crie:. Although, it may
be an indication of corrupted data.

Refs:
        * https://en.wikipedia.org/wiki/Base64
        * https://stackoverflow.com/questions/2941995/python-ignore-incorrect-padding-error-when-base64-decoding
```
### `get_file_url`
**Arguments:** `file_data_name`
**Decorators:** ``

**Docstring:**
```

```
### `upload`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_file_doc`
**Arguments:** `dt, dn, folder, is_private, df`
**Decorators:** ``

**Docstring:**
```
Return File object (Document) from given parameters or `form_dict`.
```
### `save_uploaded`
**Arguments:** `dt, dn, folder, is_private, df`
**Decorators:** ``

**Docstring:**
```

```
### `save_url`
**Arguments:** `file_url, filename, dt, dn, folder, is_private, df`
**Decorators:** ``

**Docstring:**
```

```
### `get_uploaded_content`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `save_file`
**Arguments:** `fname, content, dt, dn, folder, decode, is_private, df`
**Decorators:** ``

**Docstring:**
```

```
### `get_file_data_from_hash`
**Arguments:** `content_hash, is_private`
**Decorators:** ``

**Docstring:**
```

```
### `save_file_on_filesystem`
**Arguments:** `fname, content, content_type, is_private`
**Decorators:** ``

**Docstring:**
```

```
### `get_max_file_size`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `check_max_file_size`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```

```
### `write_file`
**Arguments:** `content, fname, is_private`
**Decorators:** ``

**Docstring:**
```
write file to disk with a random name (to compare)
```
### `remove_all`
**Arguments:** `dt, dn, from_delete, delete_permanently`
**Decorators:** ``

**Docstring:**
```
remove all files in a transaction
```
### `remove_file`
**Arguments:** `fid, attached_to_doctype, attached_to_name, from_delete, delete_permanently`
**Decorators:** ``

**Docstring:**
```
Remove file and File entry
```
### `delete_file_data_content`
**Arguments:** `doc, only_thumbnail`
**Decorators:** ``

**Docstring:**
```

```
### `delete_file_from_filesystem`
**Arguments:** `doc, only_thumbnail`
**Decorators:** ``

**Docstring:**
```
Delete file, thumbnail from File document
```
### `delete_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Delete file from `public folder`
```
### `get_file`
**Arguments:** `fname`
**Decorators:** ``

**Docstring:**
```
Return [`file_name`, `content`] for given file name `fname`.
```
### `get_file_path`
**Arguments:** `file_name`
**Decorators:** ``

**Docstring:**
```
Return file path from given file name.
```
### `get_content_hash`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```

```
### `get_file_name`
**Arguments:** `fname, optional_suffix`
**Decorators:** ``

**Docstring:**
```

```
### `add_attachments`
**Arguments:** `doctype, name, attachments`
**Decorators:** ``

**Docstring:**
```
Add attachments to the given DocType
```
### `is_safe_path`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```

