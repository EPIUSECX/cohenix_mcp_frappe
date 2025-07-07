# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/__init__.py`

## Classes

### `init_site`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, site` | `` | If site is None, initialize it for empty site ('') to load common_site_config.json |
| `__enter__` | `self` | `` |  |
| `__exit__` | `self, type, value, traceback` | `` |  |





## Functions

### `_`
**Arguments:** `msg, lang, context`
**Decorators:** ``

**Docstring:**
```
Return translated string in current lang, if exists.
Usage:
        _('Change')
        _('Change', context='Coins')
```
### `_lt`
**Arguments:** `msg, lang, context`
**Decorators:** ``

**Docstring:**
```
Lazily translate a string.


This function returns a "lazy string" which when casted to string via some operation applies
translation first before casting.

This is only useful for translating strings in global scope or anything that potentially runs
before `frappe.init()`

Note: Result is not guaranteed to equivalent to pure strings for all operations.
```
### `set_user_lang`
**Arguments:** `user, user_language`
**Decorators:** ``

**Docstring:**
```
Guess and set user language for the session. `frappe.local.lang`
```
### `init`
**Arguments:** `site, sites_path, new_site, force`
**Decorators:** ``

**Docstring:**
```
Initialize frappe for the current site. Reset thread locals `frappe.local`
```
### `connect`
**Arguments:** `site, db_name, set_admin_as_user`
**Decorators:** ``

**Docstring:**
```
Connect to site database instance.

:param site: (Deprecated) If site is given, calls `frappe.init`.
:param db_name: (Deprecated) Optional. Will use from `site_config.json`.
:param set_admin_as_user: Set Administrator as current user.
```
### `connect_replica`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `destroy`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Closes connection and releases werkzeug local.
```
### `setup_redis_cache_connection`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Defines `frappe.cache` as `RedisWrapper` instance
```
### `errprint`
**Arguments:** `msg`
**Decorators:** ``

**Docstring:**
```
Log error. This is sent back as `exc` in response.

:param msg: Message.
```
### `print_sql`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `log`
**Arguments:** `msg`
**Decorators:** ``

**Docstring:**
```
Add to `debug_log`

:param msg: Message.
```
### `create_folder`
**Arguments:** `path, with_init`
**Decorators:** ``

**Docstring:**
```
Create a folder in the given path and add an `__init__.py` file (optional).

:param path: Folder path.
:param with_init: Create `__init__.py` in the new folder.
```
### `set_user`
**Arguments:** `username`
**Decorators:** ``

**Docstring:**
```
Set current user.

:param username: **User** name to set as current user.
```
### `get_user`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_roles`
**Arguments:** `username`
**Decorators:** ``

**Docstring:**
```
Return roles of current user.
```
### `get_request_header`
**Arguments:** `key, default`
**Decorators:** ``

**Docstring:**
```
Return HTTP request header.

:param key: HTTP header key.
:param default: Default value.
```
### `sendmail`
**Arguments:** `recipients, sender, subject, message, as_markdown, delayed, reference_doctype, reference_name, unsubscribe_method, unsubscribe_params, unsubscribe_message, add_unsubscribe_link, attachments, content, doctype, name, reply_to, queue_separately, cc, bcc, message_id, in_reply_to, send_after, expose_recipients, send_priority, communication, retry, now, read_receipt, is_notification, inline_images, template, args, header, print_letterhead, with_container, email_read_tracker_url, x_priority, email_headers`
**Decorators:** ``

