# Model Context Profile: `api`

## 1. Module Overview

The `api` module is responsible for handling REST API requests in the Frappe Framework. It provides a generic and extensible way to expose whitelisted controller methods as API endpoints. This module is fundamental for integrations with third-party services and for providing a headless interface to Frappe applications.

Key functionalities include:
-   Routing API requests to the appropriate whitelisted Python methods.
-   Handling authentication and permission checks for API calls.
-   Parsing request arguments and serializing response data.
-   Providing a standard `frappe.api.handler` for all `POST` and `GET` requests.

## 2. File Index

-   **`__init__.py`**: The main entry point for all `/api` requests. It uses a `werkzeug.routing.Map` to dispatch requests to the correct handler based on the URL and API version.
-   **`v1.py`**: Implements the handlers for the legacy `/api/resource` and `/api/method` endpoints. This is considered the "v1" API.
-   **`v2.py`**: Implements the handlers for the newer, more structured `/api/v2/` endpoints, including `/api/v2/document` and `/api/v2/method`.
-   **`utils.py`**: Currently an empty file, likely reserved for future utility functions.

## 3. Public API / Callable Functions

The entire module is essentially a public API. The primary entry point is `frappe.api.handle`, which is called by the request handler. The user-callable functions are exposed via HTTP endpoints.

**Key Endpoints:**

*   **`/api/method/{method_path}` (v1 & v2)**: Calls any whitelisted Python method. This is the most generic endpoint.
*   **`/api/resource/{doctype}` (v1)**: A RESTful endpoint for listing, creating, reading, updating, and deleting documents.
    *   `GET`: List documents (`frappe.client.get_list`).
    *   `POST`: Create a new document (`frappe.new_doc().insert()`).
    *   `GET /{name}`: Read a document (`frappe.get_doc`).
    *   `PUT /{name}`: Update a document (`doc.save()`).
    *   `DELETE /{name}`: Delete a document (`frappe.delete_doc`).
*   **`/api/v2/document/{doctype}` (v2)**: A more modern and powerful RESTful endpoint for documents.
    *   `GET`: List documents with advanced querying capabilities (pagination, filtering, ordering) via a `QueryBuilder` instance.
    *   `POST`: Create a new document.
    *   `GET /{name}`: Read a document.
    *   `PUT/PATCH /{name}`: Update a document.
    *   `DELETE /{name}`: Delete a document.
*   **`/api/v2/doctype/{doctype}/meta` (v2)**: Get the metadata for a DocType (`frappe.get_meta`).
*   **`/api/v2/doctype/{doctype}/count` (v2)**: Get the count of documents for a DocType.

## 4. Detailed Walkthrough

### `__init__.py`

This file acts as the master router for the API.

-   **`handle(request)`**: This is the main function that receives the `werkzeug.Request` object. It first checks if API request logging is enabled and creates an `API Request Log` if so.
-   **`API_URL_MAP`**: This is a `werkzeug.routing.Map` object that holds all the URL rules for all API versions. It uses `Submount` to prefix the rules from `v1.py` and `v2.py` with their respective version paths (e.g., `/api/v1/`, `/api/v2/`).
-   The router attempts to match the incoming request path against the `API_URL_MAP`. If a match is found, it calls the corresponding endpoint function (e.g., `v1.document_list`, `v2.read_doc`).
-   The return value from the endpoint function is then packaged into a standard JSON response using `frappe.utils.response.build_response`.

### `v1.py`

This file contains the implementation for the older, legacy API endpoints. These endpoints are typically found under `/api/resource` and `/api/method`.

-   **`document_list(doctype)`**: Handles `GET /api/resource/{doctype}`. It essentially wraps `frappe.client.get_list`, passing through query string parameters like `fields`, `filters`, and `limit_page_length`.
-   **`create_doc(doctype)`**, **`read_doc(doctype, name)`**, **`update_doc(doctype, name)`**, **`delete_doc(doctype, name)`**: These functions implement the basic CRUD operations for the `resource` endpoint. They directly call the corresponding `frappe` ORM methods (`frappe.new_doc`, `frappe.get_doc`, `doc.save`, `frappe.delete_doc`).
-   **`handle_rpc_call(method)`**: This is a powerful but less structured endpoint that handles `GET /api/method/{method_path}`. It passes the request directly to `frappe.handler.handle`, which can execute any whitelisted function in the system.

### `v2.py`

This file represents a more modern, structured, and explicit version of the API.

-   **`document_list(doctype)`**: This is a significant improvement over the v1 counterpart. It handles `GET /api/v2/document/{doctype}`. Instead of just wrapping `get_list`, it uses the `frappe.qb` (Query Builder) directly. This provides more robust and secure filtering and field selection.
    -   **Controller Customization**: A key feature is that it allows DocType controllers to implement a static `get_list(query)` method. This method receives the `QueryBuilder` object before it's executed, allowing developers to add custom permission checks or filters directly into the API logic for that specific DocType.
-   **CRUD Functions (`create_doc`, `read_doc`, etc.)**: The v2 CRUD functions are similar to v1 but are more consistent in their return values, typically returning the full document dictionary (`.as_dict()`) after an operation.
-   **`handle_rpc_call(method, doctype=None)`**: The v2 RPC handler is more sophisticated. It can resolve methods from DocType controllers directly (e.g., `/api/v2/method/Project/get_updates`) and also supports API calls defined via `Server Script`.
-   **New Endpoints**: v2 introduces several new, useful endpoints that are not present in v1, such as:
    -   `/doctype/{doctype}/meta`: To fetch DocType metadata.
    -   `/doctype/{doctype}/count`: To get a count of records.
    -   `/document/{doctype}/{name}/copy`: To get a clean, unsaved copy of a document.
    -   `/method/run_doc_method`: To execute a method on an in-memory document object sent in the request body, which is useful for complex client-side interactions that require server-side validation without immediate saving.