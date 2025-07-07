# Model Context Profile: `query_builder`

## 1. Module Overview

The `query_builder` module provides a high-level, Pythonic API for constructing SQL queries, abstracting away the differences between database backends like MariaDB and PostgreSQL. It is built on top of the `pypika` library and is the recommended way to build complex, safe, and maintainable database queries in modern Frappe development.

Key functionalities are expected to include:
-   A fluent API for building `SELECT`, `INSERT`, `UPDATE`, and `DELETE` queries.
-   Automatic handling of table name quoting (e.g., `tabDocType`).
-   Integration with Frappe's permission system.
-   Methods for creating complex joins, filters, and aggregations.

## 2. File Index

-   **`builder.py`**: Defines the core query builder classes (`MariaDB`, `Postgres`, `SQLite`) that inherit from `pypika`'s query classes and add Frappe-specific customizations.
-   **`functions.py`**: Implements a mapping from generic function calls (e.g., `GroupConcat`, `CombineDatetime`) to their database-specific SQL function names (e.g., `GROUP_CONCAT` for MariaDB, `STRING_AGG` for PostgreSQL).
-   **`terms.py`**: Contains custom `pypika` term classes, which are the building blocks of queries.
-   **`utils.py`**: Contains helper functions and the crucial `patch_all()` function, which monkey-patches the query builder methods onto the `pypika` classes at runtime.
-   **`custom.py`**: Defines custom, non-standard SQL functions that are specific to Frappe's needs, like `MATCH` for full-text search.

## 3. Public API / Callable Functions

The entire public API of this module is exposed through the `frappe.qb` object. This object is an instance of one of the builder classes (`MariaDB`, `Postgres`, or `SQLite`) depending on the database driver in use.

**Key `frappe.qb` Methods:**

-   **`frappe.qb.from_(doctype)`**: The starting point for any `SELECT` query.
-   **`frappe.qb.into(doctype)`**: The starting point for an `INSERT` query.
-   **`frappe.qb.update(doctype)`**: The starting point for an `UPDATE` query.
-   **`.select(field1, field2, ...)`**: Specifies the columns to retrieve.
-   **`.where(condition)`**: Adds a `WHERE` clause to the query. Can be chained for multiple conditions.
-   **`.run(as_dict=False)`**: Executes the query and returns the result.

**Example Usage:**
```python
from frappe.query_builder.functions import Count

user = frappe.qb.DocType("User")
query = (
    frappe.qb.from_(user)
    .select(user.name, Count(user.name).as_("login_count"))
    .where(user.enabled == 1)
    .groupby(user.name)
    .orderby(user.name)
)
# The .run() method is patched in by utils.py
users = query.run(as_dict=True)
```

## 4. Detailed Walkthrough

### `builder.py`

This file is the foundation of the query builder. It defines a `Base` class and specific classes for each supported database.

-   **`Base` Class**: This class provides common functionalities, most importantly the `DocType` static method, which is a wrapper around `pypika.Table`. It automatically prepends `tab` to the DocType name, so developers can write `frappe.qb.DocType("User")` instead of `frappe.qb.Table("tabUser")`.
-   **`MariaDB`, `Postgres`, `SQLite` Classes**: These classes inherit from both the `Base` class and the corresponding `pypika` query class (e.g., `MySQLQuery`, `PostgreSQLQuery`). This is how they gain the pypika's fluent API (`.select`, `.where`, etc.). They primarily override the `_builder` method to inject Frappe-specific customizations. The `Postgres` class also contains logic to translate MariaDB-specific field names and schema names to their PostgreSQL equivalents.

### `functions.py`

This file provides a database-agnostic way to use SQL functions.

-   **`ImportMapper`**: This is a clever utility class. It's initialized with a dictionary mapping a database type to a specific function implementation (e.g., `{db_type_is.MARIADB: GROUP_CONCAT, db_type_is.POSTGRES: STRING_AGG}`). When called, it checks the current database type (`frappe.conf.db_type`) and returns the correct function class.
-   **Function Mappings**: The file defines several of these mappings for common functions that have different names or implementations across databases, such as `GroupConcat`, `Match` (for full-text search), `CombineDatetime`, and `UnixTimestamp`. This allows developers to write `GroupConcat("name")` in their query, and the query builder will automatically generate the correct SQL (`GROUP_CONCAT` or `STRING_AGG`) for the target database.

### `utils.py`

This file is the glue that holds the module together.

-   **`get_query_builder(type_of_db)`**: This function is called once at startup to get the correct builder class (`MariaDB`, `Postgres`, or `SQLite`) based on the database configuration. The result is assigned to `frappe.qb`.
-   **`patch_all()`**: This is a critical function that is called at startup. It performs monkey-patching to make the query builder more convenient to use:
    -   `patch_query_execute()`: Adds the `.run()` and `.walk()` methods to the `QueryBuilder` class, so developers can execute a query directly from the query object instead of passing it to `frappe.db.sql()`.
    -   `patch_query_aggregation()`: Adds convenient aggregation methods like `.max()`, `.min()`, `.avg()`, and `.sum()` directly to the builder class.
-   **`prepare_query(query)`**: This function takes a built query object, calls its `.get_sql()` method to generate the final SQL string, and extracts the parameters for safe, parameterized execution by the database driver. It also includes a security check to prevent non-`SELECT` queries from being run from server scripts.