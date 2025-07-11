# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/lazy_loader.py`

## Classes

No classes found in this file.


## Functions

### `lazy_import`
**Arguments:** `name, package`
**Decorators:** ``

**Docstring:**
```
Import a module lazily.

The module is loaded when modules's attribute is accessed for the first time.
This works with both absolute and relative imports.
$ cat mod.py
print("Loading mod.py")
$ python -i lazy_loader.py
>>> mod = lazy_import("mod")  # Module is not loaded
>>> mod.__str__()  # module is loaded on accessing attribute
Loading mod.py
"<module 'mod' from '.../frappe/utils/mod.py'>"
>>>

Code based on https://github.com/python/cpython/blob/master/Doc/library/importlib.rst#implementing-lazy-imports.
```

