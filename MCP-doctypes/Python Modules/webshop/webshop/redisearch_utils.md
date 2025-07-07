# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/redisearch_utils.py`

## Classes

No classes found in this file.


## Functions

### `get_indexable_web_fields`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return valid fields from Website Item that can be searched for.
```
### `is_redisearch_enabled`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return True only if redisearch is loaded and enabled.
```
### `is_search_module_loaded`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `if_redisearch_enabled`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```
Decorator to check if Redisearch is enabled.
```
### `make_key`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `create_website_items_index`
**Arguments:** ``
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```
Creates Index Definition.
```
### `to_search_field`
**Arguments:** `field`
**Decorators:** ``

**Docstring:**
```

```
### `insert_item_to_index`
**Arguments:** `website_item_doc`
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```

```
### `insert_to_name_ac`
**Arguments:** `web_name, doc_name`
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```

```
### `create_web_item_map`
**Arguments:** `website_item_doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_index_for_item`
**Arguments:** `website_item_doc`
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```

```
### `delete_item_from_index`
**Arguments:** `website_item_doc`
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```

```
### `delete_from_ac_dict`
**Arguments:** `website_item_doc`
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```
Removes this items's name from autocomplete dictionary
```
### `define_autocomplete_dictionary`
**Arguments:** ``
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```
Defines/Redefines an autocomplete search dictionary for Website Item Name.
Also creats autocomplete dictionary for Published Item Groups.
```
### `create_items_autocomplete_dict`
**Arguments:** ``
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```
Add items as suggestions in Autocompleter.
```
### `create_item_groups_autocomplete_dict`
**Arguments:** ``
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```
Add item groups with weightage as suggestions in Autocompleter.
```
### `reindex_all_web_items`
**Arguments:** ``
**Decorators:** `if_redisearch_enabled`

**Docstring:**
```

```
### `get_cache_key`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `get_fields_indexed`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `raise_redisearch_error`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Create an Error Log and raise error.
```

