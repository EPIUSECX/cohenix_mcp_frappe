# MCP: Email Module

## Module Overview

The **Email** module in Frappe is a comprehensive system for managing all email-related activities. It provides the functionality to configure email accounts, send and receive emails, create and use email templates, and manage email queues and logs. This module is essential for communication within the Frappe framework, enabling notifications, auto-replies, and integration with external email services.

The module is designed to be robust, with support for both POP3 and IMAP protocols for incoming mail, and SMTP for outgoing mail. It also includes features for handling email threads, attachments, and automatic linking of emails to relevant documents in the system.

## File Index

*   `frappe/email/__init__.py`
*   `frappe/email/email_body.py`
*   `frappe/email/queue.py`
*   `frappe/email/receive.py`
*   `frappe/email/smtp.py`
*   `frappe/email/doctype/email_account/email_account.py`
*   `frappe/email/doctype/email_template/email_template.py`
*   ... and so on for all files in the `email` module.

## Public API / Callable Functions

### `frappe.email.queue.flush()`
- **Description:** Flushes the email queue, sending out all pending emails. This is typically called by the scheduler.
- **Arguments:** None.
- **Returns:** None.

### `frappe.email.doctype.email_template.get_email_template(template_name, doc)`
- **Description:** Returns the processed HTML of an email template with the given document as context.
- **Arguments:**
    - `template_name` (string): The name of the `Email Template`.
    - `doc` (dict or Document): The document to use as context for rendering the template.
- **Returns:** A dictionary containing the formatted `subject` and `message`.

### `frappe.sendmail(...)`
- **Description:** This is the primary function for sending emails from Frappe. It is a wrapper around the `EmailQueue` DocType and handles the creation of an `Email Queue` document, which is then processed by the scheduler.
- **Arguments:** A wide range of arguments including `recipients`, `sender`, `subject`, `content`, `doctype`, `name`, etc.
- **Returns:** The `Email Queue` document.

## Detailed Walkthrough

### `frappe/email/doctype/email_account/email_account.py`

This file defines the `EmailAccount` DocType, which is the central point for configuring email accounts in Frappe.

#### Class: `EmailAccount(Document)`

This class represents an email account. It stores all the necessary information to connect to an email server for both sending and receiving emails, including server settings, credentials, and various options.

**Key Methods:**

*   **`validate()`**: Validates the email account settings, including checking the connection to the email server if credentials are provided.
*   **`on_update()`**: Ensures that there is only one default incoming and one default outgoing email account.
*   **`get_incoming_server()`**: Returns a logged-in POP3 or IMAP connection object.
*   **`get_smtp_server()`**: Returns an SMTP server object for sending emails.
*   **`receive()`**: Fetches new emails from the email account and processes them.
*   **`append_email_to_sent_folder(message)`**: Appends a sent email to the "Sent" folder of the email account if IMAP is enabled.

**Key Properties (Fields):**

*   **`email_id`**: The email address of the account.
*   **`enable_incoming`**, **`enable_outgoing`**: Checkboxes to enable receiving and sending emails for this account.
*   **`default_incoming`**, **`default_outgoing`**: Checkboxes to set this account as the default for incoming or outgoing emails.
*   **`email_server`**, **`use_imap`**, **`use_ssl`**: Settings for the incoming mail server.
*   **`smtp_server`**, **`use_tls`**: Settings for the outgoing mail server.
*   **`password`**: The password for the email account.

### `frappe/email/doctype/email_template/email_template.py`

This file defines the `EmailTemplate` DocType, which allows users to create reusable templates for emails.

#### Class: `EmailTemplate(Document)`

This class represents an email template. Templates can contain Jinja templating tags to insert dynamic data from documents.

**Key Methods:**

*   **`get_formatted_subject(doc)`**: Renders the template's subject with the given document as context.
*   **`get_formatted_response(doc)`**: Renders the template's body with the given document as context.
*   **`get_formatted_email(doc)`**: Returns a dictionary with the formatted subject and message.

**Key Properties (Fields):**

*   **`subject`**: The subject of the email template.
*   **`response`**: The body of the email template.
*   **`use_html`**: If checked, the response is treated as HTML.

### `frappe/email/queue.py`

This file contains the logic for managing the email queue. Emails are not sent immediately but are added to a queue and sent in the background by the scheduler.

**Key Functions:**

*   **`flush()`**: The main function that is called by the scheduler to send pending emails. It fetches a batch of emails from the `Email Queue` and sends them one by one.
*   **`get_queue()`**: Fetches a batch of pending emails from the `Email Queue` to be sent.
*   **`get_emails_sent_today()`**: Returns the number of emails sent in the last 24 hours.

### `frappe/email/receive.py`

This file handles the receiving and processing of incoming emails.

#### Class: `EmailServer`
A wrapper for POP3 and IMAP connections to fetch emails from the server.

#### Class: `Email`
A wrapper for a raw email message, providing methods to parse headers, content, and attachments.

