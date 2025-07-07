# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/__init__.py`

## Classes

### `_UserInfo`
**Inherits:** `TypedDict`


**Docstring:**
```

```

**Methods:**
No methods found.

### `CallbackManager`


**Docstring:**
```
Manage callbacks.

```
# Capture callacks
callbacks = CallbackManager()

# Put a function call in queue
callbacks.add(func)

# Run all pending functions in queue
callbacks.run()

# Reset queue
callbacks.reset()
```

Example usage: frappe.db.after_commit
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `add` | `self, func` | `` | Add a function to queue, functions are executed in order of addition. |
| `__call__` | `self, func` | `` |  |
| `run` | `self` | `` | Run all functions in queue |
| `reset` | `self` | `` |  |





## Functions

### `get_fullname`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
get the full name (first name + last name) of the user from User
```
### `get_email_address`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
get the email address of the user from User
```
### `get_formatted_email`
**Arguments:** `user, mail`
**Decorators:** ``

**Docstring:**
```
get Email Address of user formatted as: `John Doe <johndoe@example.com>`
```
### `extract_email_id`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```
fetch only the email part of the Email Address
```
### `validate_phone_number_with_country_code`
**Arguments:** `phone_number, fieldname`
**Decorators:** ``

**Docstring:**
```

```
### `validate_phone_number`
**Arguments:** `phone_number, throw`
**Decorators:** ``

**Docstring:**
```
Return True if valid phone number.
```
### `validate_name`
**Arguments:** `name, throw`
**Decorators:** ``

**Docstring:**
```
Return True if the name is valid

* valid names may have unicode and ascii characters, dash, quotes, numbers
* anything else is considered invalid

Note: "Name" here is name of a person, not the primary key in Frappe doctypes.
```
### `validate_email_address`
**Arguments:** `email_str, throw`
**Decorators:** ``

**Docstring:**
```
Validates the email string
```
### `split_emails`
**Arguments:** `txt`
**Decorators:** ``

**Docstring:**
```

```
### `validate_url`
**Arguments:** `txt, throw, valid_schemes`
**Decorators:** ``

**Docstring:**
```
Return True if `txt` represents a valid URL.

Args:
        throw: throws a validationError if URL is not valid
        valid_schemes: if provided checks the given URL's scheme against this
```
### `random_string`
**Arguments:** `length`
**Decorators:** ``

**Docstring:**
```
generate a random string
```
### `has_gravatar`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```
Return gravatar url if user has set an avatar at gravatar.com.
```
### `get_gravatar_url`
**Arguments:** `email, default`
**Decorators:** ``

**Docstring:**
```
Return gravatar URL for the given email.

If `default` is set to "404", gravatar URL will return 404 if no avatar is found.
If `default` is set to "mm", a placeholder image will be returned.
```
### `get_gravatar`
**Arguments:** `email`
**Decorators:** ``

**Docstring:**
```
Return gravatar URL if user has set an avatar at gravatar.com.

Else return identicon image (base64).
```
### `get_traceback`
**Arguments:** `with_context`
**Decorators:** ``

**Docstring:**
```
Return the traceback of the Exception.
```
### `_get_traceback_sanitizer`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `log`
**Arguments:** `event, details`
**Decorators:** ``

**Docstring:**
```

```
### `dict_to_str`
**Arguments:** `args, sep`
**Decorators:** ``

**Docstring:**
```
Convert a dictionary to URL.
```
### `list_to_str`
**Arguments:** `seq, sep`
**Decorators:** ``

**Docstring:**
```
Convert a sequence into a string using seperator.

Same as str.join, but does type conversion and strip extra spaces.
```
### `get_defaults`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```
Get dictionary of default values from the defaults, or a value if key is passed
```
### `set_default`
**Arguments:** `key, val`
**Decorators:** ``

**Docstring:**
```
Set / add a default value to defaults`
```
### `remove_blanks`
**Arguments:** `d`
**Decorators:** ``

**Docstring:**
```
Return d with empty ('' or None) values stripped. Mutates inplace.
```
### `strip_html_tags`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```
Remove html tags from the given `text`.
```
### `get_file_timestamp`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Return timestamp of the given file.
```
### `esc`
**Arguments:** `s, esc_chars`
**Decorators:** ``

**Docstring:**
```
Escape special characters
```
### `unesc`
**Arguments:** `s, esc_chars`
**Decorators:** ``

**Docstring:**
```
UnEscape special characters
```
### `execute_in_shell`
**Arguments:** `cmd, verbose, low_priority, check_exit_code`
**Decorators:** ``

**Docstring:**
```

```
### `get_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_site_base_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_site_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_files_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_bench_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_bench_id`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_site_id`
**Arguments:** `site`
**Decorators:** ``

**Docstring:**
```

```
### `get_backups_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_request_site_address`
**Arguments:** `full_address`
**Decorators:** ``

**Docstring:**
```

```
### `get_site_url`
**Arguments:** `site`
**Decorators:** ``

**Docstring:**
```

```
### `encode_dict`
**Arguments:** `d, encoding`
**Decorators:** ``

**Docstring:**
```

```
### `decode_dict`
**Arguments:** `d, encoding`
**Decorators:** ``

**Docstring:**
```

```
### `get_site_name`
**Arguments:** `hostname`
**Decorators:** ``

**Docstring:**
```

```
### `get_disk_usage`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
get disk usage of files folder
```
### `touch_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `get_test_client`
**Arguments:** `use_cookies`
**Decorators:** ``

