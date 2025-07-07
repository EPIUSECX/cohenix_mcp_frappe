# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/database/database.py`

## Classes

### `Database`


**Docstring:**
```
Open a database connection with the given parmeters, if use_default is True, use the
login details from `conf.py`. This is called by the request handler and is accessible using
the `db` global variable. the `sql` method is also global to run queries
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, socket, host, user, password, port, cur_db_name` | `` |  |
| `setup_type_map` | `self` | `` |  |
| `connect` | `self` | `` | Connects to a database as set in `site_config.json`. |
| `set_execution_timeout` | `self, seconds` | `` | Set session speicifc timeout on exeuction of statements.
If any statement takes more time it will be killed along with entire transaction. |
| `use` | `self, db_name` | `` | `USE` db_name. |
| `get_connection` | `self` | `` | Return a Database connection object that conforms with https://peps.python.org/pep-0249/#connection-objects. |
| `get_database_size` | `self` | `` |  |
| `_transform_query` | `self, query, values` | `` |  |
| `_transform_result` | `self, result` | `` |  |
| `_clean_up` | `self` | `` |  |
| `sql` | `self, query, values` | `` | Execute a SQL query and fetch all rows.

:param query: SQL query.
:param values: Tuple / List / Dict of values to be escaped and substituted in the query.
:param as_dict: Return as a dictionary.
:param as_list: Always return as a list.
:param debug: Print query and `EXPLAIN` in debug log.
:param ignore_ddl: Catch exception if table, column missing.
:param auto_commit: Commit after executing the query.
:param update: Update this dict to all rows (if returned `as_dict`).
:param run: Return query without executing it if False.
:param pluck: Get the plucked field only.
:param explain: Print `EXPLAIN` in error log.
:param as_iterator: Returns iterator over results instead of fetching all results at once.
        This should be used with unbuffered cursor as default cursors used by pymysql and postgres
        buffer the results internally. See `Database.unbuffered_cursor`.
Examples:

        # return customer names as dicts
        frappe.db.sql("select name from tabCustomer", as_dict=True)

        # return names beginning with a
        frappe.db.sql("select name from tabCustomer where name like %s", "a%")

        # values as dict
        frappe.db.sql("select name from tabCustomer where name like %(name)s and owner=%(owner)s",
                {"name": "a%", "owner":"test@example.com"}) |
| `_return_as_iterator` | `self` | `` |  |
| `execute_query` | `self, query, values` | `` |  |
| `_log_query` | `self, mogrified_query, query_type, debug, unmogrified_query` | `` | Takes the query and logs it to various interfaces according to the settings. |
| `log_query` | `self, query, query_type, values, debug` | `` |  |
| `mogrify` | `self, query, values` | `` | build the query string with values |
| `lazy_mogrify` | `self, query, values` | `` | Wrap the object with str to generate mogrified query. |
| `explain_query` | `self, query, values` | `` | Print `EXPLAIN` in error log. |
| `sql_list` | `self, query, values, debug` | `` | Return data as list of single elements (first column).

Example:

        # doctypes = ["DocType", "DocField", "User", ...]
        doctypes = frappe.db.sql_list("select name from DocType") |
| `sql_ddl` | `self, query, debug` | `` | Commit and execute a query. DDL (Data Definition Language) queries that alter schema
autocommit in MariaDB. |
| `check_transaction_status` | `self, query, query_type` | `` | Raises exception if more than 200,000 `INSERT`, `UPDATE` queries are
executed in one transaction. This is to ensure that writes are always flushed otherwise this
could cause the system to hang. |
| `check_implicit_commit` | `self, query, query_type` | `` |  |
| `fetch_as_dict` | `self, result` | `` | Internal. Convert results to dict. |
| `clear_db_table_cache` | `query_type` | `staticmethod` |  |
| `get_description` | `self` | `` | Return result metadata. |
| `convert_to_lists` | `res` | `staticmethod` | Convert tuple output to lists (internal). |
| `get` | `self, doctype, filters, as_dict, cache` | `` | Return `get_value` with fieldname='*'. |
| `get_value` | `self, doctype, filters, fieldname, ignore, as_dict, debug, order_by, cache, for_update` | `` | Return a document property or list of properties.

