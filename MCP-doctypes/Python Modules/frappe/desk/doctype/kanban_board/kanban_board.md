# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/kanban_board/kanban_board.py`

## Classes

### `KanbanBoard`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_change` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `validate_column_name` | `self` | `` |  |





## Functions

### `get_permission_query_conditions`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doc, ptype, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_kanban_boards`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Get Kanban Boards for doctype to show in List View
```
### `add_column`
**Arguments:** `board_name, column_title`
**Decorators:** ``

**Docstring:**
```
Adds new column to Kanban Board
```
### `archive_restore_column`
**Arguments:** `board_name, column_title, status`
**Decorators:** ``

**Docstring:**
```
Set column's status to status
```
### `update_order`
**Arguments:** `board_name, order`
**Decorators:** ``

**Docstring:**
```
Save the order of cards in columns
```
### `update_order_for_single_card`
**Arguments:** `board_name, docname, from_colname, to_colname, old_index, new_index`
**Decorators:** ``

**Docstring:**
```
Save the order of cards in columns
```
### `get_kanban_column_order_and_index`
**Arguments:** `board, colname`
**Decorators:** ``

**Docstring:**
```

```
### `add_card`
**Arguments:** `board_name, docname, colname`
**Decorators:** ``

**Docstring:**
```

```
### `quick_kanban_board`
**Arguments:** `doctype, board_name, field_name, project`
**Decorators:** ``

**Docstring:**
```
Create new KanbanBoard quickly with default options
```
### `get_order_for_column`
**Arguments:** `board, colname`
**Decorators:** ``

**Docstring:**
```

```
### `update_column_order`
**Arguments:** `board_name, order`
**Decorators:** ``

**Docstring:**
```
Set the order of columns in Kanban Board
```
### `set_indicator`
**Arguments:** `board_name, column_name, indicator`
**Decorators:** ``

**Docstring:**
```
Set the indicator color of column
```
### `save_settings`
**Arguments:** `board_name, settings`
**Decorators:** ``

**Docstring:**
```

```

