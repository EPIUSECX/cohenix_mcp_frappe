# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/config.py`

## Classes

No classes found in this file.


## Functions

### `get_site_config`
**Arguments:** `sites_path, site_path`
**Decorators:** ``

**Docstring:**
```
Return `site_config.json` combined with `sites/common_site_config.json`.
`site_config` is a set of site wide settings like database name, password, email etc.
```
### `_get_site_config`
**Arguments:** `sites_path, site_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_common_site_config`
**Arguments:** `sites_path, cached`
**Decorators:** ``

**Docstring:**
```
Return common site config as dictionary.

This is useful for:
- checking configuration which should only be allowed in common site config
- When no site context is present and fallback is required.
```
### `_get_common_site_config`
**Arguments:** `sites_path`
**Decorators:** ``

**Docstring:**
```

```
### `clear_site_config_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_conf`
**Arguments:** `site`
**Decorators:** ``

**Docstring:**
```

```

