# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/gettext/translate.py`

## Classes

No classes found in this file.


## Functions

### `new_catalog`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```

```
### `get_po_dir`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `get_locale_dir`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_locales`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `get_po_path`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```

```
### `get_mo_path`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```

```
### `get_pot_path`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `get_catalog`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```
Returns a catatalog for the given app and locale
```
### `write_catalog`
**Arguments:** `app, catalog, locale`
**Decorators:** ``

**Docstring:**
```
Writes a catalog to the given app and locale
```
### `write_binary`
**Arguments:** `app, catalog, locale`
**Decorators:** ``

**Docstring:**
```

```
### `get_method_map`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```
### `generate_pot`
**Arguments:** `target_app`
**Decorators:** ``

**Docstring:**
```
Generate a POT (PO template) file. This file will contain only messages IDs.
https://en.wikipedia.org/wiki/Gettext
:param target_app: If specified, limit to `app`
```
### `get_is_gitignored_function_for_app`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Used to check if a directory is gitignored or not.
Can NOT be used to check if a file is gitignored or not.
```
### `new_po`
**Arguments:** `locale, target_app`
**Decorators:** ``

**Docstring:**
```

```
### `compile_translations`
**Arguments:** `target_app, locale, force`
**Decorators:** ``

**Docstring:**
```

```
### `_compile_translation`
**Arguments:** `app, locale, force`
**Decorators:** ``

**Docstring:**
```

```
### `update_po`
**Arguments:** `target_app, locale`
**Decorators:** ``

**Docstring:**
```
Add keys to available PO files, from POT file. This could be used to keep
track of available keys, and missing translations
:param target_app: Limit operation to `app`, if specified
```
### `migrate`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```

```
### `csv_to_po`
**Arguments:** `app, locale`
**Decorators:** ``

**Docstring:**
```

```
### `get_translations_from_mo`
**Arguments:** `lang, app`
**Decorators:** ``

**Docstring:**
```
Get translations from MO files.

For dialects (i.e. es_GT), take translations from the base language (i.e. es)
and then update with specific translations from the dialect (i.e. es_GT).

If we only have a translation with context, also use it as a translation
without context. This way we can provide the context for each source string
but don't have to create a translation for each context.
```
### `escape_percent`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```

```