**Docstring:**
```
Send email using user's default **Email Account** or global default **Email Account**.


:param recipients: List of recipients.
:param sender: Email sender. Default is current user or default outgoing account.
:param subject: Email Subject.
:param message: (or `content`) Email Content.
:param as_markdown: Convert content markdown to HTML.
:param delayed: Send via scheduled email sender **Email Queue**. Don't send immediately. Default is true
:param send_priority: Priority for Email Queue, default 1.
:param reference_doctype: (or `doctype`) Append as communication to this DocType.
:param reference_name: (or `name`) Append as communication to this document name.
:param unsubscribe_method: Unsubscribe url with options email, doctype, name. e.g. `/api/method/unsubscribe`
:param unsubscribe_params: Unsubscribe paramaters to be loaded on the unsubscribe_method [optional] (dict).
:param attachments: List of attachments.
:param reply_to: Reply-To Email Address.
:param message_id: Used for threading. If a reply is received to this email, Message-Id is sent back as In-Reply-To in received email.
:param in_reply_to: Used to send the Message-Id of a received email back as In-Reply-To.
:param send_after: Send after the given datetime.
:param expose_recipients: Display all recipients in the footer message - "This email was sent to"
:param communication: Communication link to be set in Email Queue record
:param inline_images: List of inline images as {"filename", "filecontent"}. All src properties will be replaced with random Content-Id
:param template: Name of html template from templates/emails folder
:param args: Arguments for rendering the template
:param header: Append header in email
:param with_container: Wraps email inside a styled container
:param x_priority: 1 = HIGHEST, 3 = NORMAL, 5 = LOWEST
:param email_headers: Additional headers to be added in the email, e.g. {"X-Custom-Header": "value"} or {"Custom-Header": "value"}. Automatically prepends "X-" to the header name if not present.
```
### `whitelist`
**Arguments:** `allow_guest, xss_safe, methods`
**Decorators:** ``

**Docstring:**
```
Decorator for whitelisting a function and making it accessible via HTTP.
Standard request will be `/api/method/[path.to.method]`

:param allow_guest: Allow non logged-in user to access this method.
:param methods: Allowed http method to access the method.

Use as:

        @frappe.whitelist()
        def myfunc(param1, param2):
                pass
```
### `is_whitelisted`
**Arguments:** `method`
**Decorators:** ``

**Docstring:**
```

```
### `read_only`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `write_only`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `only_for`
**Arguments:** `roles, message`
**Decorators:** ``

**Docstring:**
```
Raises `frappe.PermissionError` if the user does not have any of the permitted roles.

:param roles: Permitted role(s)
```
### `get_domain_data`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```

```
### `only_has_select_perm`
**Arguments:** `doctype, user, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `has_permission`
**Arguments:** `doctype, ptype, doc, user, throw`
**Decorators:** ``

**Docstring:**
```
Return True if the user has permission `ptype` for given `doctype` or `doc`.

Raise `frappe.PermissionError` if user isn't permitted and `throw` is truthy

:param doctype: DocType for which permission is to be check.
:param ptype: Permission type (`read`, `write`, `create`, `submit`, `cancel`, `amend`). Default: `read`.
:param doc: [optional] Checks User permissions for given doc.
:param user: [optional] Check for given user. Default: current user.
:param parent_doctype: Required when checking permission for a child DocType (unless doc is specified).
```
### `has_website_permission`
**Arguments:** `doc, ptype, user, verbose, doctype`
**Decorators:** ``

**Docstring:**
```
Raises `frappe.PermissionError` if not permitted.

:param doctype: DocType for which permission is to be check.
:param ptype: Permission type (`read`, `write`, `create`, `submit`, `cancel`, `amend`). Default: `read`.
:param doc: Checks User permissions for given doc.
:param user: [optional] Check for given user. Default: current user.
```
### `is_table`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return True if `istable` property (indicating child Table) is set for given DocType.
```
### `get_precision`
**Arguments:** `doctype, fieldname, currency, doc`
**Decorators:** ``

**Docstring:**
```
Get precision for a given field
```
### `generate_hash`
**Arguments:** `txt, length`
**Decorators:** ``

**Docstring:**
```
Generate random hash using best available randomness source.
```
### `new_doc`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return a new document of the given DocType with defaults set.

:param doctype: DocType of the new document.
:param parent_doc: [optional] add to parent document.
:param parentfield: [optional] add against this `parentfield`.
:param as_dict: [optional] return as dictionary instead of Document.
:param kwargs: [optional] You can specify fields as field=value pairs in function call.
```
### `set_value`
**Arguments:** `doctype, docname, fieldname, value`
**Decorators:** ``

