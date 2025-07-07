# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/modules/patch_handler.py`

## Classes

### `PatchError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `PatchType`
**Inherits:** `Enum`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `run_all`
**Arguments:** `skip_failing, patch_type`
**Decorators:** ``

**Docstring:**
```
run all pending patches
```
### `get_all_patches`
**Arguments:** `patch_type`
**Decorators:** ``

**Docstring:**
```

```
### `get_patches_from_app`
**Arguments:** `app, patch_type`
**Decorators:** ``

**Docstring:**
```
Get patches from an app's patches.txt

patches.txt can be:
        1. ini like file with section for different patch_type
        2. plain text file with each line representing a patch.
```
### `parse_as_configfile`
**Arguments:** `patches_file, patch_type`
**Decorators:** ``

**Docstring:**
```

```
### `reload_doc`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```

```
### `run_single`
**Arguments:** `patchmodule, method, methodargs, force`
**Decorators:** ``

**Docstring:**
```

```
### `execute_patch`
**Arguments:** `patchmodule, method, methodargs`
**Decorators:** ``

**Docstring:**
```
execute the patch
```
### `update_patch_log`
**Arguments:** `patchmodule, skipped`
**Decorators:** ``

**Docstring:**
```
update patch_file in patch log
```
### `executed`
**Arguments:** `patchmodule`
**Decorators:** ``

**Docstring:**
```
return True if is executed
```
### `_patch_mode`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```
stop/start execution till patch is run
```