:param doctype: DocType name.
:param filters: Filters like `{"x":"y"}` or name of the document. `None` if Single DocType.
:param fieldname: Column name.
:param ignore: Don't raise exception if table, column is missing.
:param as_dict: Return values as dict.
:param debug: Print query in error log.
:param order_by: Column to order by
:param cache: Use cached results fetched during current job/request
:param pluck: pluck first column instead of returning as nested list or dict.
:param for_update: All the affected/read rows will be locked.
:param skip_locked: Skip selecting currently locked rows.
:param wait: Wait for aquiring lock

Example:

        # return first customer starting with a
        frappe.db.get_value("Customer", {"name": ("like a%")})

        # return last login of **User** `test@example.com`
        frappe.db.get_value("User", "test@example.com", "last_login")

        last_login, last_ip = frappe.db.get_value("User", "test@example.com",
                ["last_login", "last_ip"])

        # returns default date_format
        frappe.db.get_value("System Settings", None, "date_format") |
| `get_values` | `self, doctype, filters, fieldname, ignore, as_dict, debug, order_by, update, cache, for_update` | `` | Return multiple document properties.

:param doctype: DocType name.
:param filters: Filters like `{"x":"y"}` or name of the document.
:param fieldname: Column name.
:param ignore: Don't raise exception if table, column is missing.
:param as_dict: Return values as dict.
:param debug: Print query in error log.
:param order_by: Column to order by,
:param distinct: Get Distinct results.

Example:

        # return first customer starting with a
        customers = frappe.db.get_values("Customer", {"name": ("like a%")})

        # return last login of **User** `test@example.com`
        user = frappe.db.get_values("User", "test@example.com", "*")[0] |
| `get_values_from_single` | `self, fields, filters, doctype, as_dict, debug, update` | `` | Get values from `tabSingles` (Single DocTypes) (internal).

:param fields: List of fields,
:param filters: Filters (dict).
:param doctype: DocType name. |
| `get_singles_dict` | `self, doctype, debug` | `` | Get Single DocType as dict.

:param doctype: DocType of the single object whose value is requested
:param debug: Execute query in debug mode - print to STDOUT
:param for_update: Take `FOR UPDATE` lock on the records
:param cast: Cast values to Python data types based on field type

Example:

        # Get coulmn and value of the single doctype Accounts Settings
        account_settings = frappe.db.get_singles_dict("Accounts Settings") |
| `get_all` | `` | `staticmethod` |  |
| `get_list` | `` | `staticmethod` |  |
| `_get_update_dict` | `fieldname, value` | `staticmethod` | Create update dict that represents column-values to be updated. |
| `set_single_value` | `self, doctype, fieldname, value` | `` | Set field value of Single DocType.

:param doctype: DocType of the single object
:param fieldname: `fieldname` of the property
:param value: `value` of the property

Example:

        # Update the `deny_multiple_sessions` field in System Settings DocType.
        frappe.db.set_single_value("System Settings", "deny_multiple_sessions", True) |
| `get_single_value` | `self, doctype, fieldname, cache` | `` | Get property of Single DocType. Cache locally by default

:param doctype: DocType of the single object whose value is requested
:param fieldname: `fieldname` of the property whose value is requested

Example:

        # Get the default value of the company from the Global Defaults doctype.
        company = frappe.db.get_single_value('Global Defaults', 'default_company') |
| `get_singles_value` | `self` | `` | Alias for get_single_value |
| `set_value` | `self, dt, dn, field, val, modified, modified_by, update_modified, debug` | `` | Set a single value in the database, do not call the ORM triggers
but update the modified timestamp (unless specified not to).

**Warning:** this function will not call Document events and should be avoided in normal cases.