**Docstring:**
```
Return an test instance of the Frappe WSGI.
```
### `get_hook_method`
**Arguments:** `hook_name, fallback`
**Decorators:** ``

**Docstring:**
```

```
### `call_hook_method`
**Arguments:** `hook`
**Decorators:** ``

**Docstring:**
```

```
### `is_cli`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return True if current instance is being run via a terminal.
```
### `update_progress_bar`
**Arguments:** `txt, i, l, absolute`
**Decorators:** ``

**Docstring:**
```

```
### `get_html_format`
**Arguments:** `print_path`
**Decorators:** ``

**Docstring:**
```

```
### `is_markdown`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```

```
### `is_a_property`
**Arguments:** `x`
**Decorators:** ``

**Docstring:**
```
Get properties (@property, @cached_property) in a controller class
```
### `get_sites`
**Arguments:** `sites_path`
**Decorators:** ``

**Docstring:**
```

```
### `get_request_session`
**Arguments:** `max_retries`
**Decorators:** ``

**Docstring:**
```

```
### `markdown`
**Arguments:** `text, sanitize, linkify`
**Decorators:** ``

**Docstring:**
```

```
### `sanitize_email`
**Arguments:** `emails`
**Decorators:** ``

**Docstring:**
```

```
### `parse_addr`
**Arguments:** `email_string`
**Decorators:** ``

**Docstring:**
```
Return email_id and user_name based on email string
Raise error if email string is not valid
```
### `check_format`
**Arguments:** `email_id`
**Decorators:** ``

**Docstring:**
```
Check if email_id is valid. valid email:text@example.com
String check ensures that email_id contains both '.' and
'@' and index of '@' is less than '.'
```
### `get_name_from_email_string`
**Arguments:** `email_string, email_id, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_installed_apps_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_site_info`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_db_count`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Pass a doctype or a series of doctypes to get the count of docs in them.

Parameters:
        *args: Variable length argument list of doctype names whose doc count you need

Return:
        dict: A dict with the count values.

Example:
        via terminal:
                bench --site erpnext.local execute frappe.utils.get_db_count --args "['DocType', 'Communication']"
```
### `call`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Pass a doctype or a series of doctypes to get the count of docs in them
Parameters:
        fn: frappe function to be called

Return:
        based on the function you call: output of the function you call

Example:
        via terminal:
                bench --site erpnext.local execute frappe.utils.call --args '''["frappe.get_all", "Activity Log"]''' --kwargs '''{"fields": ["user", "creation", "full_name"], "filters":{"Operation": "Login", "Status": "Success"}, "limit": "10"}'''
```
### `get_safe_filters`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```

```
### `create_batch`
**Arguments:** `iterable, size`
**Decorators:** ``

**Docstring:**
```
Convert an iterable to multiple batches of constant size of batch_size.

Args:
        iterable (Iterable): Iterable object which is subscriptable
        size (int): Maximum size of batches to be generated

Yields:
        Generator[List]: Batched iterable of maximum length `size`
```
### `set_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_html_for_route`
**Arguments:** `route`
**Decorators:** ``

**Docstring:**
```

```
### `get_file_size`
**Arguments:** `path, format`
**Decorators:** ``

**Docstring:**
```

```
### `get_build_version`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_assets_json`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_bench_relative_path`
**Arguments:** `file_path`
**Decorators:** ``

**Docstring:**
```
Fix paths relative to the bench root directory if exists and return the absolute path.

Args:
        file_path (str, Path): Path of a file that exists on the file system

Return:
        str: Absolute path of the file_path
```
### `groupby_metric`
**Arguments:** `iterable, key`
**Decorators:** ``

**Docstring:**
```
Group records by a metric.

Usecase: Lets assume we got country wise players list with the ranking given for each player(multiple players in a country can have same ranking aswell).
We can group the players by ranking(can be any other metric) using this function.

>>> d = {
        'india': [{'id':1, 'name': 'iplayer-1', 'ranking': 1}, {'id': 2, 'ranking': 1, 'name': 'iplayer-2'}, {'id': 2, 'ranking': 2, 'name': 'iplayer-3'}],
        'Aus': [{'id':1, 'name': 'aplayer-1', 'ranking': 1}, {'id': 2, 'ranking': 1, 'name': 'aplayer-2'}, {'id': 2, 'ranking': 2, 'name': 'aplayer-3'}]
}
>>> groupby(d, key="ranking")
{1: {'Aus': [{'id': 1, 'name': 'aplayer-1', 'ranking': 1},
                        {'id': 2, 'name': 'aplayer-2', 'ranking': 1}],
        'india': [{'id': 1, 'name': 'iplayer-1', 'ranking': 1},
                        {'id': 2, 'name': 'iplayer-2', 'ranking': 1}]},
2: {'Aus': [{'id': 2, 'name': 'aplayer-3', 'ranking': 2}],
        'india': [{'id': 2, 'name': 'iplayer-3', 'ranking': 2}]}}
```
### `get_table_name`
**Arguments:** `table_name, wrap_in_backticks`
**Decorators:** ``

**Docstring:**
```

```
### `squashify`
**Arguments:** `what`
**Decorators:** ``

**Docstring:**
```

```
### `safe_json_loads`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `dictify`
**Arguments:** `arg`
**Decorators:** ``

**Docstring:**
```

```
### `add_user_info`
**Arguments:** `user, user_info`
**Decorators:** ``

**Docstring:**
```

```
### `is_git_url`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```

```
### `safe_eval`
**Arguments:** `code, eval_globals, eval_locals`
**Decorators:** ``

**Docstring:**
```
A safer `eval`
```

