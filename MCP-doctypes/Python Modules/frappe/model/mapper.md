# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/mapper.py`

## Classes

No classes found in this file.


## Functions

### `make_mapped_doc`
**Arguments:** `method, source_name, selected_children, args`
**Decorators:** ``

**Docstring:**
```
Return the mapped document calling the given mapper method.
Set `selected_children` as flags for the `get_mapped_doc` method.

Called from `open_mapped_doc` from create_new.js
```
### `map_docs`
**Arguments:** `method, source_names, target_doc, args`
**Decorators:** ``

**Docstring:**
```
Return the mapped document calling the given mapper method with each of the given source docs on the target doc.

:param args: Args as string to pass to the mapper method

e.g. args: "{ 'supplier': 'XYZ' }"
```
### `get_mapped_doc`
**Arguments:** `from_doctype, from_docname, table_maps, target_doc, postprocess, ignore_permissions, ignore_child_tables, cached`
**Decorators:** ``

**Docstring:**
```

```
### `map_doc`
**Arguments:** `source_doc, target_doc, table_map, source_parent`
**Decorators:** ``

**Docstring:**
```

```
### `map_fields`
**Arguments:** `source_doc, target_doc, table_map, source_parent`
**Decorators:** ``

**Docstring:**
```

```
### `map_fetch_fields`
**Arguments:** `target_doc, df, no_copy_fields`
**Decorators:** ``

**Docstring:**
```

```
### `map_child_doc`
**Arguments:** `source_d, target_parent, table_map, source_parent`
**Decorators:** ``

**Docstring:**
```

```

