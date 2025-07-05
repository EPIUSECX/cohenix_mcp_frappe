# MCP: Core Module

## Module Overview

The **Core** module is the heart of the Frappe Framework, providing the fundamental building blocks for creating and managing applications. It is responsible for the meta-modelling system (DocTypes), user and permission management, and a wide range of essential system functionalities.

The module defines how data structures are created and behave, how users interact with the system, and how security is enforced. It is the foundation upon which all other Frappe modules and custom applications are built.

## File Index

*   `frappe/core/__init__.py`
*   `frappe/core/api/__init__.py`
*   `frappe/core/doctype/__init__.py`
*   `frappe/core/doctype/access_log/__init__.py`
*   `frappe/core/doctype/access_log/access_log.js`
*   `frappe/core/doctype/access_log/access_log.json`
*   `frappe/core/doctype/access_log/access_log.py`
*   `frappe/core/doctype/activity_log/__init__.py`
*   `frappe/core/doctype/activity_log/activity_log.js`
*   `frappe/core/doctype/activity_log/activity_log.json`
*   `frappe/core/doctype/activity_log/activity_log.py`
*   `frappe/core/doctype/activity_log/test_activity_log.py`
*   `frappe/core/doctype/amended_document_naming_settings/__init__.py`
*   `frappe/core/doctype/amended_document_naming_settings/amended_document_naming_settings.js`
*   `frappe/core/doctype/amended_document_naming_settings/amended_document_naming_settings.json`
*   `frappe/core/doctype/amended_document_naming_settings/amended_document_naming_settings.py`
*   `frappe/core/doctype/api_request_log/api_request_log.js`
*   `frappe/core/doctype/api_request_log/api_request_log.py`
*   `frappe/core/doctype/api_request_log/test_api_request_log.py`
*   ... and so on for all files in the `core` module.

## Detailed Walkthrough

### `frappe/core/doctype/doctype/doctype.py`

This file defines the `DocType` class, which is the model for creating other DocTypes. It is a meta-model, meaning it defines the structure of models themselves.

#### Class: `DocType(Document)`

This class inherits from `frappe.model.document.Document` and represents a DocType document. It contains all the logic for validating, saving, and managing DocTypes.

**Key Methods:**

*   **`validate()`**: This is the main validation method, called before a DocType is saved. It orchestrates a series of other validation methods to ensure the DocType's integrity. Key validations include:
    *   `check_developer_mode()`: Ensures that standard DocTypes are only created in developer mode.
    *   `validate_name()`: Validates the DocType's name against various rules (length, characters, etc.).
    *   `validate_fields()`: A comprehensive validation of all fields (DocFields) within the DocType.
    *   `validate_permissions()`: Validates the permission rules defined for the DocType.
    *   `make_amendable()`: Adds `amended_from` field if the DocType is submittable.
    *   `validate_nestedset()`: Adds fields required for tree structures (`lft`, `rgt`).

*   **`on_update()`**: This method is called after a DocType is saved. It is responsible for:
    *   Updating the database schema using `frappe.db.updatedb()`.
    *   Exporting the DocType to a `.json` file if it's a standard DocType.
    *   Creating boilerplate controller code (`.py` and `.js` files).
    *   Clearing relevant caches.

*   **`after_rename(old, new, merge=False)`**: Handles the renaming of a DocType. It renames the database table (`tabOldName` to `tabNewName`) and moves/renames the associated files.

*   **`export_doc()`**: Exports the DocType definition to a JSON file within its module's directory.

*   **`make_controller_template()`**: Creates boilerplate Python and JavaScript controller files for the DocType.

**Key Properties (Fields):**

*   **`name`**: The unique name of the DocType.
*   **`module`**: The module the DocType belongs to.
*   **`fields`**: A table (child DocType `DocField`) containing the list of fields for this DocType.
*   **`permissions`**: A table (child DocType `DocPerm`) defining the permission rules.
*   **`issingle`**: A checkbox indicating if the DocType is a Single DocType (only one record exists).
*   **`istable`**: A checkbox indicating if the DocType is a child table (used within other DocTypes).
*   **`is_submittable`**: A checkbox indicating if documents of this type can be submitted.

### `frappe/core/doctype/user/user.py`

This file defines the `User` class, which manages user accounts in the system.

#### Class: `User(Document)`

This class represents a user document. It handles everything from user creation and authentication to roles, permissions, and user settings.

**Key Methods:**

