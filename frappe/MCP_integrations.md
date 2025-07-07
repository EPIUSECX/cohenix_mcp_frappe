# MCP: Integrations Module

## Module Overview

The **Integrations** module provides the framework and tools for connecting Frappe with other applications and services. It includes features for OAuth 2.0, webhooks, and integrations with popular services like Google, Slack, and LDAP.

This module is essential for extending the functionality of Frappe by allowing it to communicate and exchange data with external systems.

## File Index

*   `frappe/integrations/__init__.py`
*   `frappe/integrations/google_oauth.py`
*   `frappe/integrations/oauth2.py`
*   `frappe/integrations/doctype/webhook/webhook.py`
*   `frappe/integrations/doctype/oauth_client/oauth_client.py`
*   `frappe/integrations/doctype/google_settings/google_settings.py`
*   `frappe/integrations/doctype/ldap_settings/ldap_settings.py`
*   `frappe/integrations/doctype/slack_webhook_url/slack_webhook_url.py`
*   ... and so on for all files in the `integrations` module.

## Public API / Callable Functions

### `frappe.integrations.doctype.webhook.enqueue_webhook(doc, webhook)`
- **Description:** Enqueues a webhook to be sent. This is the main function for triggering webhooks.
- **Arguments:**
    - `doc` (Document): The document that triggered the webhook.
    - `webhook` (dict): A dictionary containing the webhook's name.
- **Returns:** None.

### `frappe.integrations.doctype.slack_webhook_url.send_slack_message(webhook_url, message, reference_doctype, reference_name)`
- **Description:** Sends a message to a Slack channel using a configured webhook URL.
- **Arguments:**
    - `webhook_url` (string): The name of the `Slack Webhook URL` document.
    - `message` (string): The message to be sent.
    - `reference_doctype` (string): The DocType of the document to which the message is related.
    - `reference_name` (string): The name of the document to which the message is related.
- **Returns:** "success" or "error".

## Detailed Walkthrough

### `frappe/integrations/doctype/webhook/webhook.py`

This file defines the `Webhook` DocType, which is used to send data to a URL when a specific event occurs in Frappe.

#### Class: `Webhook(Document)`

This class represents a webhook. It allows you to configure a URL, a DocType, and an event that will trigger the webhook. When the event occurs, Frappe will send a POST request to the specified URL with the document's data.

**Key Methods:**

*   **`validate()`**: Validates the webhook settings, including the request URL and the condition.
*   **`preview_request_body(preview_document)`**: Returns a preview of the request body that will be sent with the webhook.

**Key Functions (outside the class):**

*   **`enqueue_webhook(doc, webhook)`**: This function is called when a webhook is triggered. It builds the request headers and data and sends the request to the webhook URL.

**Key Properties (Fields):**

*   **`webhook_doctype`**: The DocType that triggers the webhook.
*   **`webhook_docevent`**: The event that triggers the webhook (e.g., "on_submit", "on_trash").
*   **`request_url`**: The URL to which the webhook request will be sent.
*   **`request_structure`**: The format of the request body ("Form URL-Encoded" or "JSON").
*   **`webhook_data`**: A child table for defining the data to be sent in a "Form URL-Encoded" request.
*   **`webhook_json`**: A Jinja template for the request body of a "JSON" request.
*   **`enable_security`**, **`webhook_secret`**: Options for securing the webhook with a signature.

### `frappe/integrations/doctype/oauth_client/oauth_client.py`

This file defines the `OAuthClient` DocType, which is used to configure OAuth 2.0 clients for Frappe.

#### Class: `OAuthClient(Document)`

This class represents an OAuth 2.0 client. It stores the client ID, client secret, and other information needed to authenticate with an OAuth 2.0 provider.

**Key Methods:**

*   **`validate()`**: Generates a client secret if one is not provided and validates the grant and response types.

**Key Properties (Fields):**

*   **`app_name`**: The name of the application.
*   **`client_id`**: The client ID.
*   **`client_secret`**: The client secret.
*   **`redirect_uris`**: A list of allowed redirect URIs.
*   **`default_redirect_uri`**: The default redirect URI.
*   **`scopes`**: The scopes that the client is allowed to request.

### `frappe/integrations/doctype/google_settings/google_settings.py`

This file defines the `GoogleSettings` DocType, a Singleton for configuring Google APIs.

#### Class: `GoogleSettings(Document)`

This class holds the API keys and other settings needed to integrate with Google services like Google Drive and Google Calendar.

**Key Functions (outside the class):**

*   **`get_file_picker_settings()`**: Returns the settings needed to use the Google Drive file picker.

**Key Properties (Fields):**

*   **`enable`**: A checkbox to enable or disable Google integration.
*   **`client_id`**, **`client_secret`**: The client ID and secret for the Google API project.
*   **`api_key`**: The API key for the Google API project.

### `frappe/integrations/doctype/ldap_settings/ldap_settings.py`

This file defines the `LDAPSettings` DocType, a Singleton for configuring LDAP integration.

#### Class: `LDAPSettings(Document)`

This class holds the settings for connecting to an LDAP server for user authentication and synchronization.

**Key Methods:**

*   **`authenticate(username, password)`**: Authenticates a user against the LDAP server.
*   **`create_or_update_user(user_data, groups)`**: Creates or updates a user in Frappe based on the data from the LDAP server.
*   **`sync_roles(user, additional_groups)`**: Synchronizes the user's roles in Frappe with their groups in LDAP.

**Key Properties (Fields):**

*   **`enabled`**: A checkbox to enable or disable LDAP integration.
*   **`ldap_server_url`**: The URL of the LDAP server.
*   **`base_dn`**: The base DN for searching for users and groups.
*   **`password`**: The password for the bind user.
*   **`ldap_search_string`**: The search filter for finding users.
*   **`ldap_groups`**: A child table for mapping LDAP groups to Frappe roles.

### `frappe/integrations/doctype/slack_webhook_url/slack_webhook_url.py`

This file defines the `SlackWebhookURL` DocType, which is used to configure webhook URLs for sending messages to Slack.

#### Class: `SlackWebhookURL(Document)`

This class represents a Slack webhook URL. It stores the URL and a name for the webhook.

**Key Functions (outside the class):**

*   **`send_slack_message(webhook_url, message, reference_doctype, reference_name)`**: Sends a message to the specified Slack webhook URL.

**Key Properties (Fields):**

*   **`webhook_name`**: A name for the webhook.
*   **`webhook_url`**: The Slack webhook URL.
*   **`show_document_link`**: If checked, a link to the reference document will be included in the Slack message.