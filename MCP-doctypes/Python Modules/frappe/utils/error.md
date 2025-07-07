# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/error.py`

## Classes

No classes found in this file.


## Functions

### `_is_ldap_exception`
**Arguments:** `e`
**Decorators:** ``

**Docstring:**
```
Check if exception is from LDAP library.

This is a hack but ensures that LDAP is not imported unless it's required. This is tested in
unittests in case the exception changes in future.
```
### `log_error`
**Arguments:** `title, message, reference_doctype, reference_name`
**Decorators:** ``

**Docstring:**
```
Log error to Error Log
```
### `log_error_snapshot`
**Arguments:** `exception`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_args`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```
Get default arguments of a function from its signature.
```
### `raise_error_on_no_output`
**Arguments:** `error_message, error_type, keep_quiet`
**Decorators:** ``

**Docstring:**
```
Decorate any function to throw error incase of missing output.

:param error_message: error message to raise
:param error_type: type of error to raise
:param keep_quiet: control error raising with external factor.
:type error_message: str
:type error_type: Exception Class
:type keep_quiet: function

---
Example:

```py
@raise_error_on_no_output("Ingredients are missing")
def get_ingredients(_raise_error=1):
    return


# this will raise an Exception with message "Ingredients are missing"
ingredients = get_ingredients()
```

---

TODO: Remove keep_quiet flag after testing and fixing sendmail flow.
```
### `guess_exception_source`
**Arguments:** `exception`
**Decorators:** ``

**Docstring:**
```
Attempts to guess source of error based on traceback.

E.g.

- For unhandled exception last python file from apps folder is responsible.
- For frappe.throws the exception source is possibly present after skipping frappe.throw frames
- For server script the file name contains SERVER_SCRIPT_FILE_PREFIX
```

