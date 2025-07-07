# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/file/file.py`

## Classes

### `File`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `is_remote_file` | `self` | `property` |  |
| `autoname` | `self` | `` | Set name for folder |
| `before_insert` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_attachment_references` | `self` | `` |  |
| `after_rename` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `on_rollback` | `self` | `` |  |
| `get_name_based_on_parent_folder` | `self` | `` |  |
| `get_successors` | `self` | `` |  |
| `validate_file_path` | `self` | `` |  |
| `validate_file_url` | `self` | `` |  |
| `handle_is_private_changed` | `self` | `` |  |
| `fetch_attached_to_field` | `self, old_file_url` | `` |  |
| `validate_attachment_limit` | `self` | `` |  |
| `validate_remote_file` | `self` | `` | Validates if file uploaded using URL already exist |
| `set_folder_name` | `self` | `` | Make parent folders if not exists based on reference doctype and name |
| `set_file_type` | `self` | `` |  |
| `validate_file_on_disk` | `self` | `` | Validates existence file |
| `validate_file_extension` | `self` | `` |  |
| `validate_duplicate_entry` | `self` | `` |  |
| `set_file_name` | `self` | `` |  |
| `generate_content_hash` | `self` | `` |  |
| `make_thumbnail` | `self, set_as_thumbnail, width, height, suffix, crop` | `` |  |
| `validate_empty_folder` | `self` | `` | Throw exception if folder is not empty |
| `validate_protected_file` | `self` | `` | Throw an exception if this file is attached to a doctype that protects files.

Allows deleting the attached file if the linked document is in draft. If submitted,
deletion is not allowed. If canceled, requires delete permissions on the linked document. |
| `_delete_file_on_disk` | `self` | `` | If file not attached to any other record, delete it |
| `unzip` | `self` | `` | Unzip current file and replace it by its children |
| `exists_on_disk` | `self` | `` |  |
| `get_content` | `self, encodings` | `` |  |
| `get_full_path` | `self` | `` | Return file path using the set file name. |
| `write_file` | `self` | `` | write file to disk with a random name (to compare) |
| `save_file` | `self, content, decode, ignore_existing_file_check, overwrite` | `` |  |
| `save_file_on_filesystem` | `self` | `` |  |
| `check_max_file_size` | `self` | `` |  |
| `delete_file_data_content` | `self, only_thumbnail` | `` |  |
| `delete_file_from_filesystem` | `self, only_thumbnail` | `` | Delete file, thumbnail from File document |
| `is_downloadable` | `self` | `` |  |
| `get_extension` | `self` | `` | Split and return filename and extension for the set `file_name`. |
| `create_attachment_record` | `self` | `` |  |
| `add_comment_in_reference_doc` | `self, comment_type, text` | `` |  |
| `set_is_private` | `self` | `` |  |
| `optimize_file` | `self` | `` |  |
| `unique_url` | `self` | `property` | Unique URL contains file ID in URL to speed up permisison checks. |
| `zip_files` | `files` | `staticmethod` |  |





## Functions

### `on_doctype_update`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, ptype, user, debug`
**Decorators:** ``

**Docstring:**
```

```
### `get_permission_query_conditions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```

