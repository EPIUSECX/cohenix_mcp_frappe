# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/ui_test_helpers.py`

## Classes

No classes found in this file.


## Functions

### `whitelist_for_tests`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```

```
### `create_if_not_exists`
**Arguments:** `doc`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```
Create records if they dont exist.
Will check for uniqueness by checking if a record exists with these field value pairs

:param doc: dict of field value pairs. can be a list of dict for multiple records.
```
### `create_todo_records`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `prepare_webform_test`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_communication_record`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `setup_workflow`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_contact_phone_nos_records`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_doctype`
**Arguments:** `name, fields`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_child_doctype`
**Arguments:** `name, fields`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_contact_records`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_multiple_todo_records`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `insert_contact`
**Arguments:** `first_name, phone_number`
**Decorators:** ``

**Docstring:**
```

```
### `create_form_tour`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_data_for_discussions`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_web_page`
**Arguments:** `title, route, single_thread`
**Decorators:** ``

**Docstring:**
```

```
### `create_topic_and_reply`
**Arguments:** `web_page`
**Decorators:** ``

**Docstring:**
```

```
### `update_webform_to_multistep`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `update_child_table`
**Arguments:** `name`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `insert_doctype_with_child_table_record`
**Arguments:** `name`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `insert_translations`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_blog_post`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_test_user`
**Arguments:** `username`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `setup_tree_doctype`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `setup_image_doctype`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `setup_inbox`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `setup_default_view`
**Arguments:** `view, force_reroute`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_kanban`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_todo`
**Arguments:** `description`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_todo_with_attachment_limit`
**Arguments:** `description`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `create_admin_kanban`
**Arguments:** ``
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `add_remove_role`
**Arguments:** `action, user, role`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `publish_realtime`
**Arguments:** `event, message, room, user, doctype, docname, task_id`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `publish_progress`
**Arguments:** `duration, title, doctype, docname`
**Decorators:** `whitelist_for_tests`

**Docstring:**
```

```
### `slow_task`
**Arguments:** `duration, title, doctype, docname`
**Decorators:** ``

**Docstring:**
```

```

