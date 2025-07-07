# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/core/utils.py`

## Classes

No classes found in this file.


## Functions

### `get_parent_doc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Return document of `reference_doctype`, `reference_doctype`.
```
### `set_timeline_doc`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Set timeline_doctype and timeline_name
```
### `find`
**Arguments:** `list_of_dict, match_function`
**Decorators:** ``

**Docstring:**
```
Return a dict in a list of dicts on matching the conditions provided in match function.

Usage:
        list_of_dict = [{'name': 'Suraj'}, {'name': 'Aditya'}]

        required_dict = find(list_of_dict, lambda d: d['name'] == 'Aditya')
```
### `find_all`
**Arguments:** `list_of_dict, match_function`
**Decorators:** ``

**Docstring:**
```
Return all matching dicts in a list of dicts. Uses matching function to filter out the dicts.

Usage:
        colored_shapes = [
                {'color': 'red', 'shape': 'square'},
                {'color': 'red', 'shape': 'circle'},
                {'color': 'blue', 'shape': 'triangle'}
        ]

        red_shapes = find_all(colored_shapes, lambda d: d['color'] == 'red')
```
### `ljust_list`
**Arguments:** `_list, length, fill_word`
**Decorators:** ``

**Docstring:**
```
Similar to ljust but for list.

Usage:
        $ ljust_list([1, 2, 3], 5)
        > [1, 2, 3, None, None]
```
### `html2text`
**Arguments:** `html, strip_links, wrap`
**Decorators:** ``

**Docstring:**
```
Return the given `html` as markdown text.
```

