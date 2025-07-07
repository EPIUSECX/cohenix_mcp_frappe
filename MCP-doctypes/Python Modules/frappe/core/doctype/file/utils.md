# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/file/utils.py`

## Classes

No classes found in this file.


## Functions

### `make_home_folder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `setup_folder_path`
**Arguments:** `filename, new_parent`
**Decorators:** ``

**Docstring:**
```

```
### `get_extension`
**Arguments:** `filename, extn, content, response`
**Decorators:** ``

**Docstring:**
```

```
### `get_local_image`
**Arguments:** `file_url`
**Decorators:** ``

**Docstring:**
```

```
### `get_web_image`
**Arguments:** `file_url`
**Decorators:** ``

**Docstring:**
```

```
### `delete_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Delete file from `public folder`
```
### `remove_file_by_url`
**Arguments:** `file_url, doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_content_hash`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```

```
### `generate_file_name`
**Arguments:** `name, suffix, is_private`
**Decorators:** ``

**Docstring:**
```
Generate conflict-free file name. Suffix will be ignored if name available. If the
provided suffix doesn't result in an available path, a random suffix will be picked.
```
### `get_file_name`
**Arguments:** `fname, optional_suffix`
**Decorators:** ``

**Docstring:**
```

```
### `extract_images_from_doc`
**Arguments:** `doc, fieldname, is_private`
**Decorators:** ``

**Docstring:**
```

```
### `extract_images_from_html`
**Arguments:** `doc, content, is_private`
**Decorators:** ``

**Docstring:**
```

```
### `get_corrupted_image_msg`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_random_filename`
**Arguments:** `content_type`
**Decorators:** ``

**Docstring:**
```

```
### `update_existing_file_docs`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `attach_files_to_document`
**Arguments:** `doc, event`
**Decorators:** ``

**Docstring:**
```
Runs on on_update hook of all documents.
Goes through every file linked with the Attach and Attach Image field and attaches
the file to the document if not already attached. If no file is found, a new file
is created.
```
### `relink_files`
**Arguments:** `doc, fieldname, temp_doc_name`
**Decorators:** ``

**Docstring:**
```
Relink files attached to incorrect document name to the new document name
by check if file with temp name exists that was created in last 60 minutes
```
### `relink_mismatched_files`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `decode_file_content`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```

```
### `find_file_by_url`
**Arguments:** `path, name`
**Decorators:** ``

**Docstring:**
```

```