:param dt: DocType name.
:param dn: Document name for updating single record or filters for updating many records.
:param field: Property / field name or dictionary of values to be updated
:param value: Value to be updated.
:param modified: Use this as the `modified` timestamp.
:param modified_by: Set this user as `modified_by`.
:param update_modified: default True. Set as false, if you don't want to update the timestamp.
:param debug: Print the query in the developer / js console. |
| `bulk_update` | `self, doctype, doc_updates` | `` | :param doctype: DocType to update
:param doc_updates: Dictionary of key (docname) and values to update
:param chunk_size: Number of documents to update in a single transaction
:param modified: Use this as the `modified` timestamp.
:param modified_by: Set this user as `modified_by`.
:param update_modified: default True. Update `modified` and `modified_by` fields
:param debug: Print the query in the developer / js console.

doc_updates should be in the following format:
```py
{
    "docname1": {
        "field1": "value1",
        "field2": "value2",
        ...
    },
    "docname2": {
        "field1": "value1",
        "field2": "value2",
        ...
    },
}
```

Note:
    - Bigger chunk sizes could be less performant. Use appropriate chunk size based on the number of fields to update. |
| `_build_and_run_bulk_update_query` | `doctype, doc_updates, modified_dict, debug` | `staticmethod` | :param doctype: DocType to update
:param doc_updates: Dictionary of key (docname) and values to update
:param debug: Print the query in the developer / js console.

---

doc_updates should be in the following format:
```py
{
    "docname1": {
        "field1": "value1",
        "field2": "value2",
        ...
    },
    "docname2": {
        "field1": "value1",
        "field2": "value2",
        ...
    },
}
```

---

Query will be built as:
```sql
UPDATE `tabItem`
SET `status` = CASE
    WHEN `name` = 'Item-1' THEN 'Close'
    WHEN `name` = 'Item-2' THEN 'Open'
    WHEN `name` = 'Item-3' THEN 'Close'
    WHEN `name` = 'Item-4' THEN 'Cancelled'
    ELSE `status`
end,
`description` = CASE
    WHEN `name` = 'Item-1' THEN 'This is the first task'
    WHEN `name` = 'Item-2' THEN 'This is the second task'
    WHEN `name` = 'Item-3' THEN 'This is the third task'
    WHEN `name` = 'Item-4' THEN 'This is the fourth task'
    ELSE `description`
end
WHERE  `name` IN ( 'Item-1', 'Item-2', 'Item-3', 'Item-4' )
``` |
| `set_global` | `self, key, val, user` | `` | Save a global key value. Global values will be automatically set if they match fieldname. |
| `get_global` | `self, key, user` | `` | Return a global key value. |
| `get_default` | `self, key, parent` | `` | Return default value as a list if multiple or single. |
| `set_default` | `key, val, parent, parenttype` | `staticmethod` | Sets a global / user default value. |
| `add_default` | `key, val, parent, parenttype` | `staticmethod` | Append a default value for a key, there can be multiple default values for a particular key. |
| `get_defaults` | `key, parent` | `staticmethod` | Get all defaults |
| `begin` | `self` | `` |  |
| `commit` | `self` | `` | Commit current transaction. Calls SQL `COMMIT`. |
| `rollback` | `self` | `` | `ROLLBACK` current transaction. Optionally rollback to a known save_point. |
| `savepoint` | `self, save_point` | `` | Savepoints work as a nested transaction.

Changes can be undone to a save point by doing frappe.db.rollback(save_point)

Note: rollback watchers can not work with save points.
        so only changes to database are undone when rolling back to a savepoint.
        Avoid using savepoints when writing to filesystem. |
| `release_savepoint` | `self, save_point` | `` |  |
| `field_exists` | `self, dt, fn` | `` | Return true of field exists. |
| `table_exists` | `self, doctype, cached` | `` | Return True if table for given doctype exists. |
| `has_table` | `self, doctype` | `` |  |
| `get_tables` | `self, cached` | `` |  |
| `a_row_exists` | `self, doctype` | `` | Return True if at least one row exists. |
| `exists` | `self, dt, dn, cache` | `` | Return the document name of a matching document, or None.

Note: `cache` only works if `dt` and `dn` are of type `str`.

## Examples

Pass doctype and docname (only in this case we can cache the result)

