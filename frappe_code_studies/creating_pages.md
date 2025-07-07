# How to Create Frappe Pages

This document explains how to create custom web pages in Frappe. There are two primary ways to create pages:

1.  **Standard Pages**: These are standalone pages with their own route, controller, and template. They are suitable for custom UI and complex applications.
2.  **Website Generators**: These are web pages that are automatically generated from a DocType's data. This is the preferred method for displaying a single record, such as a product, a blog post, or a bill of materials.

This guide focuses on the **Website Generator** pattern, as it is a common and powerful feature in Frappe.

---

## 1. The Website Generator Pattern

The Website Generator pattern allows you to create a web view for a specific DocType without having to build a completely separate page. Frappe uses a Jinja2 template to render the DocType's data on the front end.

**Example**: `BOM` (Bill of Materials) (`erpnext-develop/erpnext/manufacturing/doctype/bom/`)

### Step 1: Inherit from `WebsiteGenerator`

In your DocType's Python controller, inherit from the `WebsiteGenerator` class.

```python
# erpnext-develop/erpnext/manufacturing/doctype/bom/bom.py:102
from frappe.website.website_generator import WebsiteGenerator

class BOM(WebsiteGenerator):
    # ... controller logic
```

### Step 2: Define Web Properties

In the same Python file, define a `website` dictionary to specify the web-related properties.

```python
# erpnext-develop/erpnext/manufacturing/doctype/bom/bom.py:171
class BOM(WebsiteGenerator):
    website = frappe._dict(
        condition_field="show_in_website",
        template="templates/generators/bom.html"
    )
    # ...
```

- **`template`**: The path to the Jinja2 template that will be used to render the page. The standard location is `[your_app]/templates/generators/[doctype_name].html`.
- **`condition_field`**: The name of a checkbox field in your DocType. The web page will only be generated if this field is checked (set to 1).

### Step 3: Create the Web Template

Create the `.html` file specified in the `template` property. This is a standard Jinja2 template that has access to the DocType's data via the `doc` object.

**Example `bom.html` (Conceptual):**
```html
{% raw %}{%- extends "templates/web.html" -%}

{%- block page_content -%}
    <h1>{{ doc.item_name }}</h1>
    <p>{{ doc.description }}</p>

    <h3>Raw Materials</h3>
    <table class="table">
        <thead>
            <tr>
                <th>Item</th>
                <th>Quantity</th>
            </tr>
        </thead>
        <tbody>
            {%- for item in doc.items -%}
            <tr>
                <td>{{ item.item_name }}</td>
                <td>{{ item.qty }} {{ item.uom }}</td>
            </tr>
            {%- endfor -%}
        </tbody>
    </table>
{%- endblock -%}{% endraw %}
```

- **`{% raw %}{%- extends "templates/web.html" -%}{% endraw %}`**: Inherits from the standard web template, which provides the basic page structure, header, and footer.
- **`{{ doc.field_name }}`**: You can access any field from the DocType record using the `doc` object.

### Step 4: Pass Custom Data with `get_context`

If you need to pass additional data to your template, you can implement the `get_context` method in your Python controller.

```python
# erpnext-develop/erpnext/manufacturing/doctype/bom/bom.py:301
class BOM(WebsiteGenerator):
    # ...

    def get_context(self, context):
        # Add custom data to the context object
        context.parents = [{"name": "boms", "title": _("All BOMs")}]
        context.has_variants = # ... some logic to get variants
```

- **`context`**: An object that holds the data to be passed to the template.
- **`context.doc`**: The document object is already included in the context by default.
- You can add any custom keys and values to the `context` object, and they will be available in your Jinja2 template.

By following this pattern, you can easily create rich, data-driven web pages for any DocType in your Frappe application.