*   **`validate()`**: Validates the user document before saving. Key validations include:
    *   Populating roles from `Role Profile`.
    *   `set_system_user()`: Determines if the user is a "System User" or "Website User" based on their roles.
    *   `check_enable_disable()`: Handles logic for enabling/disabling users.
    *   `validate_username()`: Ensures the username is valid and unique.

*   **`on_update()`**: Called after a user document is saved. It handles:
    *   Sending password notifications.
    *   Creating a `Contact` for the user.
    *   Updating the user's Gravatar.
    *   Clearing user-related caches.

*   **`reset_password(send_email=False, password_expired=False)`**: Generates a password reset key and optionally sends a password reset email.

*   **`add_roles(*roles)` / `remove_roles(*roles)`**: Methods to programmatically add or remove roles from a user.

**Key Properties (Fields):**

*   **`email`**: The user's email address, which also serves as their unique name (for non-admin/guest users).
*   **`first_name`**, **`last_name`**: The user's name.
*   **`enabled`**: A checkbox to enable or disable the user account.
*   **`roles`**: A table of roles assigned to the user.
*   **`user_type`**: Can be "System User" or "Website User". System users have desk access.
*   **`new_password`**: A field to set a new password.

### `frappe/core/doctype/role/role.py`

This file defines the `Role` class, which is used to manage roles and their permissions.

#### Class: `Role(Document)`

This class represents a role document. Roles are used to group users and assign permissions to them.

**Key Methods:**

*   **`validate()`**: Validates the role document. It handles disabling a role and its consequences.
*   **`on_update()`**: If the `desk_access` for a role is changed, it triggers an update for all users with that role to re-evaluate their `user_type`.
*   **`disable_role()`**: Disables a role and removes it from all users who have it.

**Key Properties (Fields):**

*   **`role_name`**: The name of the role.
*   **`desk_access`**: A checkbox that determines if users with this role have access to the Frappe Desk.
*   **`disabled`**: A checkbox to disable the role.
### `frappe/core/doctype/docfield/docfield.py`

This file defines the `DocField` class, which is a child DocType of `DocType`. Each `DocField` document represents a field in a DocType.

#### Class: `DocField(Document)`

This class represents a field definition within a DocType. It holds all the properties of a field, such as its label, fieldtype, options, and various other configuration settings.

**Key Properties (Fields):**

*   **`fieldname`**: The name of the field in the database table.
*   **`label`**: The display label for the field in the UI.
*   **`fieldtype`**: The type of the field (e.g., `Data`, `Link`, `Table`, `Check`). This determines how the field is rendered and what kind of data it stores.
*   **`options`**: The options for the field. The meaning of this property depends on the `fieldtype`. For `Link` fields, it's the linked DocType. For `Select` fields, it's a list of options.
*   **`reqd`**: A checkbox indicating if the field is mandatory.
*   **`hidden`**: A checkbox to hide the field in the UI.
*   **`permlevel`**: The permission level of the field. Fields with a `permlevel` greater than 0 are only visible/editable to users with a matching permission level.
*   **`unique`**: A checkbox to enforce unique values for this field.
*   **`in_list_view`**: A checkbox to show the field in list views.

### `frappe/core/doctype/docperm/docperm.py`

This file defines the `DocPerm` class, which is a child DocType of `DocType`. Each `DocPerm` document represents a permission rule for a DocType.

#### Class: `DocPerm(Document)`

This class represents a permission rule. It defines which roles have what level of access (read, write, create, delete, etc.) to a DocType.

**Key Properties (Fields):**

*   **`role`**: The role to which this permission rule applies.
*   **`permlevel`**: The permission level for this rule. This corresponds to the `permlevel` of `DocField`s.
*   **`read`**, **`write`**, **`create`**, **`delete`**, **`submit`**, **`cancel`**, **`amend`**: Checkboxes that grant the respective permissions to the specified role.
*   **`if_owner`**: A checkbox to apply this permission rule only if the user is the owner of the document.

### `frappe/core/doctype/page/page.py`

This file defines the `Page` class, which is used to create custom pages within the Frappe Desk.

#### Class: `Page(Document)`

This class represents a Desk Page. Pages are single-view workspaces that can contain custom HTML, CSS, and JavaScript to create rich user interfaces.

**Key Methods:**

*   **`on_update()`**: Exports the page definition to a `.json` file and creates a boilerplate `.js` file if one doesn't exist.
*   **`is_permitted()`**: Checks if the current user has permission to view the page based on the roles assigned to the page.
*   **`load_assets()`**: Loads the associated `.js`, `.css`, and `.html` files for the page.