```
exists("User", "jane@example.org", cache=True)
```

Pass a dict of filters including the `"doctype"` key:

```
exists({"doctype": "User", "full_name": "Jane Doe"})
```

Pass the doctype and a dict of filters:

```
exists("User", {"full_name": "Jane Doe"})
``` |
| `count` | `self, dt, filters, debug, cache, distinct` | `` | Return `COUNT(*)` for given DocType and filters. |
| `estimate_count` | `self, doctype` | `` | Get estimated count of total rows in a table. |
| `format_date` | `date` | `staticmethod` |  |
| `format_datetime` | `datetime` | `staticmethod` |  |
| `get_creation_count` | `self, doctype, minutes` | `` | Get count of records created in the last x minutes |
| `get_db_table_columns` | `self, table` | `` | Return list of column names from given table. |
| `get_table_columns` | `self, doctype` | `` | Return list of column names from given doctype. |
| `has_column` | `self, doctype, column` | `` | Return True if column exists in database. |
| `has_index` | `self, table_name, index_name` | `` |  |
| `add_index` | `self, doctype, fields, index_name` | `` |  |
| `add_unique` | `self, doctype, fields, constraint_name` | `` |  |
| `get_index_name` | `fields` | `staticmethod` |  |
| `get_system_setting` | `self, key` | `` |  |
| `close` | `self` | `` | Close database connection. |
| `escape` | `s, percent` | `staticmethod` | Escape quotes and percent in given string. |
| `get_descendants` | `self, doctype, name` | `` | Return descendants of the group node in tree |
| `is_missing_table_or_column` | `self, e` | `` |  |
| `multisql` | `self, sql_dict, values` | `` |  |
| `delete` | `self, doctype, filters, debug` | `` | Delete rows from a table in site which match the passed filters. This
does not trigger DocType hooks. Simply runs a DELETE query in the database.

Doctype name can be passed directly, it will be pre-pended with `tab`. |
| `truncate` | `self, doctype` | `` | Truncate a table in the database. This runs a DDL command `TRUNCATE TABLE`.
This cannot be rolled back.

Doctype name can be passed directly, it will be pre-pended with `tab`. |
| `get_last_created` | `self, doctype` | `` |  |
| `log_touched_tables` | `self, query, query_type` | `` |  |
| `bulk_insert` | `self, doctype, fields, values, ignore_duplicates` | `` | Insert multiple records at a time

:param doctype: Doctype name
:param fields: list of fields
:params values: iterable of values |
| `create_sequence` | `self` | `` |  |
| `set_next_sequence_val` | `self` | `` |  |
| `get_next_sequence_val` | `self` | `` |  |
| `get_row_size` | `self, doctype` | `` | Get estimated max row size of any table in bytes. |
| `rename_column` | `self, doctype, old_column_name, new_column_name` | `` |  |
| `unbuffered_cursor` | `self` | `contextmanager` | Context manager to temporarily use unbuffered cursor.

Using this with `as_iterator=True` provides O(1) memory usage while reading large result sets.

NOTE: You MUST do entire result set processing in the context, otherwise underlying cursor
will be switched and you'll not get complete results.

Usage:
        with frappe.db.unbuffered_cursor():
                for row in frappe.db.sql("query with huge result", as_iterator=True):
                        continue # Do some processing. |





## Functions

### `savepoint`
**Arguments:** `catch`
**Decorators:** `contextmanager`

**Docstring:**
```
Wrapper for wrapping blocks of DB operations in a savepoint.

as contextmanager:

for doc in docs:
        with savepoint(catch=DuplicateError):
                doc.insert()

as decorator (wraps FULL function call):

@savepoint(catch=DuplicateError)
def process_doc(doc):
        doc.insert()
```
### `get_query_execution_timeout`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get execution timeout based on current timeout in different contexts.

    HTTP requests: HTTP timeout or a default (300)
    Background jobs: Job timeout
Console/Commands: No timeout = 0.

    Note: Timeout adds 1.5x as "safety factor"
```
### `get_print_sql_flag`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

