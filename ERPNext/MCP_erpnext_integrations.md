# Model Context Profile: ERPNext Integrations

## 1. Module Overview

The **ERPNext Integrations** module serves as a dedicated space for connecting the ERPNext system with various third-party services. The current implementation is focused on providing a robust integration with **Plaid**, a financial technology company that enables applications to connect with users' bank accounts.

The primary purpose of this module is to automate the process of bank reconciliation by fetching bank transactions directly from a user's bank via the Plaid API and creating corresponding `Bank Transaction` documents in ERPNext.

## 2. Core Concepts

### a. Plaid Integration for Bank Synchronization

The core of the module is the integration with Plaid. This allows users to link their bank accounts to ERPNext securely. Once linked, the system can automatically fetch transaction data, which significantly simplifies the bank reconciliation process.

The workflow is as follows:
1.  **Configuration**: An administrator configures the Plaid integration by providing a `client_id` and `secret` in the `Plaid Settings` DocType.
2.  **Linking**: A user initiates the linking process, which uses a `link_token` to open the Plaid Link front-end module. The user selects their bank and provides their credentials to Plaid.
3.  **Token Exchange**: Plaid returns a temporary `public_token`, which is then exchanged for a permanent `access_token`. This `access_token` is stored securely and is used for all future API calls for that user's bank.
4.  **Account Creation**: The system creates a `Bank` document and `Bank Account` documents in ERPNext corresponding to the accounts selected by the user.
5.  **Transaction Sync**: The system periodically fetches new transactions from Plaid and creates `Bank Transaction` documents in ERPNext.

### b. Webhook and Connector Utilities

The `utils.py` file provides generic helper functions that can be used for other integrations in the future.
-   `validate_webhooks_request`: A decorator to secure incoming webhooks by verifying the HMAC signature.
-   `get_webhook_address`: A utility to construct the full webhook URL for a given method.

## 3. Key DocTypes and Classes

### a. `Plaid Settings`

-   **File Path**: [`erpnext/erpnext_integrations/doctype/plaid_settings/plaid_settings.py`](erpnext-develop/erpnext/erpnext_integrations/doctype/plaid_settings/plaid_settings.py)
-   **Purpose**: A Singleton DocType to configure the Plaid integration.
-   **Key Fields**: `plaid_client_id`, `plaid_secret`, `plaid_env` (sandbox, development, production), `automatic_sync`.
-   **Logic**:
    -   Provides the `get_link_token` method, which is called by the front-end to initiate the Plaid Link process.
    -   Includes server-side functions like `add_institution` and `add_bank_accounts` to create the necessary ERPNext documents after a successful link.
    -   The `automatic_synchronization` method is called by the scheduler to enqueue the transaction sync process for all linked accounts.

### b. `PlaidConnector`

-   **File Path**: [`erpnext/erpnext_integrations/doctype/plaid_settings/plaid_connector.py`](erpnext-develop/erpnext/erpnext_integrations/doctype/plaid_settings/plaid_connector.py)
-   **Purpose**: A dedicated class to handle all direct communication with the Plaid API.
-   **Key Responsibilities**:
    -   Initializing the Plaid client with the correct credentials.
    -   Creating link tokens for the front-end.
    -   Exchanging the public token for an access token.
    -   Fetching bank transactions for a given date range and access token.

## 4. Utility Functions

-   **File Path**: [`erpnext/erpnext_integrations/utils.py`](erpnext-develop/erpnext/erpnext_integrations/utils.py)
-   **Key Functions**:
    -   `validate_webhooks_request`: A security utility to ensure that incoming webhook data is authentic and has not been tampered with.
    -   `get_tracking_url`: A helper to generate a tracking URL for a parcel service, indicating that this module may be extended to include logistics integrations in the future.

## 5. Integrations

-   **Banking**: The module's primary integration is with the `Banking` module in ERPNext. It creates `Bank` and `Bank Account` documents and populates the `Bank Transaction` DocType.
-   **Accounts**: By automating the creation of `Bank Transaction` documents, it directly supports the `Bank Reconciliation` process in the `Accounts` module.
-   **Scheduler**: The integration relies on the Frappe scheduler to periodically trigger the `automatic_synchronization` process, ensuring that bank data is kept up-to-date.

## 6. Callable Functions (`@frappe.whitelist()`)

This section details the whitelisted functions that can be called from the client-side (e.g., via `frappe.call`).

### `erpnext.erpnext_integrations.doctype.plaid_settings.plaid_settings`
- `get_link_token`: Fetches a new link token from Plaid to initiate the bank linking process.
- `get_plaid_configuration`: Returns the Plaid client configuration (client ID, environment) to the front-end.
- `add_institution`: Creates a `Bank` document in ERPNext after a successful Plaid link.
- `add_bank_accounts`: Creates `Bank Account` documents in ERPNext for the accounts selected by the user.
- `enqueue_synchronization`: Manually triggers a background job to synchronize bank transactions.
- `get_link_token_for_update`: Fetches a link token for updating an existing bank connection.
- `update_bank_account_ids`: Updates the account IDs in ERPNext after a Plaid update.