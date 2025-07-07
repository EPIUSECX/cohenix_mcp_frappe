# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/contacts/doctype/address/address.py`

## Classes

### `Address`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__setup__` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `link_address` | `self` | `` | Link address based on owner |
| `validate_preferred_address` | `self` | `` |  |
| `get_display` | `self` | `` |  |
| `has_link` | `self, doctype, name` | `` |  |
| `has_common_link` | `self, doc` | `` |  |





## Functions

### `get_preferred_address`
**Arguments:** `doctype, name, preferred_key`
**Decorators:** ``

**Docstring:**
```

```
### `get_default_address`
**Arguments:** `doctype, name, sort_key`
**Decorators:** ``

**Docstring:**
```
Return default Address name for the given doctype, name.
```
### `get_address_display`
**Arguments:** `address_dict`
**Decorators:** ``

**Docstring:**
```

```
### `render_address`
**Arguments:** `address, check_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `get_territory_from_address`
**Arguments:** `address`
**Decorators:** ``

**Docstring:**
```
Tries to match city, state and country of address to existing territory
```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_address_list`
**Arguments:** `doctype, txt, filters, limit_start, limit_page_length, order_by`
**Decorators:** ``

**Docstring:**
```

```
### `has_website_permission`
**Arguments:** `doc, ptype, user, verbose`
**Decorators:** ``

**Docstring:**
```
Return True if there is a related lead or contact related to this document.
```
### `get_address_templates`
**Arguments:** `address`
**Decorators:** ``

**Docstring:**
```

```
### `get_company_address`
**Arguments:** `company`
**Decorators:** ``

**Docstring:**
```

```
### `address_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_condensed_address`
**Arguments:** `doc, no_title`
**Decorators:** ``

**Docstring:**
```

```
### `update_preferred_address`
**Arguments:** `address, field`
**Decorators:** ``

**Docstring:**
```

```
### `get_address_display_list`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```

