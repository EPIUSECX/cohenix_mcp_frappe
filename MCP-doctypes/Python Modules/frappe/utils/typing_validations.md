# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/typing_validations.py`

## Classes

No classes found in this file.


## Functions

### `validate_argument_types`
**Arguments:** `func, apply_condition`
**Decorators:** ``

**Docstring:**
```

```
### `qualified_name`
**Arguments:** `obj`
**Decorators:** ``

**Docstring:**
```
Return the qualified name (e.g. package.module.Type) for the given object.

Builtins and types from the :mod:typing package get special treatment by having the module
name stripped from the generated name.
```
### `raise_type_error`
**Arguments:** `func, arg_name, arg_type, arg_value, current_exception`
**Decorators:** ``

**Docstring:**
```
Raise a TypeError with a message that includes the name of the argument, the expected type
and the actual type of the value passed.
```
### `TypeAdapter`
**Arguments:** `type_`
**Decorators:** ``

**Docstring:**
```

```
### `transform_parameter_types`
**Arguments:** `func, args, kwargs`
**Decorators:** ``

**Docstring:**
```
Validate the types of the arguments passed to a function with the type annotations
defined on the function.
```

