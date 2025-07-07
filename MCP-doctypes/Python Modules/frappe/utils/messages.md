# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/messages.py`

## Classes

No classes found in this file.


## Functions

### `msgprint`
**Arguments:** `msg, title, raise_exception, as_table, as_list, indicator, alert, primary_action, is_minimizable, wide`
**Decorators:** ``

**Docstring:**
```
Print a message to the user (via HTTP response).
Messages are sent in the `__server_messages` property in the
response JSON and shown in a pop-up / modal.

:param msg: Message.
:param title: [optional] Message title. Default: "Message".
:param raise_exception: [optional] Raise given exception and show message.
:param as_table: [optional] If `msg` is a list of lists, render as HTML table.
:param as_list: [optional] If `msg` is a list, render as un-ordered list.
:param primary_action: [optional] Bind a primary server/client side action.
:param is_minimizable: [optional] Allow users to minimize the modal
:param wide: [optional] Show wide modal
:param realtime: Publish message immediately using websocket.
```
### `toast`
**Arguments:** `message, indicator`
**Decorators:** ``

**Docstring:**
```

```
### `clear_messages`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_message_log`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `clear_last_message`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `throw`
**Arguments:** `msg, exc, title, is_minimizable, wide, as_list, primary_action`
**Decorators:** ``

**Docstring:**
```
Throw execption and show message (`msgprint`).

:param msg: Message.
:param exc: Exception class. Default `frappe.ValidationError`
:param title: [optional] Message title. Default: "Message".
:param is_minimizable: [optional] Allow users to minimize the modal
:param wide: [optional] Show wide modal
:param as_list: [optional] If `msg` is a list, render as un-ordered list.
:param primary_action: [optional] Bind a primary server/client side action.
```
### `throw_permission_error`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

