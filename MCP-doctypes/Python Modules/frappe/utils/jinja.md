# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/jinja.py`

## Classes

No classes found in this file.


## Functions

### `get_jenv`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_jenv`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_template`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```

```
### `get_email_from_template`
**Arguments:** `name, args`
**Decorators:** ``

**Docstring:**
```

```
### `validate_template`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```
Throws exception if there is a syntax error in the Jinja Template
```
### `render_template`
**Arguments:** `template, context, is_path, safe_render`
**Decorators:** ``

**Docstring:**
```
Render a template using Jinja

:param template: path or HTML containing the jinja template
:param context: dict of properties to pass to the template
:param is_path: (optional) assert that the `template` parameter is a path
:param safe_render: (optional) prevent server side scripting via jinja templating
```
### `guess_is_path`
**Arguments:** `template`
**Decorators:** ``

**Docstring:**
```

```
### `get_jloader`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_jloader`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `set_filters`
**Arguments:** `jenv`
**Decorators:** ``

**Docstring:**
```

```
### `get_jinja_hooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return a tuple of (methods, filters) each containing a dict of method name and method definition pair.
```

