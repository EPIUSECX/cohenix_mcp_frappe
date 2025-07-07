# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/gettext/extractors/javascript.py`

## Classes

No classes found in this file.


## Functions

### `extract`
**Arguments:** `fileobj, keywords, comment_tags, options`
**Decorators:** ``

**Docstring:**
```

```
### `extract_javascript`
**Arguments:** `code, keywords, options, lineno`
**Decorators:** ``

**Docstring:**
```
Extract messages from JavaScript source code.

This is a modified version of babel's JS parser. Reused under BSD license.
License: https://github.com/python-babel/babel/blob/master/LICENSE

Changes from upstream:
- Preserve arguments, babel's parser flattened all values in args,
  we need order because we use different syntax for translation
  which can contain 2nd arg which is array of many values. If
  argument is non-primitive type then value is NOT returned in
  args.
  E.g. __("0", ["1", "2"], "3") -> ("0", None, "3")
- remove comments support
- changed signature to accept string directly.

:param code: code as string
:param keywords: a list of keywords (i.e. function names) that should be recognized as translation functions
    Defaults to ("__",)
:param options: a dictionary of additional options (optional)
    Supported options are:
        * `template_string` -- set to false to disable ES6 template string support.
```
### `parse_template_string`
**Arguments:** `template_string, keywords, options, lineno`
**Decorators:** ``

**Docstring:**
```
Parse JavaScript template string.

This is a modified version of babel's JS parser. Reused under BSD license.
License: https://github.com/python-babel/babel/blob/master/LICENSE

:param template_string: the template string to be parsed
:param keywords: a list of keywords (i.e. function names) that should be recognized as translation functions
:param options: a dictionary of additional options (optional)
:param lineno: starting line number (optional)
```

