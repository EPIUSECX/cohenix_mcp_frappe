# Model Context Profile: `tests`

## 1. Module Overview

The `tests` module contains the actual unit, integration, and functional tests for the Frappe framework. While the `frappe.testing` module provides the infrastructure for running tests, this module is the repository for the test cases themselves.

Analyzing this module provides insight into:
-   How to write effective tests for Frappe applications.
-   The expected behavior of core framework components.
-   Examples of how to use the testing utilities and `FrappeTestCase`.

## 2. File Index

The `tests` module contains a large number of test files, each typically corresponding to a specific module or feature in the framework. The naming convention is `test_{feature_name}.py`.

-   **`test_auth.py`**: Contains tests for user authentication, login methods, and session management.
-   **`test_db.py`**: Contains tests for the database abstraction layer (`frappe.db`), including `get_value`, `set_value`, and transaction management.
-   **`test_query_builder.py`**: Contains tests specifically for the `frappe.qb` query builder, ensuring it generates correct SQL for different backends.
-   **`test_api.py`**: Contains tests for the REST API endpoints.
-   **`test_permissions.py`**: Contains tests for the permission system.
-   **`test_document.py`**: Contains tests for the core `Document` class and its lifecycle hooks.
-   **`ui_test_helpers.py`**: Contains helper functions for running UI tests.
-   ...and many others.

## 3. Public API / Callable Functions

This module does not have a public API. It contains test cases that are meant to be discovered and run by the test runner.

## 4. Detailed Walkthrough

The test files in this module demonstrate the standard patterns for writing automated tests in Frappe.

### Test Case Structure

-   **`IntegrationTestCase`**: Most test classes inherit from `frappe.tests.IntegrationTestCase`. This base class is crucial as it handles the complete setup and teardown of a test environment for each test method.
    -   **`setUp`**: Before each test runs, it creates a new, clean test site and database transaction.
    -   **`tearDown`**: After each test runs, it rolls back the database transaction, ensuring that tests are isolated and do not affect each other.
-   **`UnitTestCase`**: For tests that do not require a database connection, classes can inherit from `frappe.tests.UnitTestCase`, which is faster as it skips the site setup.
-   **Test Methods**: Test methods within these classes must start with the prefix `test_`.

### Common Testing Patterns

-   **Creating Test Data**:
    -   For simple cases, test data is created directly using the ORM: `frappe.get_doc({...}).insert()`.
    -   The `setUpClass` method is often used to create shared test data (like a test user) that can be used by all tests in a class. The `tearDownClass` method is used to clean up this data.
-   **Making Assertions**: Standard `unittest` assertions are used, such as `self.assertEqual()`, `self.assertTrue()`, `self.assertRaises()`.
-   **Testing API Endpoints**:
    -   The `frappe.frappeclient.FrappeClient` is used to simulate a client making API calls to the test site. This is useful for testing authentication and API responses.
    -   For more direct testing of API logic, `frappe.set_request` can be used to mock an incoming web request, and then the API function can be called directly.
-   **Testing Permissions**: Tests often involve creating multiple users with different roles and then using `frappe.set_user()` to switch the active user before performing an action. This allows for asserting that the permission system correctly allows or denies the action.
-   **Database-Specific Tests**: The decorator `@run_only_if(db_type_is.MARIADB)` or `@run_only_if(db_type_is.POSTGRES)` is used to mark tests that should only run on a specific database backend. This is essential for testing features that have different implementations for MariaDB and PostgreSQL, such as the query builder.
-   **Mocking and Patching**: Python's `unittest.mock.patch` is used to mock functions or objects, allowing for testing components in isolation. `self.patch_hooks` is a Frappe-specific helper for temporarily modifying hooks for a test.