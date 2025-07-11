# Model Context Profile: `templates`

## 1. Module Overview

The `templates` module contains the Jinja2 templates used for server-side rendering throughout the Frappe Framework. This includes templates for web pages, print formats, email templates, and other system-generated documents. This module is central to the visual presentation of data and the overall user interface outside of the single-page Desk application.

Key functionalities are expected to include:
-   Base templates that define the overall page structure (`base.html`).
-   Templates for specific generated pages like login, error pages, and lists.
-   Includes and macros that provide reusable template components.
-   Templates for system emails like password resets and notifications.

## 2. File Index

The `templates` module is organized into several key directories:

-   **`base.html`**: The master template for every page generated by the system, both for the website and for system pages like login and print views.
-   **`web.html`**: The base template for all standard website pages. It extends `base.html`.
-   **`pages/`**: Contains templates for specific, standalone pages like login, error pages, and password reset forms.
-   **`includes/`**: Contains reusable HTML snippets that are included in other templates (e.g., `meta_block.html`, `head.html`, `breadcrumbs.html`).
-   **`emails/`**: Contains templates for system-generated emails.
-   **`print_formats/`**: Contains templates for standard print formats.
-   **`styles/`**: Contains CSS files that are not part of the main build system but are included in specific templates.

## 3. Public API / Callable Functions

This module does not contain a Python API. Its "API" is the set of templates that can be rendered by the `frappe.render_template` function.

## 4. Detailed Walkthrough

The templating system is built on Jinja2 and uses a block-based inheritance structure to allow for easy customization and extension.

### `base.html`

This is the root of all server-rendered HTML pages in Frappe.

-   **Structure**: It defines the basic `<html>`, `<head>`, and `<body>` structure.
-   **`{% block %}`**: It is heavily populated with Jinja blocks (`{% block title %}`, `{% block head %}`, `{% block content %}`, etc.). This allows any child template that extends `base.html` to override specific parts of the page.
-   **`frappe.boot`**: A critical `<script>` tag in the `<head>` section serializes the `frappe.boot` object into JavaScript. This object contains essential information for the client-side application, such as system settings, user information, and translations.
-   **Asset Loading**: It includes the core JavaScript and CSS bundles (`frappe-web.bundle.js`) and provides blocks (`web_include_js`, `web_include_css`) for child templates to add their own assets.

### `web.html`

This template serves as the base for all standard website pages (e.g., pages generated from the `Web Page` DocType or `WebsiteGenerator` DocTypes).

-   **`{% extends base_template_path %}`**: It inherits from `base.html`. The `base_template_path` variable allows the base template to be overridden by themes or other apps.
-   **Layout and Structure**: It defines the main content layout, including a container, a page header, the main content area, and an optional sidebar.
-   **Macros**: It defines several Jinja macros (`main_content`, `sidebar`) to create reusable components within the template itself.
-   **Sidebar Logic**: It contains logic to render a sidebar on the left or right, or not at all, based on the `show_sidebar` and `sidebar_right` context variables.
-   **`page_content` block**: This is the primary block that child website templates will override to provide their specific content.

### Page Templates (e.g., in `templates/pages/`)

Specific pages like the login page, password reset page, or error pages are defined in the `pages` directory. These templates typically extend `base.html` (or sometimes `web.html`) and override the `page_content` block to provide their specific forms and content. They serve as concrete examples of how the template inheritance system works.