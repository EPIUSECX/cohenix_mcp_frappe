# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/website_theme/website_theme.py`

## Classes

### `WebsiteTheme`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `is_standard_and_not_valid_user` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `validate_if_customizable` | `self` | `` |  |
| `export_doc` | `self` | `` | Export to standard folder `[module]/website_theme/[name]/[name].json`. |
| `clear_cache_if_current_theme` | `self` | `` |  |
| `generate_bootstrap_theme` | `self` | `` |  |
| `delete_old_theme_files` | `self, folder_path` | `` |  |
| `set_as_default` | `self` | `` |  |
| `get_apps` | `self` | `` |  |





## Functions

### `get_active_theme`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_scss`
**Arguments:** `website_theme`
**Decorators:** ``

**Docstring:**
```
Render `website_theme_template.scss` with the values defined in Website Theme.

params:
website_theme - instance of a Website Theme
```
### `get_scss_paths`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return a set of SCSS import paths from all apps that provide `website.scss`.

If `$BENCH_PATH/apps/frappe/frappe/public/scss/website[.bundle].scss` exists, the
returned set will contain 'frappe/public/scss/website[.bundle]'.
```
### `after_migrate`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Regenerate Active Theme CSS file after migration.

Necessary to reflect possible changes in the imported SCSS files. Called at
the end of every `bench migrate`.
```

