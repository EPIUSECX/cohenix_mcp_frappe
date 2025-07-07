# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_patches.py`

## Classes

### `TestPatches`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_patch_module_names` | `self` | `` |  |
| `test_get_patch_list` | `self` | `` |  |
| `test_all_patches_are_marked_completed` | `self` | `` |  |


### `TestPatchReader`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `get_patches` | `self` | `` |  |
| `test_empty_file` | `self, _file` | `` |  |
| `test_empty_sections` | `self, _file` | `` |  |
| `test_new_style` | `self, _file` | `` |  |
| `test_old_style` | `self, _file` | `` |  |
| `test_new_style_edge_cases` | `self, _file` | `` |  |
| `test_ignore_comments` | `self, _file` | `` |  |
| `test_verify_patch_txt` | `self` | `` | Make sure all patches/**.py files are part of patches.txt |





## Functions

### `check_patch_files`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Make sure all patches/**.py files are part of patches.txt
```
### `_get_dotted_path`
**Arguments:** `file, app`
**Decorators:** ``

**Docstring:**
```

```

