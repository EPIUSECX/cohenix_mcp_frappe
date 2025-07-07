# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/locale.py`

## Classes

No classes found in this file.


## Functions

### `get_number_format`
**Arguments:** `language`
**Decorators:** ``

**Docstring:**
```
Return the number format for the given language.

:param language: The language code to get the value for. Defaults to the current user's language.
:return: The number format. Defaults to "#,###.##" if not found.
```
### `get_date_format`
**Arguments:** `language`
**Decorators:** ``

**Docstring:**
```
Return the date format for the given language.

:param language: The language code to get the value for. Defaults to the current user's language.
:return: The date format string. Defaults to "yyyy-mm-dd" if not found.
```
### `get_time_format`
**Arguments:** `language`
**Decorators:** ``

**Docstring:**
```
Return the time format for the given language.

:param language: The language code to get the value for. Defaults to the current user's language.
:return: The time format string. Defaults to "HH:mm:ss" if not found.
```
### `get_first_day_of_the_week`
**Arguments:** `language`
**Decorators:** ``

**Docstring:**
```
Return the first day of the week for the given language.

:param language: The language code to get the value for. Defaults to the current user's language.
:return: The first day of the week. Defaults to "Sunday" if not found.
```
### `get_locale_value`
**Arguments:** `key, language`
**Decorators:** ``

**Docstring:**
```
Return the value of the key from the Language record or System Settings.

:param key: The settings key to get the value for.
:param language: The language code to get the value for. Defaults to the current user's language.
```

