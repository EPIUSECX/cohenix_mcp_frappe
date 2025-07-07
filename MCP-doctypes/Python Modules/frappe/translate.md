# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/translate.py`

## Classes

No classes found in this file.


## Functions

### `get_language`
**Arguments:** `lang_list`
**Decorators:** ``

**Docstring:**
```
Set `frappe.local.lang` from HTTP headers at beginning of request

Order of priority for setting language:
1. Form Dict => _lang
2. Cookie => preferred_language (Non authorized user)
3. Request Header => Accept-Language (Non authorized user)
4. User document => language
5. System Settings => language
```
### `get_parent_language`
**Arguments:** `lang`
**Decorators:** ``

**Docstring:**
```
If the passed language is a variant, return its parent

Eg:
        1. zh-TW -> zh
        2. sr-BA -> sr
```
### `get_user_lang`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Set frappe.local.lang from user preferences on session beginning or resumption
```
### `get_lang_code`
**Arguments:** `lang`
**Decorators:** ``

**Docstring:**
```

```
### `set_default_language`
**Arguments:** `lang`
**Decorators:** ``

**Docstring:**
```
Set Global default language
```
### `get_lang_dict`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return all languages in dict format, full name is the key e.g. `{"english":"en"}`.
```
### `get_messages_for_boot`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return all message translations that are required on boot.
```
### `get_app_translations`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_all_translations`
**Arguments:** `lang`
**Decorators:** ``

**Docstring:**
```
Load and return the entire translations dictionary for a language from apps + user translations.

:param lang: Language Code, e.g. `hi` or `es-CO`
```
### `get_translations_from_apps`
**Arguments:** `lang, apps`
**Decorators:** ``

**Docstring:**
```
Combine all translations from `.csv` files in all `apps`.
For derivative languages (es-GT), take translations from the
base language (es) and then update translations from the child (es-GT)
```
### `get_translations_from_csv`
**Arguments:** `lang, app`
**Decorators:** ``

**Docstring:**
```

```
### `get_translation_dict_from_file`
**Arguments:** `path, lang, app, throw`
**Decorators:** ``

**Docstring:**
```
Return translation dict from given CSV file at path
```
### `get_user_translations`
**Arguments:** `lang`
**Decorators:** ``

**Docstring:**
```

```
### `clear_cache`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Clear all translation assets from :meth:`frappe.cache`
```
### `get_messages_for_app`
**Arguments:** `app, deduplicate`
**Decorators:** ``

**Docstring:**
```
Return all messages (list) for a specified `app`.
```
### `get_messages_from_navbar`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return all labels from Navbar Items, as specified in Navbar Settings.
```
### `get_messages_from_doctype`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Extract all translatable messages for a doctype. Includes labels, Python code,
Javascript code, html templates
```
### `get_messages_from_workflow`
**Arguments:** `doctype, app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_messages_from_custom_fields`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_messages_from_page`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Return all translatable strings from a :class:`frappe.core.doctype.Page`.
```
### `get_messages_from_report`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```
Return all translatable strings from a :class:`frappe.core.doctype.Report`.
```
### `_get_messages_from_page_or_report`
**Arguments:** `doctype, name, module`
**Decorators:** ``

**Docstring:**
```

```
### `get_server_messages`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Extracts all translatable strings (tagged with :func:`frappe._`) from Python modules
inside an app
```
### `get_messages_from_include_files`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Return messages from js files included at time of boot like desk.min.js for desk and web.
```
### `get_all_messages_from_js_files`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Extracts all translatable strings from app `.js` files
```
### `get_messages_from_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Return a list of transatable strings from a code file.

:param path: path of the code file
```
### `extract_messages_from_python_code`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```
Extracts translatable strings from Python code using babel.
```
### `extract_messages_from_javascript_code`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```
Extracts translatable strings from JavaScript code using babel.
```
### `read_csv_file`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Read CSV file and return as list of list

:param path: File path
```
### `write_csv_file`
**Arguments:** `path, app_messages, lang_dict`
**Decorators:** ``

**Docstring:**
```
Write translation CSV file.

:param path: File path, usually `[app]/translations`.
:param app_messages: Translatable strings for this app.
:param lang_dict: Full translated dict.
```
### `get_untranslated`
**Arguments:** `lang, untranslated_file, get_all, app`
**Decorators:** ``

**Docstring:**
```
Return all untranslated strings for a language and write in a file.

:param lang: Language code.
:param untranslated_file: Output file path.
:param get_all: Return all strings, translated or not.
```
### `update_translations`
**Arguments:** `lang, untranslated_file, translated_file, app`
**Decorators:** ``

**Docstring:**
```
Update translations from a source and target file for a given language.

:param lang: Language code (e.g. `en`).
:param untranslated_file: File path with the messages in English.
:param translated_file: File path with messages in language to be updated.
```
### `import_translations`
**Arguments:** `lang, path`
**Decorators:** ``

**Docstring:**
```
Import translations from file in standard format
```
### `migrate_translations`
**Arguments:** `source_app, target_app`
**Decorators:** ``

**Docstring:**
```
Migrate target-app-specific translations from source-app to target-app
```
### `rebuild_all_translation_files`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Rebuild all translation files: `[app]/translations/[lang].csv`.
```
### `write_translations_file`
**Arguments:** `app, lang, full_dict, app_messages`
**Decorators:** ``

**Docstring:**
```
Write a translation file for a given language.

:param app: `app` for which translations are to be written.
:param lang: Language code.
:param full_dict: Full translated language dict (optional).
:param app_messages: Source strings (optional).
```
### `send_translations`
**Arguments:** `translation_dict`
**Decorators:** ``

**Docstring:**
```
Append translated dict in `frappe.local.response`
```
### `deduplicate_messages`
**Arguments:** `messages`
**Decorators:** ``

**Docstring:**
```

```
### `update_translations_for_source`
**Arguments:** `source, translation_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_all_languages`
**Arguments:** `with_language_name`
**Decorators:** ``

**Docstring:**
```
Return all enabled language codes ar, ch etc.
```
### `get_preferred_language_cookie`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_translated_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `print_language`
**Arguments:** `language`
**Decorators:** `contextmanager`

**Docstring:**
```
Ensure correct globals for printing in a specific language.

Usage:

```
with print_language("de"):
    html = frappe.get_print(...)
```
```

