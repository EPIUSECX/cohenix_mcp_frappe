# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/desktop_icon/desktop_icon.py`

## Classes

### `DesktopIcon`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_trash` | `self` | `` |  |





## Functions

### `after_doctype_insert`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_desktop_icons`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Return desktop icons for user
```
### `add_user_icon`
**Arguments:** `_doctype, _report, label, link, type, standard`
**Decorators:** ``

**Docstring:**
```
Add a new user desktop icon to the desktop
```
### `set_order`
**Arguments:** `new_order, user`
**Decorators:** ``

**Docstring:**
```
set new order by duplicating user icons (if user is set) or set global order
```
### `set_desktop_icons`
**Arguments:** `visible_list, ignore_duplicate`
**Decorators:** ``

**Docstring:**
```
Resets all lists and makes only the given one standard,
if the desktop icon does not exist and the name is a DocType, then will create
an icon for the doctype
```
### `set_hidden_list`
**Arguments:** `hidden_list, user`
**Decorators:** ``

**Docstring:**
```
Sets property `hidden`=1 in **Desktop Icon** for given user.
If user is None then it will set global values.
It will also set the rest of the icons as shown (`hidden` = 0)
```
### `set_hidden`
**Arguments:** `module_name, user, hidden`
**Decorators:** ``

**Docstring:**
```
Set module hidden property for given user. If user is not specified,
hide/unhide it globally
```
### `get_all_icons`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_desktop_icons_cache`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_copy`
**Arguments:** `module_name, user`
**Decorators:** ``

**Docstring:**
```
Return user copy (Desktop Icon) of the given module_name. If user copy does not exist, create one.

:param module_name: Name of the module
:param user: User for which the copy is required (optional)
```
### `make_user_copy`
**Arguments:** `module_name, user`
**Decorators:** ``

**Docstring:**
```
Insert and return the user copy of a standard Desktop Icon
```
### `sync_desktop_icons`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Sync desktop icons from all apps
```
### `sync_from_app`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```
Sync desktop icons from app. To be called during install
```
### `update_icons`
**Arguments:** `hidden_list, user`
**Decorators:** ``

**Docstring:**
```
update modules
```
### `get_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `get_module_icons`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_icons`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```
Get user icons for module setup page
```
### `hide`
**Arguments:** `name, user`
**Decorators:** ``

**Docstring:**
```

```

