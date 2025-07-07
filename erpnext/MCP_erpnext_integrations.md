# Model Context Profile: ERPNext Integrations

## 1. Module Overview

The ERPNext Integrations module provides connections to external services and platforms, enabling seamless data exchange and extending the core functionality of the ERP system. This includes integrations with payment gateways, shipping providers, and other third-party applications.

## 2. Key Reusable Functions

This section details important client-side and server-side functions that can be leveraged for custom application development. The Plaid integration is a prime example of how ERPNext can connect to external services.

### 2.1. Server-Side (Python)

#### `erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings`

-   **`get_link_token()`**: A `@frappe.whitelist()` method that acts as a secure bridge to the Plaid API. It retrieves a short-lived `link_token` from Plaid, which is then passed to the client-side to initialize the Plaid Link UI.

-   **`add_institution(token, response)`**: After a successful link on the client-side, this `@frappe.whitelist()` function receives the public token, exchanges it for a permanent `access_token` with Plaid, and creates a corresponding `Bank` document in ERPNext to store this token.

-   **`add_bank_accounts(response, bank, company)`**: This function takes the account data returned by Plaid and creates the necessary `Bank Account` and `Account` documents in ERPNext, linking them to the newly created `Bank`.

-   **`sync_transactions(bank, bank_account)`**: This is the core data synchronization function. It fetches transactions from Plaid for a given bank account, starting from the `last_integration_date`, and creates a `Bank Transaction` record for each new transaction. This function is designed to be run as a background job.

-   **`enqueue_synchronization()`**: A `@frappe.whitelist()` function that iterates through all Plaid-linked bank accounts and queues a background job (`frappe.enqueue`) for each one to run `sync_transactions`. This ensures that the synchronization process is asynchronous and does not block the UI.

#### `erpnext.erpnext_integrations.utils`

-   **`validate_webhooks_request(doctype, hmac_key, secret_key="secret")`**: A generic decorator for securing webhook endpoints. It validates the incoming request's signature to ensure that it originated from the trusted third-party service.

-   **`get_webhook_address(connector_name, method, ...)`**: A utility function to generate the full webhook URL for a given connector, which can then be provided to the external service.

### 2.2. Client-Side (JavaScript)

#### `erpnext.integrations.plaidLink` in `plaid_settings.js`

-   **`constructor(parent)`**: The entry point for the Plaid integration UI. When a user clicks the "Link a new bank account" button, this class is instantiated.

-   **`init_config()`**: This asynchronous function orchestrates the client-side workflow. It calls the `get_link_token` method on the server to retrieve the link token.

-   **`init_plaid()`**: This function dynamically loads the official Plaid Link JavaScript library from their CDN. Once loaded, it initializes the Plaid Link UI using the retrieved token.

-   **`plaid_success(token, response)`**: This is the callback function that is executed when the user successfully authenticates with their bank through the Plaid UI. It sends the public token and account information back to the Frappe server (`add_institution` and `add_bank_accounts`) to complete the linking process.