# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/build.py`

## Classes

### `AssetsNotDownloadedError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.

### `AssetsDontExistError`
**Inherits:** `Exception`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `download_file`
**Arguments:** `url, prefix`
**Decorators:** ``

**Docstring:**
```

```
### `build_missing_files`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Check which files dont exist yet from the assets.json and run build for those files
```
### `get_assets_link`
**Arguments:** `frappe_head`
**Decorators:** ``

**Docstring:**
```

```
### `fetch_assets`
**Arguments:** `url, frappe_head`
**Decorators:** ``

**Docstring:**
```

```
### `setup_assets`
**Arguments:** `assets_archive`
**Decorators:** ``

**Docstring:**
```

```
### `download_frappe_assets`
**Arguments:** `verbose`
**Decorators:** ``

**Docstring:**
```
Download and set up Frappe assets if they exist based on the current commit HEAD.
Return True if correctly setup else return False.
```
### `symlink`
**Arguments:** `target, link_name, overwrite`
**Decorators:** ``

**Docstring:**
```
Create a symbolic link named link_name pointing to target.
If link_name exists then FileExistsError is raised, unless overwrite=True.
When trying to overwrite a directory, IsADirectoryError is raised.

Source: https://stackoverflow.com/a/55742015/10309266
```
### `setup`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `bundle`
**Arguments:** `mode, apps, hard_link, verbose, skip_frappe, files, save_metafiles, using_cached`
**Decorators:** ``

**Docstring:**
```
concat / minify js files
```
### `watch`
**Arguments:** `apps`
**Decorators:** ``

**Docstring:**
```
watch and rebuild if necessary
```
### `check_node_executable`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_node_env`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_safe_max_old_space_size`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `generate_assets_map`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `setup_assets_dirs`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_broken_symlinks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `unstrip`
**Arguments:** `message`
**Decorators:** ``

**Docstring:**
```
Pads input string on the right side until the last available column in the terminal
```
### `make_asset_dirs`
**Arguments:** `hard_link`
**Decorators:** ``

**Docstring:**
```

```
### `link_assets_dir`
**Arguments:** `source, target, hard_link`
**Decorators:** ``

**Docstring:**
```

```
### `scrub_html_template`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```
Return HTML content with removed whitespace and comments.
```
### `html_to_js_template`
**Arguments:** `path, content`
**Decorators:** ``

**Docstring:**
```
Return HTML template content as Javascript code, by adding it to `frappe.templates`.
```

