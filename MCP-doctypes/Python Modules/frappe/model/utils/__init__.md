# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/utils/__init__.py`

## Classes

### `InvalidIncludePath`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `set_default`
**Arguments:** `doc, key`
**Decorators:** ``

**Docstring:**
```
Set is_default property of given doc and unset all others filtered by given key.
```
### `set_field_property`
**Arguments:** `filters, key, value`
**Decorators:** ``

**Docstring:**
```
utility set a property in all fields of a particular type
```
### `render_include`
**Arguments:** `content`
**Decorators:** ``

**Docstring:**
```
render {% raw %}{% include "app/path/filename" %}{% endraw %} in js file
```
### `get_fetch_values`
**Arguments:** `doctype, fieldname, value`
**Decorators:** ``

**Docstring:**
```
Return fetch value dict for the given object.

:param doctype: Target doctype
:param fieldname: Link fieldname selected
:param value: Value selected
```
### `is_virtual_doctype`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `is_single_doctype`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `simple_singledispatch`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```
A decorator that implements a simplified version of single dispatch.

This decorator allows you to define a generic function that can have
different behaviors based on the type of its first argument. It's similar
to Python's functools.singledispatch, but with a simpler implementation.

Args:
    func (callable): The base function to be decorated.

Returns:
    callable: A wrapper function that implements the single dispatch logic.

The returned wrapper function has a 'register' method that can be used
to register type-specific implementations:

@wrapper.register(specific_type)
def type_specific_func(arg, ...):
    # Implementation for specific_type

When the wrapped function is called, it dispatches to the most specific
implementation based on the type of the first argument. If no matching
implementation is found, it falls back to the base function.

Example:
    @simple_singledispatch
    def func(arg):
        print(f"Base implementation for {type(arg)}")

    @func.register(int)
    def _(arg):
        print(f"Implementation for int: {arg}")

    @func.register(str)
    def _(arg):
        print(f"Implementation for str: {arg}")

    func(10)  # Outputs: Implementation for int: 10
    func("hello")  # Outputs: Implementation for str: hello
    func([1, 2, 3])  # Outputs: Base implementation for <class 'list'>
```