**Docstring:**
```
Set document value. Calls `frappe.client.set_value`
```
### `get_cached_doc`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Identical to `frappe.get_doc`, but return from cache if available.
```
### `_set_document_in_cache`
**Arguments:** `key, doc`
**Decorators:** ``

**Docstring:**
```

```
### `can_cache_doc`
**Arguments:** `args`
**Decorators:** ``

**Docstring:**
```
Determine if document should be cached based on get_doc params.
Return cache key if doc can be cached, None otherwise.
```
### `get_document_cache_key`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `clear_document_cache`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_cached_value`
**Arguments:** `doctype, name, fieldname, as_dict`
**Decorators:** ``

**Docstring:**
```

```
### `get_single_value`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the cached value associated with the given fieldname from single DocType.

Usage:
        telemetry_enabled = frappe.get_single_value("System Settings", "telemetry_enabled")
```
### `get_last_doc`
**Arguments:** `doctype, filters, order_by`
**Decorators:** ``

**Docstring:**
```
Get last created document of this type.
```
### `get_single`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return a `frappe.model.document.Document` object of the given Single doctype.
```
### `get_meta_module`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `delete_doc`
**Arguments:** `doctype, name, force, ignore_doctypes, for_reload, ignore_permissions, flags, ignore_on_trash, ignore_missing, delete_permanently`
**Decorators:** ``

**Docstring:**
```
Delete a document. Calls `frappe.model.delete_doc.delete_doc`.

:param doctype: DocType of document to be delete.
:param name: Name of document to be delete.
:param force: Allow even if document is linked. Warning: This may lead to data integrity errors.
:param ignore_doctypes: Ignore if child table is one of these.
:param for_reload: Call `before_reload` trigger before deleting.
:param ignore_permissions: Ignore user permissions.
:param delete_permanently: Do not create a Deleted Document for the document.
```
### `delete_doc_if_exists`
**Arguments:** `doctype, name, force`
**Decorators:** ``

**Docstring:**
```
Delete document if exists.
```
### `reload_doctype`
**Arguments:** `doctype, force, reset_permissions`
**Decorators:** ``

**Docstring:**
```
Reload DocType from model (`[module]/[doctype]/[name]/[name].json`) files.
```
### `reload_doc`
**Arguments:** `module, dt, dn, force, reset_permissions`
**Decorators:** ``

**Docstring:**
```
Reload Document from model (`[module]/[doctype]/[name]/[name].json`) files.

:param module: Module name.
:param dt: DocType name.
:param dn: Document name.
:param force: Reload even if `modified` timestamp matches.
```
### `rename_doc`
**Arguments:** `doctype, old, new, force, merge`
**Decorators:** ``

**Docstring:**
```
Renames a doc(dt, old) to doc(dt, new) and updates all linked fields of type "Link"

Calls `frappe.model.rename_doc.rename_doc`
```
### `get_module`
**Arguments:** `modulename`
**Decorators:** ``

**Docstring:**
```
Return a module object for given Python module name using `importlib.import_module`.
```
### `scrub`
**Arguments:** `txt`
**Decorators:** ``

**Docstring:**
```
Return sluggified string. e.g. `Sales Order` becomes `sales_order`.
```
### `unscrub`
**Arguments:** `txt`
**Decorators:** ``

**Docstring:**
```
Return titlified string. e.g. `sales_order` becomes `Sales Order`.
```
### `get_module_path`
**Arguments:** `module`
**Decorators:** ``

**Docstring:**
```
Get the path of the given module name.

:param module: Module name.
:param *joins: Join additional path elements using `os.path.join`.
```
### `get_app_path`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Return path of given app.

:param app: App name.
:param *joins: Join additional path elements using `os.path.join`.
```
### `get_app_source_path`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Return source path of given app.

:param app: App name.
:param *joins: Join additional path elements using `os.path.join`.
```
### `get_site_path`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return path of current site.

