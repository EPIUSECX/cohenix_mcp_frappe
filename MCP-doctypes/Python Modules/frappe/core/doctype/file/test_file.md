# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/file/test_file.py`

## Classes

### `TestSimpleFile`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_save` | `self` | `` |  |


### `TestFSRollbacks`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_rollback_from_file_system` | `self` | `` |  |


### `TestExtensionValidations`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_allowed_extension` | `self` | `` |  |


### `TestBase64File`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_saved_content` | `self` | `` |  |


### `TestSameFileName`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_saved_content` | `self` | `` |  |
| `test_saved_content_private` | `self` | `` |  |


### `TestSameContent`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_saved_content` | `self` | `` |  |
| `test_attachment_limit` | `self` | `` |  |
| `test_utf8_bom_content_decoding` | `self` | `` |  |


### `TestFile`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `delete_test_data` | `self` | `` |  |
| `upload_file` | `self` | `` |  |
| `get_folder` | `self, folder_name, parent_folder` | `` |  |
| `tests_after_upload` | `self` | `` |  |
| `test_file_copy` | `self` | `` |  |
| `test_folder_depth` | `self` | `` |  |
| `test_folder_copy` | `self` | `` |  |
| `test_default_folder` | `self` | `` |  |
| `test_on_delete` | `self` | `` |  |
| `test_same_file_url_update` | `self` | `` |  |
| `test_parent_directory_validation_in_file_url` | `self` | `` |  |
| `test_file_url_validation` | `self` | `` |  |
| `test_make_thumbnail` | `self` | `` |  |
| `test_file_unzip` | `self` | `` |  |
| `test_create_file_without_file_url` | `self` | `` |  |
| `test_symlinked_files_folder` | `self` | `` |  |


### `TestAttachment`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_file_attachment_on_update` | `self` | `` |  |


### `TestAttachmentsAccess`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_list_private_attachments` | `self` | `` |  |
| `tearDown` | `self` | `` |  |


### `TestFileUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_extract_images_from_doc` | `self` | `` |  |
| `test_extract_images_from_comment` | `self` | `` | Ensure that images are extracted from comments and become private attachments. |
| `test_extract_images_from_communication` | `self` | `` | Ensure that images are extracted from communication and become public attachments. |
| `test_broken_image` | `self` | `` | Ensure that broken inline images don't cause errors. |
| `test_create_new_folder` | `self` | `` |  |


### `TestFileOptimization`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_optimize_file` | `self` | `` |  |
| `test_optimize_svg` | `self` | `` |  |
| `test_optimize_textfile` | `self` | `` |  |
| `test_optimize_folder` | `self` | `` |  |
| `test_revert_optimized_file_on_rollback` | `self` | `` |  |
| `test_image_header_guessing` | `self` | `` |  |


### `TestGuestFileAndAttachments`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_attach_unattached_guest_file` | `self` | `` | Ensure that unattached files are attached on doc update. |
| `test_list_private_guest_single_file` | `self` | `` | Ensure that guests are not able to read private standalone guest files. |
| `test_list_private_guest_attachment` | `self` | `` | Ensure that guests are not able to read private guest attachments. |
| `test_private_remains_private_even_if_same_hash` | `self` | `` |  |





## Functions

### `make_test_doc`
**Arguments:** `ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `make_test_image_file`
**Arguments:** `private`
**Decorators:** `contextmanager`

**Docstring:**
```

```
### `convert_to_symlink`
**Arguments:** `directory`
**Decorators:** `contextmanager`

**Docstring:**
```
Moves a directory to temp directory and symlinks original path for testing
```

