# Model Context Profile: `database`

## 1. Module Overview

The `database` module is a fundamental part of the Frappe Framework, providing a generic abstraction layer for all database operations. It allows the framework to support multiple database backends (MariaDB and PostgreSQL) by providing a unified API for schema manipulation (DDL) and data querying/manipulation (DML).

Key functionalities are expected to include:
-   Database connection management.
-   A generic `Database` class with methods like `get_value`, `get_all`, `sql`, `sql_ddl`.
-   Specific database classes (`MariaDBDatabase`, `PostgresDatabase`) that inherit from the generic class and implement database-specific logic.
-   Schema management tools for creating, altering, and deleting tables and columns.
-   The Query Builder (`frappe.qb`), which is likely defined or heavily utilized here.

## 2. File Index

-   **`database.py`**: Defines the abstract `Database` class, which serves as the primary interface for all database interactions (`frappe.db`).
-   **`mariadb/database.py`**: Contains the `MariaDBDatabase` class, which inherits from `Database` and implements the specific logic for MariaDB.
-   **`postgres/database.py`**: Contains the `PostgresDatabase` class, which implements the specific logic for PostgreSQL.
-   **`schema.py`**: Defines the `DBTable` and `DbColumn` classes, which are used to manage database schema based on DocType definitions.
-   **`db_manager.py`**: Contains logic for managing the database instance itself, such as creating and dropping databases and users.
-   **`query.py`**: Contains the `Query` class, which is a precursor to the modern Query Builder.
-   **`sequence.py`**: Contains logic for managing database sequences, used for autoincrementing fields.

## 3. Public API / Callable Functions

The entire `frappe.db` object is the public API for this module. It is an instance of either `MariaDBDatabase` or `PostgresDatabase`.

**Key Methods on `frappe.db`:**

-   **`sql(query, values, as_dict)`**: The fundamental method for executing any SQL query. It returns a list of tuples by default, or a list of dicts if `as_dict=True`.
-   **`get_value(doctype, filters, fieldname)`**: A high-level method to fetch a single value from a single document.
-   **`get_all(doctype, filters, fields)`**: A high-level method to fetch multiple records matching certain criteria.
-   **`set_value(doctype, docname, fieldname, value)`**: A high-level method to update a single value in a document without triggering all controller hooks.
-   **`commit()` / `rollback()`**: Methods to control database transactions.
-   **`updatedb(doctype)`**: The main method for synchronizing a DocType's schema with the database table.
-   **`exists(doctype, docname)`**: Checks if a document exists in the database.
-   **`count(doctype, filters)`**: Returns the count of documents matching the given filters.

## 4. Detailed Walkthrough

### `database.py`

This file defines the abstract `Database` class, which establishes the contract for all database interactions in the framework. The global `frappe.db` object is an instance of a subclass of `Database`.

-   **`sql(...)`**: This is the core method. It takes a raw SQL query and values, handles debugging and error handling, and executes the query using the underlying database driver (e.g., `pymysql` or `psycopg2`). It also includes important transaction management logic, like raising an error if too many write operations occur in a single transaction.
-   **`get_value(...)` / `get_all(...)` / `set_value(...)`**: These are the most commonly used high-level ORM methods. They provide a convenient and safe way to interact with the database without writing raw SQL. They internally build and execute SQL queries using the `sql()` method.
-   **Transaction Management (`commit`, `rollback`, `savepoint`)**: This class provides methods to explicitly control database transactions. Frappe runs in autocommit mode by default, but these methods allow for grouping multiple operations into a single atomic transaction. It also manages `before_commit` and `after_commit` hooks.
-   **Schema Information (`table_exists`, `field_exists`)**: Provides methods to check for the existence of tables and columns in the database.

### `mariadb/database.py` and `postgres/database.py`

These files contain the concrete implementations of the `Database` class for MariaDB and PostgreSQL, respectively.

-   **Database Connection**: Each class implements the `get_connection()` method, which uses the appropriate Python driver (`pymysql` for MariaDB, `psycopg2` for PostgreSQL) to establish a connection to the database using credentials from `site_config.json`.
-   **Type Mapping (`type_map`)**: Each class defines a `type_map` dictionary that maps Frappe's abstract fieldtypes (e.g., "Data", "Int", "Currency") to the specific column types of the target database (e.g., `varchar(140)`, `int(11)`, `decimal(21,9)`).
-   **SQL Dialect Differences**: They implement methods to handle differences in SQL syntax. For example, `postgres.py` contains a `modify_query` function that replaces backticks (`) with double quotes (") and translates MariaDB-specific functions like `LOCATE` to their PostgreSQL equivalents (`STRPOS`).
-   **Error Handling**: Each class has a nested `ExceptionUtil` class that maps driver-specific exception codes (e.g., `ER.DUP_ENTRY` for MariaDB, `UNIQUE_VIOLATION` for PostgreSQL) to generic Frappe exceptions, allowing the rest of the framework to handle database errors in a consistent way.

### `schema.py`

This file contains the logic for managing the database schema. It's used by the `updatedb` method to synchronize DocType definitions with the database tables.

-   **`DBTable` Class**: This class represents a database table corresponding to a DocType.
    -   When initialized, it reads the fields from the DocType's metadata (`meta.get_fieldnames_with_value()`).
    -   The `sync()` method is the main entry point. It checks if the table is new (`is_new()`) and calls either `create()` or `alter()`.
    -   The `alter()` method (implemented in the database-specific `schema.py` files) compares the existing columns in the database with the columns defined in the DocType and generates `ALTER TABLE` statements to add, remove, or modify columns as needed.
-   **`DbColumn` Class**: Represents a single column in a database table. It has a `get_definition()` method that uses the `type_map` to generate the correct SQL column definition string (e.g., `varchar(140) NOT NULL DEFAULT ''`).