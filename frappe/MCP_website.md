# MCP: Website Module

## Module Overview

The **Website** module is responsible for rendering the public-facing website of a Frappe application. It provides the tools and models to create and manage web pages, blogs, web forms, and other website content. This module uses a combination of DocTypes and a routing system to generate web pages dynamically from documents or static files.

Key features of the Website module include:
*   A routing system that maps URLs to specific documents or templates.
*   A `WebsiteGenerator` class that serves as a base for any DocType that needs a web view.
*   DocTypes for managing content like Web Pages, Blog Posts, and Web Forms.
*   A templating system based on Jinja for rendering web pages.

## File Index

*   `frappe/website/__init__.py`
*   `frappe/website/router.py`
*   `frappe/website/serve.py`
*   `frappe/website/utils.py`
*   `frappe/website/doctype/web_page/web_page.py`
*   `frappe/website/doctype/blog_post/blog_post.py`
*   `frappe/website/doctype/web_form/web_form.py`
*   ... and so on for all files in the `website` module.

## Public API / Callable Functions

### `frappe.website.doctype.web_form.accept(web_form, data)`
- **Description:** Saves the data submitted through a web form.
- **Arguments:**
    - `web_form` (string): The name of the `Web Form`.
    - `data` (JSON string): The data submitted in the form.
- **Returns:** The newly created or updated document.

### `frappe.website.doctype.web_page.get_dynamic_web_pages()`
- **Description:** Returns a list of all published web pages that have a dynamic route.
- **Arguments:** None.
- **Returns:** A list of dictionaries, each containing the `name`, `route`, and `modified` timestamp of a web page.

## Detailed Walkthrough

### `frappe/website/website_generator.py`

This file defines the `WebsiteGenerator` class, which is the base class for any DocType that needs to be rendered as a web page.

#### Class: `WebsiteGenerator(Document)`

This class provides the basic functionality for generating a web page from a document. It includes methods for setting the route, getting the page context, and handling website search indexing.

**Key Methods:**

*   **`validate()`**: Sets the `route` for the document if it's published.
*   **`make_route()`**: Generates a default route for the document based on its title.
*   **`get_context(context)`**: This method is meant to be overridden by subclasses to provide the context for rendering the web page template.
*   **`on_update()`**: Sends an indexing request to search engines if configured.
*   **`on_trash()`**: Sends a request to remove the page from search engine indexes.

### `frappe/website/doctype/web_page/web_page.py`

This file defines the `WebPage` DocType, which is used to create generic web pages with custom content.

#### Class: `WebPage(WebsiteGenerator)`

This class represents a web page. It can be a simple static page with HTML content, or a dynamic page with a Jinja template and a context script.

**Key Methods:**

*   **`get_context(context)`**: Builds the context for rendering the web page. It can execute a `context_script` to add dynamic data to the context. It also handles slideshows, comments, and sidebars.
*   **`render_dynamic(context)`**: Renders the main section of the page as a Jinja template if it contains dynamic content.

**Key Properties (Fields):**

*   **`title`**: The title of the web page.
*   **`route`**: The URL route for the page.
*   **`content_type`**: The type of content ("Rich Text", "Markdown", "HTML", "Page Builder").
*   **`main_section`**: The main content of the page.
*   **`published`**: A checkbox to publish or unpublish the page.
*   **`context_script`**: A Python script that can be used to add dynamic data to the page's context.

### `frappe/website/doctype/blog_post/blog_post.py`

This file defines the `BlogPost` DocType, which is used for creating blog posts.

#### Class: `BlogPost(WebsiteGenerator)`

This class represents a blog post. It includes fields for the blog title, content, category, and blogger.

**Key Methods:**

*   **`get_context(context)`**: Builds the context for rendering the blog post page. It fetches information about the blogger, social links, and comments.
*   **`set_read_time()`**: Calculates the estimated read time for the blog post based on the word count.

**Key Properties (Fields):**

*   **`title`**: The title of the blog post.
*   **`blog_category`**: The category the blog post belongs to.
*   **`blogger`**: A link to the `Blogger` who wrote the post.
*   **`content`**: The content of the blog post.
*   **`published`**: A checkbox to publish or unpublish the blog post.

### `frappe/website/doctype/web_form/web_form.py`

This file defines the `WebForm` DocType, which is used to create web forms that can be embedded on a website.

#### Class: `WebForm(WebsiteGenerator)`

This class represents a web form. It allows you to create forms that can create or update any DocType in the system.

**Key Methods:**

*   **`get_context(context)`**: Builds the context for rendering the web form. It loads the form fields and, if a document name is provided in the URL, it loads the document to be edited.
*   **`has_web_form_permission(doctype, name, ptype="read")`**: Checks if the current user has permission to access a document through the web form.

**Key Functions (outside the class):**

