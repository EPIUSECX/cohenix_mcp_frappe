# Model Context Profile: Portal

## 1. Module Overview

The `portal` module in ERPNext provides functionalities for the customer and supplier-facing web portal. It has two primary responsibilities:

1.  **E-commerce Filtering Configuration**: It provides data models to configure how items are filtered and what attributes are displayed on the website portal.
2.  **User and Party Management**: It includes logic to automate the creation of `Customer` and `Supplier` entities when a new `Website User` signs up, streamlining the onboarding process for B2B and B2C portals.

This module bridges the gap between backend ERP data (like Item Attributes and Parties) and the frontend website experience.

## 2. Core Components

### 2.1. DocTypes

The `portal` module contains two child DocTypes used for configuration within other, parent DocTypes (likely `Website Settings`).

-   **`Website Attribute` (Child Table)**: This DocType is used to create a list of `Item Attribute` records. Its purpose is to define which specific attributes of an item (e.g., "Color", "Size", "Brand") should be made visible on the product listing pages of the web portal.
    -   **Key Fields**:
        -   `attribute`: A Link to the `Item Attribute` DocType.

-   **`Website Filter Field` (Child Table)**: This DocType is used to specify which fields of a DocType (e.g., `Item`) can be used as filters on the website. This allows users to narrow down product listings based on specific criteria.
    -   **Key Fields**:
        -   `fieldname`: An `Autocomplete` field that stores the name of the field to be used for filtering.

### 2.2. Business Logic (`utils.py`)

The business logic in `portal/utils.py` focuses on automating the relationship between a `Website User` and their corresponding `Customer` or `Supplier` record.

-   **`create_customer_or_supplier()`**: This is the main function, triggered on session creation (`on_session_creation` hook). It checks the `default_role` set in `Portal Settings`. If a new Website User has this role (e.g., "Customer"), the system automatically:
    1.  Creates a new `Customer` (or `Supplier`) document.
    2.  Populates it with the user's full name.
    3.  Creates a `Contact` document and links it to both the user's email and the newly created party (Customer/Supplier).
    This ensures that a user who signs up on the portal immediately has a corresponding party record in the ERP backend.

-   **`set_default_role(doc, method)`**: This function is typically called on the `User` DocType's `on_update` event. It checks if the user's email is already linked to a `Contact`. If that `Contact` is linked to a `Customer` or `Supplier`, the corresponding role is automatically assigned to the `User`.

-   **`party_exists(doctype, user)`**: A helper function that checks if a `Contact` with the user's email is already linked to the specified party `doctype` (`Customer` or `Supplier`). This prevents the creation of duplicate party records.

## 3. Data Models

The data models are simple child tables designed for embedding in configuration documents.

### `Website Attribute`
```json
{
 "doctype": "DocType",
 "istable": 1,
 "module": "Portal",
 "name": "Website Attribute",
 "fields": [
  {
   "fieldname": "attribute",
   "fieldtype": "Link",
   "label": "Attribute",
   "options": "Item Attribute",
   "reqd": 1
  }
 ]
}
```

### `Website Filter Field`
```json
{
 "doctype": "DocType",
 "istable": 1,
 "module": "Portal",
 "name": "Website Filter Field",
 "fields": [
  {
   "fieldname": "fieldname",
   "fieldtype": "Autocomplete",
   "label": "Fieldname"
  }
 ]
}
```

## 4. Integrations and Dependencies

-   **`Portal Settings`**: The logic in `utils.py` is heavily dependent on the `default_role` configured in the `Portal Settings` singleton DocType.
-   **`User`**: The module interacts with the `User` DocType to assign roles and identify `Website User` types.
-   **`Contact`**: The `Contact` DocType is used as the central link between a `User`'s email and their associated `Customer` or `Supplier` party records.
-   **`Customer` / `Supplier`**: The module's primary automation goal is to create these party DocTypes.
-   **`Item Attribute`**: The `Website Attribute` DocType directly links to `Item Attribute` to control website display.

## 5. Architectural Significance

The `portal` module is a key component for enabling self-service and e-commerce functionalities in ERPNext. By automating party creation, it reduces administrative overhead and provides a smoother user experience. The filtering and attribute configurations provide the necessary tools to build a functional and user-friendly online product catalog from the items managed within the ERP.

## 6. Callable Functions (`@frappe.whitelist()`)

This module has **no whitelisted functions**. Its logic is executed via server-side hooks (`on_session_creation`, `on_update`) and it does not expose any callable API methods.