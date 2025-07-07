# Model Context Profile: `www`

## 1. Module Overview

The `www` module is responsible for rendering standard, server-side web pages that are part of the core Frappe Framework. These are typically un-styled or minimally styled pages that provide essential functionality like login, document lists, and print views. This module operates on a simple convention: for a URL like `/login`, the framework looks for a `frappe/www/login.py` file and a `frappe/www/login.html` file.

The Python file's `get_context` function is executed to fetch and prepare data, which is then passed to the Jinja template in the corresponding HTML file for rendering. This provides a straightforward way to create data-driven web pages without the complexity of the full `website` module's routing and content management system.

## 2. File Structure and Key Components

The `www` directory is mostly flat, containing pairs of `.py` and `.html` files for each web page.

```
frappe/www/
├── login.py                # Backend logic for the login page.
├── login.html              # Jinja template for the login page.
├── list.py                 # Backend logic for generic list views.
├── list.html               # Jinja template for generic list views.
├── printview.py            # Backend logic for preparing print format data.
├── printview.html          # Jinja template that renders the print format HTML.
├── sitemap.py              # Logic to generate sitemap URLs.
├── sitemap.xml             # Jinja template for the sitemap.
├── robots.py               # Logic to fetch robots.txt content.
└── robots.txt              # Jinja template for robots.txt.
```

## 3. Key Files and Functions

### `login.py`
-   **`get_context(context)`**: Prepares the context for the login page. It handles redirects for already logged-in users, fetches social login providers (like Google, GitHub), enables LDAP login if configured, and sets up options for passwordless email-based login.

### `list.py`
-   **`get_context(context)`**: Prepares the context for a generic document list page (e.g., `/blog`). It determines the DocType from the URL, fetches the list of documents using `get_list_data`, and prepares them for rendering.
-   **`get_list_data(...)`**: A generic function to fetch a list of documents for the website. It applies filters based on URL query parameters and published status (`is_published_field`). It also respects the `get_list_context` hook from the DocType's controller to allow for custom queries and filters.

### `printview.py`
-   **`get_context(context)`**: The core of the print format rendering engine. It fetches the document to be printed, gets the specified `Print Format` (or the standard one), and renders the document data into the print format's HTML template.
-   **`get_rendered_template(...)`**: This function orchestrates the rendering. It validates print permissions, applies print settings, fetches the letterhead, and uses Jinja to combine the document data with the print format template. It also handles the conversion of Markdown in "Text Editor" fields to HTML.
-   **`make_layout(...)`**: A crucial utility that builds a structured, hierarchical layout of the document's fields based on the Print Format definition or the DocType's field order. This layout is what the `standard.html` print format uses to render fields in sections and columns.

### `sitemap.py` & `robots.py`
-   **`sitemap.py: get_context(context)`**: Generates the list of URLs for the `sitemap.xml`. It queries all "Web Pages" and all published documents from DocTypes that have a web view (e.g., Blog Post, Help Article) to create a comprehensive list for search engines.
-   **`robots.py: get_context(context)`**: Fetches the content for the `robots.txt` file from `Website Settings`. This allows administrators to control web crawler access directly from the UI.

## 4. Dependencies and Interactions

-   **Jinja2 Templating**: The `www` module is entirely dependent on Frappe's Jinja2 rendering engine. The `.py` files prepare the context, and the `.html` files render it.
-   **`frappe.get_doc` / `frappe.get_list`**: These are the primary functions used by the Python context files to fetch document data from the database.
-   **Website Settings**: Many pages, like `login.py` and `robots.py`, pull their configuration from the "Website Settings" singleton DocType.
-   **Print Formats**: `printview.py` is tightly coupled with the "Print Format" and "Print Settings" DocTypes to produce document prints.