**Key Properties (Fields):**

*   **`page_name`**: The name of the page.
*   **`module`**: The module the page belongs to.
*   **`roles`**: A table of roles that are allowed to access this page.
*   **`script`**, **`style`**, **`content`**: Fields to hold the JavaScript, CSS, and HTML content of the page, respectively. These are typically loaded from the corresponding files.

### `frappe/core/doctype/report/report.py`

This file defines the `Report` class, which is used to create reports in Frappe.

#### Class: `Report(Document)`

This class represents a report. Frappe supports several types of reports, including "Report Builder" reports (created through a UI), "Query Reports" (based on a SQL query), and "Script Reports" (based on a Python script).

**Key Methods:**

*   **`validate()`**: Validates the report, ensuring that standard reports are not modified by non-administrators and that script reports are only editable by users with the "Script Manager" role.
*   **`execute_query_report(filters)`**: Executes the SQL query for a "Query Report" and returns the columns and results.
*   **`execute_script_report(filters)`**: Executes the Python script for a "Script Report" and returns the columns and results.
*   **`get_data(...)`**: A general method to get the data for the report, which calls the appropriate execution method based on the `report_type`.

**Key Properties (Fields):**

*   **`report_name`**: The name of the report.
*   **`ref_doctype`**: The reference DocType for the report.
*   **`report_type`**: The type of the report ("Report Builder", "Query Report", "Script Report").
*   **`query`**: The SQL query for a "Query Report".
*   **`report_script`**: The Python script for a "Script Report".
*   **`json`**: A JSON field that stores the configuration for "Report Builder" reports.
*   **`roles`**: A table of roles that are allowed to access this report.
### `frappe/core/doctype/system_settings/system_settings.py`

This file defines the `SystemSettings` class, a Singleton DocType that holds a wide variety of global configuration options for the Frappe instance.

#### Class: `SystemSettings(Document)`

This class represents the central configuration document for the system. Since it's a Singleton, there is only one `SystemSettings` document in the database.

**Key Methods:**

*   **`validate()`**: Validates the system settings before saving. This includes checks for:
    *   Password policy configuration.
    *   Session expiry format.
    *   Two-factor authentication setup.
    *   Availability of alternative login methods if standard password login is disabled.
*   **`on_update()`**: Called after the document is saved. It sets the default values for the system based on the settings and clears the system settings cache.
*   **`set_defaults()`**: Iterates through the fields and sets them as system-wide defaults using `frappe.db.set_default()`.

**Key Properties (Fields):**

*   **`language`**: The default system language.
*   **`time_zone`**: The default system time zone.
*   **`date_format`**, **`time_format`**, **`number_format`**: Default formatting for dates, times, and numbers.
*   **`enable_scheduler`**: A checkbox to enable or disable the background job scheduler.
*   **`enable_two_factor_auth`**: A checkbox to enable two-factor authentication for all users.
*   **`session_expiry`**: The duration after which a user's session expires.
*   **`backup_limit`**: The number of database backups to retain.
*   **`max_file_size`**: The maximum allowed size for file uploads (in MB).

### `frappe/core/doctype/sms_settings/sms_settings.py`

This file defines the `SMSSettings` class, a Singleton DocType for configuring the SMS gateway.

#### Class: `SMSSettings(Document)`

This class holds the configuration for sending SMS messages through a third-party gateway.

**Key Functions (outside the class):**

*   **`send_sms(receiver_list, msg, sender_name="", success_msg=True)`**: The main function for sending an SMS. It validates the receiver numbers and calls `send_via_gateway`.
*   **`send_via_gateway(arg)`**: Constructs the request to the SMS gateway based on the settings and sends it. It also creates an `SMS Log` for each successful message.
*   **`create_sms_log(args, sent_to)`**: Creates an `SMS Log` document to record the details of the sent SMS.

**Key Properties (Fields):**

*   **`sms_gateway_url`**: The URL of the SMS gateway provider.
*   **`message_parameter`**: The name of the parameter in the gateway's API that holds the message content.
*   **`receiver_parameter`**: The name of the parameter for the receiver's mobile number.
*   **`parameters`**: A child table to define additional static parameters required by the gateway's API (e.g., API keys, sender ID).

### `frappe/core/doctype/scheduled_job_log/scheduled_job_log.py`

This file defines the `ScheduledJobLog` class, which is used to log the execution of scheduled background jobs.

#### Class: `ScheduledJobLog(Document)`