:param *joins: Join additional path elements using `os.path.join`.
```
### `get_pymodule_path`
**Arguments:** `modulename`
**Decorators:** ``

**Docstring:**
```
Return path of given Python module name.

:param modulename: Python module name.
:param *joins: Join additional path elements using `os.path.join`.
```
### `get_module_list`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```
Get list of modules for given all via `app/modules.txt`.
```
### `get_all_apps`
**Arguments:** `with_internal_apps, sites_path`
**Decorators:** ``

**Docstring:**
```
Get list of all apps via `sites/apps.txt`.
```
### `get_installed_apps`
**Arguments:** ``
**Decorators:** `request_cache`

**Docstring:**
```
Get list of installed apps in current site.

:param _ensure_on_bench: Only return apps that are present on bench.
```
### `get_doc_hooks`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return hooked methods for given doc. Expand the dict tuple if required.
```
### `_load_app_hooks`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_hooks`
**Arguments:** `hook, default, app_name`
**Decorators:** ``

**Docstring:**
```
Get hooks via `app/hooks.py`

:param hook: Name of the hook. Will gather all hooks for this name and return as a list.
:param default: Default if no hook found.
:param app_name: Filter by app.
```
### `append_hook`
**Arguments:** `target, key, value`
**Decorators:** ``

**Docstring:**
```
appends a hook to the the target dict.

If the hook key, exists, it will make it a key.

If the hook value is a dict, like doc_events, it will
listify the values against the key.
```
### `setup_module_map`
**Arguments:** `include_all_apps`
**Decorators:** ``

**Docstring:**
```
Function to rebuild map of all modules

:param: include_all_apps: Include all apps on bench, or just apps installed on the site.
:return: Nothing
```
### `get_file_items`
**Arguments:** `path, raise_not_found, ignore_empty_lines`
**Decorators:** ``

**Docstring:**
```
Return items from text file as a list. Ignore empty lines.
```
### `get_file_json`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Read a file and return parsed JSON object.
```
### `read_file`
**Arguments:** `path, raise_not_found, as_base64`
**Decorators:** ``

**Docstring:**
```
Open a file and return its content as Unicode or Base64 string.
```
### `get_attr`
**Arguments:** `method_string`
**Decorators:** ``

**Docstring:**
```
Get python method object from its name.
```
### `call`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Call a function and match arguments.
```
### `_get_cached_signature_params`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```
Get cached parameters for a function.
Returns a dictionary of parameters and a boolean indicating if the function has **kwargs.
```
### `get_newargs`
**Arguments:** `fn, kwargs`
**Decorators:** ``

**Docstring:**
```
Remove any kwargs that are not supported by the function.

Example:
        >>> def fn(a=1, b=2):
        ...     pass

        >>> get_newargs(fn, {"a": 2, "c": 1})
                {"a": 2}
```
### `make_property_setter`
**Arguments:** `args, ignore_validate, validate_fields_for_doctype, is_system_generated`
**Decorators:** ``

**Docstring:**
```
Create a new **Property Setter** (for overriding DocType and DocField properties).

If doctype is not specified, it will create a property setter for all fields with the
given fieldname
```
### `import_doc`
**Arguments:** `path`
**Decorators:** ``

**Docstring:**
```
Import a file using Data Import.
```
### `copy_doc`
**Arguments:** `doc, ignore_no_copy`
**Decorators:** ``

**Docstring:**
```
No_copy fields also get copied.
```
### `respond_as_web_page`
**Arguments:** `title, html, success, http_status_code, context, indicator_color, primary_action, primary_label, fullpage, width, template`
**Decorators:** ``

**Docstring:**
```
Send response as a web page with a message rather than JSON. Used to show permission errors etc.

