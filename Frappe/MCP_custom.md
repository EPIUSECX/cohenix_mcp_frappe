# MCP: Custom Module

## Module Overview

The **Custom** module provides the tools for users to customize and extend the Frappe Framework without modifying the core code. This includes adding custom fields to DocTypes, changing the properties of standard fields, creating custom client-side and server-side scripts, and customizing the layout of forms.

This module is central to the flexibility of Frappe, allowing it to be adapted to a wide range of business needs.

## File Index

*   `frappe/custom/__init__.py`
*   `frappe/custom/doctype/custom_field/custom_field.py`
*   `frappe/custom/doctype/property_setter/property_setter.py`
*   `frappe/custom/doctype/client_script/client_script.py`
*   `frappe/custom/doctype/customize_form/customize_form.py`
*   ... and so on for all files in the `custom` module.

## Public API / Callable Functions

### `frappe.custom.doctype.custom_field.create_custom_field(doctype, df)`
- **Description:** Creates a new `Custom Field` document.
- **Arguments:**
    - `doctype` (string): The DocType to which the custom field should be added.
    - `df` (dict): A dictionary of properties for the new custom field.
- **Returns:** The newly created `Custom Field` document.

### `frappe.custom.doctype.property_setter.make_property_setter(doctype, fieldname, property, value, property_type, ...)`
- **Description:** Creates a new `Property Setter` document to modify a property of a standard field or DocType.
- **Arguments:**
    - `doctype` (string): The DocType being modified.
    - `fieldname` (string, optional): The field being modified.
    - `property` (string): The property to be changed.
    - `value` (any): The new value for the property.
    - `property_type` (string): The type of the property.
- **Returns:** The newly created `Property Setter` document.

## Detailed Walkthrough

### `frappe/custom/doctype/custom_field/custom_field.py`

This file defines the `CustomField` DocType, which is used to add new fields to existing DocTypes.

#### Class: `CustomField(Document)`

This class represents a custom field. It has almost the same properties as a standard `DocField`, but it is stored in a separate table and applied to the DocType at runtime.

**Key Methods:**

*   **`validate()`**: Validates the custom field, ensuring that the fieldname is unique and that the fieldtype is valid.
*   **`on_update()`**: Clears the DocType cache and updates the database schema to add the new field.
*   **`on_trash()`**: Deletes the corresponding `Property Setter` documents and removes the field from any `DocType Layouts`.

### `frappe/custom/doctype/property_setter/property_setter.py`

This file defines the `PropertySetter` DocType, which is used to change the properties of standard fields in a DocType.

#### Class: `PropertySetter(Document)`

This class represents a property setter. It allows you to override the properties of a standard field, such as its label, whether it's mandatory, or its default value.

**Key Methods:**

*   **`validate()`**: Validates the property setter, ensuring that the property being changed is valid for the field type.
*   **`on_update()`**: Clears the DocType cache so that the changes are applied.

### `frappe/custom/doctype/client_script/client_script.py`

This file defines the `ClientScript` DocType, which is used to add custom client-side scripts to forms and lists.

#### Class: `ClientScript(Document)`

This class represents a client script. It allows you to write custom JavaScript code that will be executed on the client-side for a specific DocType.

**Key Methods:**

*   **`on_update()`**: Clears the DocType cache so that the new script is loaded.
*   **`on_trash()`**: Clears the DocType cache to remove the script.

**Key Properties (Fields):**

*   **`dt`**: The DocType to which the script should be applied.
*   **`view`**: The view in which the script should be executed ("Form" or "List").
*   **`script`**: The JavaScript code to be executed.

### `frappe/custom/doctype/customize_form/customize_form.py`

This file provides the server-side logic for the "Customize Form" tool, which is a user-friendly interface for customizing forms.

#### Class: `CustomizeForm(Document)`

This is a Singleton DocType that acts as a controller for the "Customize Form" page. It doesn't store any data itself but provides the methods for fetching the form's structure and saving the customizations.

**Key Methods:**

*   **`fetch_to_customize()`**: Fetches the metadata for a DocType and populates the "Customize Form" with its fields and properties.
*   **`save_customization()`**: Saves the changes made in the "Customize Form" tool. It creates or updates `Custom Field` and `Property Setter` documents to store the customizations.
*   **`reset_to_defaults()`**: Deletes all customizations for a DocType, restoring it to its standard state.