This class represents a log entry for a scheduled job. Each time a scheduled job runs (e.g., daily, weekly), a new `ScheduledJobLog` document is created to record its status and any output.

**Key Methods:**

*   **`clear_old_logs(days=90)`**: A static method to delete logs older than a specified number of days. This is typically called by a scheduled job itself to prevent the log from growing indefinitely.

**Key Properties (Fields):**

*   **`scheduled_job_type`**: A link to the `Scheduled Job Type` that was executed.
*   **`status`**: The status of the job execution ("Scheduled", "Complete", "Failed").
*   **`details`**: Any output or traceback from the job execution.
### `frappe/core/notifications.py`

This file centralizes the configuration for the notification bell in the Desk UI. It defines which documents should appear as notifications and how to count them.

**Key Functions:**

*   **`get_notification_config()`**: This is the central function that returns a dictionary defining the notification behavior for different DocTypes.
    *   For simple cases, it can be a dictionary of filters (e.g., for `Error Log`, show a count of documents where `seen=0`).
    *   For more complex cases, it can be a string pointing to a whitelisted Python function that will be called to get the count (e.g., for `ToDo`, it calls `get_things_todo`).
*   **`get_things_todo()`**: A function that returns the count of open `ToDo` items assigned to or by the current user. This is used to populate the "To Do" notification.
*   **`get_todays_events()`**: A function that returns the count of events scheduled for the current day for the current user.

### `frappe/core/utils.py`

This file contains miscellaneous utility functions that are used across the `core` module and other parts of the framework.

**Key Functions:**

*   **`get_parent_doc(doc)`**: A helper function to get the parent document of a given document, typically used in the context of child tables or linked documents.
*   **`set_timeline_doc(doc)`**: A function used to automatically link a document (like a `Communication`) to a master document's timeline (e.g., a `Lead` or `Opportunity`). It inspects the parent document's `timeline_field` meta property to determine the correct timeline to link to.
*   **`find(list_of_dict, match_function)`**: A simple but useful utility to find the first dictionary in a list of dictionaries that matches a given condition.
*   **`html2text(html)`**: A wrapper around the `markdownify` library to convert HTML content into plain text or Markdown.
### `frappe/core/doctype/version/version.py`

This file contains the logic for the `Version` DocType, which is the cornerstone of Frappe's data auditing and version control system. A new `Version` document is created every time a tracked document is saved.

#### Class: `Version(Document)`

This class represents a single version of another document. It doesn't store the full document but rather a JSON diff of the changes.

**Key Methods:**

*   **`update_version_info(old, new)`**: This is the main entry point called from the `on_update` hook of a document. It determines if the document is new or being updated and calls the appropriate method (`for_insert` or `set_diff`).
*   **`set_diff(old, new)`**: This method calculates the difference between the old and new state of a document. It calls the global `get_diff` function and stores the resulting JSON data in the `data` field of the `Version` document.
*   **`for_insert(doc)`**: If a document is being created (e.g., via Data Import) and has a `updater_reference` flag, this method creates a "creation" version to log how the document was created.
*   **`get_data()`**: A simple helper to parse the JSON stored in the `data` field and return it as a Python dictionary.

**Key Functions (outside the class):**

*   **`get_diff(old, new)`**: This is the core diffing engine. It iterates through all the fields of the `new` document and compares them to the `old` one. It is smart enough to handle changes in child tables (added, removed, and changed rows) and tracks changes to standard fields. The output is a dictionary containing keys like `changed`, `added`, `removed`, and `row_changed`.

### `frappe/core/doctype/comment/comment.py`

This file defines the `Comment` DocType, which is a generic model used for various types of interactions on a document's timeline, including user comments, likes, assignments, and system-generated messages (like "Created", "Submitted").

#### Class: `Comment(Document)`

This class represents a single comment or timeline entry.

**Key Methods:**

*   **`after_insert()`**: After a comment is created, this method calls `notify_mentions` to send notifications to any users mentioned in the comment content (e.g., `@user`). It also publishes a realtime event to update the UI for all users viewing the document.
*   **`on_update()` / `on_trash()`**: These methods ensure that the `_comments` cache on the parent document is updated when a comment is edited or deleted.
*   **`notify_change(action)`**: This method is responsible for publishing a `docinfo_update` event via `frappe.publish_realtime`. This event tells the client-side UI to refresh the timeline (comments, attachments, etc.) for the referenced document.

**Key Functions (outside the class):**