#### Class: `InboundMail(Email)`
A subclass of `Email` that contains the logic for processing an incoming email. It creates a `Communication` document from the email and links it to other documents in the system if possible.

**Key Methods (`InboundMail`):**
*   **`process()`**: The main method that processes an incoming email. It checks if the email already exists in the system, and if not, it creates a new `Communication` document.
*   **`parent_communication()`**: Finds a related `Communication` document to thread the new email correctly.
*   **`reference_document()`**: Finds a reference document (e.g., an Issue, Lead, or Opportunity) to link the email to, based on the subject or sender.

### `frappe/email/smtp.py`

This file provides a wrapper around Python's `smtplib` for sending emails.

#### Class: `SMTPServer`
This class manages the connection to an SMTP server. It handles authentication (including OAuth) and provides a session object for sending emails.

**Key Methods:**
*   **`session` (property)**: Returns an active SMTP session, creating a new one if necessary.
*   **`secure_session(conn)`**: Secures the SMTP connection using TLS if configured.
*   **`quit()`**: Closes the SMTP connection.
### `frappe/email/doctype/email_queue/email_queue.py`

This file defines the `EmailQueue` DocType, which acts as a queue for outgoing emails.

#### Class: `EmailQueue(Document)`

This class represents an email that is waiting to be sent. When `frappe.sendmail` is called, it creates an `EmailQueue` document, which is then picked up by the scheduler to be sent.

**Key Methods:**

*   **`send()`**: This is the main method that sends the email. It builds the email message, connects to the SMTP server, and sends the email to the recipients.
*   **`get_email_account()`**: Determines which `Email Account` to use for sending the email.
*   **`build_message(recipient_email)`**: Constructs the final email message for a specific recipient, including replacing placeholders for tracking and unsubscribe links.

**Key Properties (Fields):**

*   **`sender`**: The sender's email address.
*   **`recipients`**: A child table (`Email Queue Recipient`) of recipients.
*   **`message`**: The full, raw email message, including headers.
*   **`status`**: The status of the email ("Not Sent", "Sending", "Sent", "Error").
*   **`communication`**: A link to the `Communication` document that was created for this email.
*   **`attachments`**: A JSON field containing a list of attachments.

### `frappe/email/doctype/notification/notification.py`

This file defines the `Notification` DocType, which is used to configure automated system notifications.

#### Class: `Notification(Document)`

This class represents a notification rule. Notifications can be triggered by various events (e.g., "New", "Save", "Submit", "Days Before/After" a date) and can be sent via different channels (Email, Slack, System Notification, SMS).

**Key Methods:**

*   **`send(doc)`**: The main method that sends the notification for a given document. It builds the list of recipients and sends the notification via the specified channel.
*   **`get_documents_for_today()`**: For date-based events, this method fetches all documents that meet the criteria to be notified today.
*   **`get_list_of_recipients(doc, context)`**: Builds the list of recipients for the notification based on the rules defined in the `recipients` child table.
*   **`get_attachment(doc)`**: If `attach_print` is checked, this method generates a PDF of the document and attaches it to the email.

**Key Properties (Fields):**

*   **`document_type`**: The DocType for which this notification is configured.
*   **`event`**: The event that triggers the notification.
*   **`channel`**: The channel through which the notification is sent.
*   **`subject`**: The subject of the notification.
*   **`message`**: The body of the notification, which can be a Jinja template.
*   **`recipients`**: A child table that defines who should receive the notification. Recipients can be specified by email address, document field, or role.

### `frappe/email/doctype/auto_email_report/auto_email_report.py`

This file defines the `AutoEmailReport` DocType, which allows users to schedule reports to be sent to them via email.

#### Class: `AutoEmailReport(Document)`

This class represents a scheduled email report. Users can select a report, specify filters, and set a schedule (daily, weekly, or monthly) for the report to be emailed to them.

**Key Methods:**

*   **`get_report_content()`**: Fetches the data for the report, formats it according to the specified format (HTML, XLSX, or CSV), and returns the content.
*   **`send()`**: The main method that sends the report. It calls `get_report_content()` and then emails the result to the specified recipients.

**Key Properties (Fields):**

*   **`user`**: The user who created the auto email report.
*   **`report`**: A link to the `Report` to be sent.
*   **`email_to`**: A list of email addresses to send the report to.
*   **`frequency`**: The frequency at which to send the report ("Daily", "Weekly", "Monthly").
*   **`format`**: The format of the report ("HTML", "XLSX", "CSV").
*   **`filters`**: A JSON field to store the filters for the report.

### `frappe/email/doctype/email_rule/email_rule.py`

This file defines the `EmailRule` DocType, which is used to create simple rules for incoming emails.

#### Class: `EmailRule(Document)`

This class represents an email rule. Currently, the only functionality is to mark emails from a specific sender as spam.

**Key Properties (Fields):**

*   **`email_id`**: The email address to which the rule applies.
*   **`is_spam`**: If checked, emails from this sender will be marked as spam.