:param title: Page title and heading.
:param message: Message to be shown.
:param success: Alert message.
:param http_status_code: HTTP status code
:param context: web template context
:param indicator_color: color of indicator in title
:param primary_action: route on primary button (default is `/`)
:param primary_label: label on primary button (default is "Home")
:param fullpage: hide header / footer
:param width: Width of message in pixels
:param template: Optionally pass view template
```
### `redirect`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Raise a 301 redirect to url
```
### `redirect_to_message`
**Arguments:** `title, html, http_status_code, context, indicator_color`
**Decorators:** ``

**Docstring:**
```
Redirects to /message?id=random
Similar to respond_as_web_page, but used to 'redirect' and show message pages like success, failure, etc. with a detailed message

:param title: Page title and heading.
:param message: Message to be shown.
:param http_status_code: HTTP status code.

Example Usage:
        frappe.redirect_to_message(_('Thank you'), "<div><p>You will receive an email at test@example.com</p></div>")
```
### `build_match_conditions`
**Arguments:** `doctype, as_condition`
**Decorators:** ``

**Docstring:**
```
Return match (User permissions) for given doctype as list or SQL.
```
### `get_list`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
List database query via `frappe.model.db_query`. Will also check for permissions.

:param doctype: DocType on which query is to be made.
:param fields: List of fields or `*`.
:param filters: List of filters (see example).
:param order_by: Order By e.g. `creation desc`.
:param limit_start: Start results at record #. Default 0.
:param limit_page_length: No of records in the page. Default 20.

Example usage:

        # simple dict filter
        frappe.get_list("ToDo", fields=["name", "description"], filters = {"owner":"test@example.com"})

        # filter as a list of lists
        frappe.get_list("ToDo", fields="*", filters = [["modified", ">", "2014-01-01"]])
```
### `get_all`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
List database query via `frappe.model.db_query`. Will **not** check for permissions.
Parameters are same as `frappe.get_list`

:param doctype: DocType on which query is to be made.
:param fields: List of fields or `*`. Default is: `["name"]`.
:param filters: List of filters (see example).
:param order_by: Order By e.g. `creation desc`.
:param limit_start: Start results at record #. Default 0.
:param limit_page_length: No of records in the page. Default 20.

Example usage:

        # simple dict filter
        frappe.get_all("ToDo", fields=["name", "description"], filters = {"owner":"test@example.com"})

        # filter as a list of lists
        frappe.get_all("ToDo", fields=["*"], filters = [["modified", ">", "2014-01-01"]])
```
### `get_value`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return a document property or list of properties.

Alias for `frappe.db.get_value`

:param doctype: DocType name.
:param filters: Filters like `{"x":"y"}` or name of the document. `None` if Single DocType.
:param fieldname: Column name.
:param ignore: Don't raise exception if table, column is missing.
:param as_dict: Return values as dict.
:param debug: Print query in error log.
```
### `as_json`
**Arguments:** `obj, indent, separators, ensure_ascii`
**Decorators:** ``

**Docstring:**
```
Return the JSON string representation of the given `obj`.
```
### `are_emails_muted`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `attach_print`
**Arguments:** `doctype, name, file_name, print_format, style, html, doc, lang, print_letterhead, password, letterhead`
**Decorators:** ``

**Docstring:**
```

```
### `task`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_doctype_app`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `logger`
**Arguments:** `module, with_more_info, allow_site, filter, max_size, file_count`
**Decorators:** ``

**Docstring:**
```
Return a python logger that uses StreamHandler.
```
### `get_desk_link`
**Arguments:** `doctype, name, show_title_with_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_website_settings`
**Arguments:** `key`
**Decorators:** ``

**Docstring:**
```

```
### `get_active_domains`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_setup_complete`
**Arguments:** ``
**Decorators:** `request_cache`

**Docstring:**
```

```
### `ping`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `validate_and_sanitize_search_inputs`
**Arguments:** `fn`
**Decorators:** ``

**Docstring:**
```

```
### `override_whitelisted_method`
**Arguments:** `original_method`
**Decorators:** ``

**Docstring:**
```
Return the last override or the original whitelisted method.
```