*   **`update_comment_in_doc(doc)`**: This is a crucial caching mechanism. To avoid querying the `Comment` table every time a document is loaded, Frappe stores a truncated list of the latest comments directly on the referenced document in a hidden field called `_comments`. This function is responsible for updating this JSON field whenever a comment is added or edited.

### `frappe/core/doctype/file/file.py`

This file contains the logic for the `File` DocType, which is central to how Frappe manages all file uploads, attachments, and folders.

#### Class: `File(Document)`

This class represents a file or a folder in the system.

**Key Methods:**

*   **`before_insert()`**: This method orchestrates the entire file saving process. It sets the folder, validates the file extension and size, and then calls `save_file` to write the content to disk.
*   **`save_file(...)`**: This is the core method for handling file content.
    *   It calculates the `content_hash` of the file.
    *   It checks if another file with the same hash already exists to avoid storing duplicate data on disk. If a duplicate is found, it simply points the new `File` document's `file_url` to the existing file on disk.
    *   If the file is new, it calls a `write_file` hook (if one exists, for cloud storage) or `save_file_on_filesystem` to save the file locally.
*   **`on_trash()`**: When a `File` document is deleted, this method calls `_delete_file_on_disk`. This method checks if any other `File` document is referencing the same file on disk (via `content_hash`). If not, the physical file is deleted from the server.
*   **`unzip()`**: A utility to extract the contents of a zip file, creating new `File` documents for each file within the archive and then deleting the original zip file record.
*   **`make_thumbnail(...)`**: Generates a smaller version of an image file, used for previews in the UI.
*   **`handle_is_private_changed()`**: If the `is_private` flag is toggled, this method physically moves the file between the public and private files directories on the server and updates the `file_url`.

**Key Functions (outside the class):**

*   **`has_permission(doc, ptype, user)`**: Implements the permission logic for files. A user can access a file if:
    1.  The file is public (`is_private=0`).
    2.  The user is the owner of the `File` document.
    3.  The user has permission to access the document the file is attached to.
### `frappe/core/doctype/user_permission/user_permission.py`

This file contains the logic for the `User Permission` DocType, a powerful feature that allows for instance-level permissions, restricting user access to specific documents within a DocType (e.g., allowing a user to see only a specific `Customer` or `Company`).

#### Class: `UserPermission(Document)`

This class represents a single user permission record.

**Key Methods:**

*   **`validate()`**: Ensures that a duplicate permission rule is not created for the same user, DocType, and document.
*   **`on_update()` / `on_trash()`**: These hooks are critical for performance. They clear the user's permission cache (`frappe.cache.hdel("user_permissions", self.user)`) whenever a rule is added, changed, or removed. They also publish a realtime event (`update_user_permissions`) to notify the client to refetch its permissions.

**Key Functions (outside the class):**

*   **`get_user_permissions(user=None)`**: This is the central function for fetching and processing user permissions. It retrieves all `User Permission` documents for a given user and compiles them into a dictionary, keyed by the "allow" DocType (e.g., `{"Customer": [{"doc": "Customer A"}, {"doc": "Customer B"}]}`).
    *   **Caching**: The results of this function are heavily cached in Redis to avoid querying the database on every request.
    *   **Tree Structures**: It has special handling for nested set (tree) DocTypes. If a user is given permission for a parent node (e.g., a Territory), they automatically get permission for all descendant nodes unless `hide_descendants` is checked.
*   **`check_applicable_doc_perm(user, doctype, docname)`**: A utility to check which other DocTypes a specific user permission applies to.
*   **`clear_user_permissions(user, for_doctype)`**: A utility for administrators to remove all user permissions for a specific user and DocType.

### `frappe/core/doctype/translation/translation.py`

This file contains the logic for the `Translation` DocType, which stores user-generated translations for various strings in the system.

#### Class: `Translation(Document)`

This class represents a single translation record.

**Key Methods:**

*   **`validate()`**: Strips any HTML tags from the `source_text` to ensure that only the raw text is stored for translation.
*   **`on_update()` / `on_trash()`**: These hooks call `clear_user_translation_cache` to invalidate the translation cache for the specific language, ensuring that the changes are reflected immediately across the system.

**Key Functions (outside the class):**

*   **`clear_user_translation_cache(lang)`**: This function clears two specific cache keys: `USER_TRANSLATION_KEY` and `MERGED_TRANSLATION_KEY`. Frappe maintains a merged dictionary of all translations (from `.csv` files and the `Translation` DocType) for each language to speed up the translation process. This function ensures that the cache is rebuilt when a user-contributed translation is changed.