*   **`accept(web_form, data)`**: The main endpoint for accepting web form submissions. It creates or updates a document with the submitted data.

**Key Properties (Fields):**

*   **`doc_type`**: The DocType for which the web form is being created.
*   **`title`**: The title of the web form.
*   **`web_form_fields`**: A child table that defines the fields to be displayed in the form.
*   **`login_required`**: If checked, the user must be logged in to access the form.
*   **`allow_edit`**: If checked, users can edit existing documents through the form.

### `frappe/website/router.py`

This file is the heart of the website routing system. It's responsible for resolving a URL path to the correct content, whether it's a static page, a document with a web view, or a web form.

**Key Functions:**

*   **`resolve_route(path)`**: The main function that resolves a route. It checks for a matching route in the following order:
    1.  Static web pages (`www` or `templates/pages`).
    2.  Published documents with a `route` field.
    3.  Web pages with dynamic routes.
    4.  Web forms.
*   **`get_page_info_from_web_page_with_dynamic_routes(path)`**: Checks for a match against web pages with dynamic routes.
*   **`evaluate_dynamic_routes(rules, path)`**: Uses Werkzeug's routing system to match a path against a set of rules.
### `frappe/website/doctype/website_settings/website_settings.py`

This file defines the `WebsiteSettings` DocType, a Singleton that holds global configuration options for the website.

#### Class: `WebsiteSettings(Document)`

This class represents the central configuration document for the website. It controls various aspects of the website's appearance and behavior, such as the home page, top bar and footer items, Google Analytics integration, and more.

**Key Methods:**

*   **`validate()`**: Validates the website settings, including the top bar and footer items, the home page route, and Google settings.
*   **`on_update()`**: Clears the website cache after the settings are updated.

**Key Functions (outside the class):**

*   **`get_website_settings(context=None)`**: Fetches the website settings and populates the given context with them. This is used to provide the settings to the website's rendering context.

**Key Properties (Fields):**

*   **`home_page`**: The route of the website's home page.
*   **`top_bar_items`**, **`footer_items`**: Child tables that define the items in the website's top bar and footer menus.
*   **`website_theme`**: A link to the `Website Theme` to be used for the website.
*   **`google_analytics_id`**: The ID for Google Analytics integration.
*   **`robots_txt`**: The content of the `robots.txt` file.

### `frappe/website/doctype/website_theme/website_theme.py`

This file defines the `WebsiteTheme` DocType, which is used to create and manage themes for the website.

#### Class: `WebsiteTheme(Document)`

This class represents a website theme. It allows you to customize the appearance of the website by setting colors, fonts, and custom SCSS.

**Key Methods:**

*   **`validate()`**: Validates the theme and generates the compiled CSS file.
*   **`generate_bootstrap_theme()`**: Compiles the theme's SCSS into a CSS file using a Node.js script.
*   **`set_as_default()`**: Sets the current theme as the default website theme in `Website Settings`.

**Key Properties (Fields):**

*   **`theme`**: The name of the theme.
*   **`primary_color`**, **`secondary_color`**, etc.: Color pickers for setting the theme's colors.
*   **`google_font`**: The name of a Google Font to be used in the theme.
*   **`custom_scss`**: A field for adding custom SCSS to the theme.
*   **`theme_url`**: The URL of the compiled CSS file for the theme.

### `frappe/website/doctype/web_template/web_template.py`

This file defines the `WebTemplate` DocType, which is used to create reusable components for web pages.

#### Class: `WebTemplate(Document)`

This class represents a web template. Web templates are essentially reusable snippets of HTML that can be included in web pages. They can also have fields to accept data, making them powerful components for building complex pages.

**Key Methods:**

*   **`render(values=None)`**: Renders the web template with the given values.
*   **`export_to_files()`**: Exports the web template to a `.json` file and its HTML content to a separate `.html` file.

**Key Properties (Fields):**

*   **`name`**: The name of the web template.
*   **`type`**: The type of the template ("Component", "Section", "Navbar", "Footer").
*   **`template`**: The HTML content of the template, which can include Jinja templating tags.
*   **`fields`**: A child table (`Web Template Field`) that defines the fields that can be passed to the template as context.

### `frappe/website/utils.py`

This file contains various utility functions that are used throughout the website module.

**Key Functions:**

*   **`get_home_page()`**: Returns the route of the website's home page, considering user roles and other settings.
*   **`get_boot_data()`**: Gathers essential data needed for the website to function, such as system defaults, language settings, and asset information.
*   **`cleanup_page_name(title)`**: Creates a URL-friendly "slug" from a title.
*   **`get_full_index(app=None)`**: Returns a hierarchical map of all the static web pages in the system, used for building table of contents and navigation.
*   **`clear_cache(path=None)`**: Clears the website cache for a specific path or for the entire website.