# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/logger.py`

## Classes

### `SiteContextFilter`


**Docstring:**
```
This is a filter which injects request information (if available) into the log.
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `filter` | `self, record` | `` |  |





## Functions

### `create_handler`
**Arguments:** `module, site, max_size, file_count, stream_only`
**Decorators:** ``

**Docstring:**
```
Create and return a Frappe-specific logging handler.
```
### `get_logger`
**Arguments:** `module, with_more_info, allow_site, filter, max_size, file_count, stream_only`
**Decorators:** ``

**Docstring:**
```
Return Application Logger for your given module.

Args:
        module (str, optional): Name of your logger and consequently your log file. Defaults to None.
        with_more_info (bool, optional): Will log the form dict using the SiteContextFilter. Defaults to False.
        allow_site ((str, bool), optional): Pass site name to explicitly log under it's logs. If True and unspecified, guesses which site the logs would be saved under. Defaults to True.
        filter (function, optional): Add a filter function for your logger. Defaults to None.
        max_size (int, optional): Max file size of each log file in bytes. Defaults to 100_000.
        file_count (int, optional): Max count of log files to be retained via Log Rotation. Defaults to 20.
        stream_only (bool, optional): Whether to stream logs only to stderr (True) or use log files (False). Defaults to False.

Return a Python logger object with Site and Bench level logging capabilities.
```
### `set_log_level`
**Arguments:** `level`
**Decorators:** ``

**Docstring:**
```
Use this method to set log level to something other than the default DEBUG
```
### `sanitized_dict`
**Arguments:** `form_dict`
**Decorators:** ``

**Docstring:**
```

```

