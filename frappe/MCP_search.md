# Model Context Profile: `search`

## 1. Module Overview

The `search` module is responsible for providing the global search functionality within the Frappe Framework. This includes the "Awesome Bar" in the Desk UI and the website search. It likely contains the logic for indexing documents, building search queries, and ranking results.

Key functionalities are expected to include:
-   Indexing of documents for full-text search.
-   Handling search queries from the client-side.
-   Ranking and formatting of search results.
-   Integration with the database's full-text search capabilities.

## 2. File Index

-   **`full_text_search.py`**: Defines the base `FullTextSearch` class, which provides a generic wrapper around the `whoosh` library for creating, updating, and searching a full-text index.
-   **`website_search.py`**: Defines the `WebsiteSearch` class, which inherits from `FullTextSearch` and specializes it for indexing and searching website routes.

## 3. Public API / Callable Functions

-   **`frappe.search.website_search.build_index_for_all_routes()`**: The main entry point for building the entire website search index. This is typically called from a scheduled job or the `bench build-search-index` command.
-   **`frappe.search.website_search.update_index_for_path(path)`**: Updates the search index for a single web page path. This is called from hooks when a web-viewable document is saved.
-   **`frappe.search.website_search.remove_document_from_index(path)`**: Removes a specific path from the search index, for example when a document is unpublished or deleted.

## 4. Detailed Walkthrough

The search functionality in Frappe is built on the `whoosh` library. The `search` module provides a high-level abstraction over `whoosh` to simplify the process of indexing and searching documents.

### `full_text_search.py`

This file provides a generic, reusable class for full-text search.

-   **`FullTextSearch` Class**:
    -   **`__init__(self, index_name)`**: The constructor takes an `index_name`, which is used to create a corresponding directory in `sites/{sitename}/indexes/` to store the `whoosh` index files.
    -   **`get_schema()`**: Defines the structure of the search index. The base schema includes a `name` (the unique ID of the document) and `content` (the text to be searched). This method is intended to be overridden by subclasses to define more specific schemas.
    -   **`build()`**: This is the main method for creating the index from scratch. It calls `get_items_to_index()` (which should be implemented by a subclass) to get a list of all documents to be indexed, and then iterates through them, adding each one to the `whoosh` index using an `AsyncWriter` for performance.
    -   **`update_index(document)` / `remove_document_from_index(doc_name)`**: These methods provide the interface for incrementally updating or removing single documents from the index after it has been built.
    -   **`search(text, ...)`**: This method performs the actual search. It uses `whoosh`'s `MultifieldParser` to search across multiple fields (defined in `get_fields_to_search()`). It also uses a custom `FuzzyTermExtended` class to enable fuzzy (typo-tolerant) searching.

### `website_search.py`

This file implements the specific logic for website search by inheriting from `FullTextSearch`.

-   **`WebsiteSearch` Class**:
    -   **`get_schema()`**: It overrides the base method to define a schema specific to web pages: `title`, `path` (as the unique ID), and `content`.
    -   **`get_items_to_index()`**: This is the core logic for discovering all searchable web pages. It does this by:
        1.  Calling `get_static_pages_from_all_apps()` to find all static `www` pages (`.html`, `.md`) in all installed apps.
        2.  Calling `slugs_with_web_view()` to find all documents that have the "Has Web View" property checked in their DocType definition (e.g., Blog Post, Web Page, Product). It only includes documents that are published and viewable by guests.
    -   **`get_document_to_index(route)`**: For a given route, this method simulates a web request using `frappe.set_request()` and renders the page's HTML content using `get_response_content()`. It then uses `BeautifulSoup` to parse the HTML, extracting the page title and the text content from the main page area, which are then used for indexing. This ensures that the indexed content is the same as what a user would see.
    -   **`parse_result(result)`**: This method takes a search result from `whoosh` and formats it for display, including generating highlighted snippets of the title and content that show where the search term was found.