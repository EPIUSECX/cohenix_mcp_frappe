# How to Create Frappe Print Formats

This document explains how to create and customize Print Formats in Frappe. Print Formats allow you to define the layout and appearance of documents when they are printed or converted to PDF.

---

## 1. Core Concepts

In Frappe, Print Formats are managed as records of the "Print Format" DocType. This allows you to create multiple print formats for a single DocType and switch between them as needed.

The most powerful and flexible way to create a Print Format is by using **Custom HTML**. This involves writing a Jinja2 template to define the structure and content of the printed document.

**Example**: `POS Invoice` Print Format (`erpnext-develop/erpnext/selling/print_format/pos_invoice/pos_invoice.json`)

---

## 2. Creating a Custom HTML Print Format

To create a custom Print Format, you create a new record of the "Print Format" DocType and set the "Custom Format" property to true.

### Key Properties

- **`"doc_type"`**: The DocType this Print Format applies to (e.g., "Sales Invoice", "Purchase Order").
- **`"custom_format": 1`**: This flag indicates that you are providing your own HTML template.
- **`"html"`**: This field contains the Jinja2 template for the Print Format.

### The Jinja2 Template

The `html` field contains the full template for your print format. You can use standard HTML, CSS, and Jinja2 templating syntax.

```json
{
    "doctype": "Print Format",
    "doc_type": "POS Invoice",
    "custom_format": 1,
    "html": "<style>...</style>{% raw %}{% if letter_head %}{{ letter_head }}{% endif %}<p><b>{{ _(\\\"Receipt No\\\") }}:</b> {{ doc.name }}</p>{% endraw %}"
}
```

### Accessing Document Data

The data from the source document is available in the template through the `doc` object.

- **Accessing Fields**: You can access any field from the document using dot notation (e.g., `{{ doc.customer_name }}`, `{{ doc.grand_total }}`).
- **Formatted Values**: To display a value with its proper formatting (e.g., currency symbols, date formats), use the `doc.get_formatted()` method:
  ```jinja
  {{ doc.get_formatted("grand_total") }}
  ```
- **Child Tables**: You can iterate over child tables using a `for` loop:
  ```jinja
  {% raw %}{%- for item in doc.items -%}
      <tr>
          <td>{{ item.item_name }}</td>
          <td class="text-right">{{ item.qty }}</td>
          <td class="text-right">{{ item.get_formatted("amount") }}</td>
      </tr>
  {%- endfor -%}{% endraw %}
  ```

### Conditional Logic

You can use `if` statements to conditionally display elements in the template.

```jinja
{% raw %}{%- if doc.discount_amount -%}
    <tr>
        <td class="text-right"><b>{{ _("Discount") }}</b></td>
        <td class="text-right">{{ doc.get_formatted("discount_amount") }}</td>
    </tr>
{%- endif -%}{% endraw %}
```

### Styling

You can add custom CSS to your Print Format by including a `<style>` block in the `html` field. This allows you to control the layout, fonts, and colors of your printed document.

```html
<style>
    .print-format table, .print-format tr, .print-format td {
        vertical-align: middle;
    }
    .text-center {
        text-align: center;
    }
</style>
```

By combining HTML, CSS, and the power of Jinja2 templating, you can create professional and highly customized Print Formats for any DocType in your Frappe application.