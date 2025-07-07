# Python Module Analysis: `/workspace/cohenix-bench/apps/webshop/webshop/webshop/doctype/override_doctype/item_group.py`

## Classes

### `WebshopItemGroup`
**Inherits:** `ItemGroup, WebsiteGenerator`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `make_route` | `self` | `` | Make website route |
| `on_trash` | `self` | `` |  |
| `get_context` | `self, context` | `` |  |
| `has_website_permission` | `self, ptype, user, verbose` | `` |  |





## Functions

### `get_item_for_list_in_html`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_parent_item_groups`
**Arguments:** `item_group_name, from_item`
**Decorators:** ``

**Docstring:**
```

```
### `invalidate_cache_for`
**Arguments:** `doc, item_group`
**Decorators:** ``

**Docstring:**
```

```
### `get_child_groups_for_website`
**Arguments:** `item_group_name, immediate, include_self`
**Decorators:** ``

**Docstring:**
```
Returns child item groups *excluding* passed group.
```

