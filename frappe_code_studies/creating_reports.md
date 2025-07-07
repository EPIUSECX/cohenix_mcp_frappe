# How to Create Frappe Reports

This document explains how to create Script and Query Reports in Frappe, with examples from the core framework. While both types exist, most complex, real-world reports in ERPNext (like the General Ledger) are **Script Reports** due to their flexibility.

---

## 1. Core Concepts & Files

A Frappe report is defined by a directory containing three key files:

- **`[report_name].json`**: Defines the report's metadata, including its name, type, and the roles that can access it.
- **`[report_name].js`**: Defines the client-side filters that users interact with to generate the report.
- **`[report_name].py`**: Contains the server-side Python script that fetches and processes the data, and defines the report's columns.

---

## 2. Script Reports

Script Reports are powerful and flexible, allowing you to use Python to generate your report data. This is the preferred method for reports that require complex logic, data manipulation, or multiple queries.

**Example**: `Gross Profit` (`erpnext-develop/erpnext/accounts/report/gross_profit/`)

### Step 1: Define Metadata (`gross_profit.json`)

The `.json` file sets the `report_type` to "Script Report".

```json
{
    "report_name": "Gross Profit",
    "report_type": "Script Report",
    "is_standard": "Yes",
    "module": "Accounts",
    "roles": [
        {
            "role": "Accounts Manager"
        },
        {
            "role": "Accounts User"
        }
    ]
}
```

- **`"report_type": "Script Report"`**: This is the most important property, telling Frappe to execute the Python script to generate the report.

### Step 2: Define Filters (`gross_profit.js`)

The `.js` file defines the filters that appear at the top of the report.

```javascript
// erpnext-develop/erpnext/accounts/report/gross_profit/gross_profit.js:4
frappe.query_reports["Gross Profit"] = {
    "filters": [
        {
            "fieldname": "company",
            "label": __("Company"),
            "fieldtype": "Link",
            "options": "Company",
            "default": frappe.defaults.get_user_default("Company"),
            "reqd": 1
        },
        {
            "fieldname": "from_date",
            "label": __("From Date"),
            "fieldtype": "Date",
            "reqd": 1
        },
        {
            "fieldname": "to_date",
            "label": __("To Date"),
            "fieldtype": "Date",
            "reqd": 1
        },
        {
            "fieldname": "group_by",
            "label": __("Group By"),
            "fieldtype": "Select",
            "options": "Invoice\nItem Code\nItem Group\nCustomer\nSales Person",
            "default": "Invoice"
        }
    ]
};
```

- **`frappe.query_reports["Gross Profit"]`**: An object that holds the report's client-side configuration.
- **`"filters"`**: An array of objects, where each object defines a filter field. The properties (`fieldname`, `label`, `fieldtype`, etc.) are similar to those in a DocType's field definition.

### Step 3: Implement Server-Side Logic (`gross_profit.py`)

The `.py` file contains the `execute` function, which generates the report's columns and data.

```python
# erpnext-develop/erpnext/accounts/report/gross_profit/gross_profit.py:21
def execute(filters=None):
    # 1. Get columns based on the "Group By" filter
    columns = get_columns(filters)

    # 2. Fetch and process the data
    gross_profit_data = GrossProfitGenerator(filters)
    data = gross_profit_data.get_data()

    # 3. Return columns and data
    return columns, data

def get_columns(filters):
    # Define columns dynamically based on filters
    columns = [
        {"label": _("Sales Invoice"), "fieldname": "sales_invoice", "fieldtype": "Link", "options": "Sales Invoice", "width": 120},
        {"label": _("Customer"), "fieldname": "customer", "fieldtype": "Link", "options": "Customer", "width": 100},
        # ... more columns
        {"label": _("Gross Profit"), "fieldname": "gross_profit", "fieldtype": "Currency", "width": 100},
        {"label": _("Gross Profit %"), "fieldname": "gross_profit_percent", "fieldtype": "Percent", "width": 100}
    ]
    return columns

class GrossProfitGenerator:
    def __init__(self, filters):
        self.filters = filters
        self.data = []
        self.process()

    def process(self):
        # Complex logic to fetch data from Sales Invoices, Stock Ledger, etc.
        # ...
        self.data = # ... processed data
```

- **`execute(filters=None)`**: The entry point for the report. It receives the user-selected filters as a dictionary.
- **Return Value**: The function **must** return a tuple containing two lists: `(columns, data)`.
- **`columns`**: A list of dictionaries, each defining a column.
- **`data`**: A list of lists or a list of dictionaries, representing the rows of the report.

---

## 3. Query Reports

Query Reports are simpler and are based on a single SQL query. They are suitable for straightforward data retrieval without complex processing.

### Required Files

- **`[report_name].json`**: Sets `"report_type": "Query Report"`.
- **`[report_name].js`**: Defines the filters, similar to a Script Report.
- **`[report_name].sql`**: Contains the SQL query to be executed.

### Example: A Simple Item Query Report

#### `item_list.json`
```json
{
    "report_name": "Item List",
    "report_type": "Query Report",
    "is_standard": "Yes",
    "module": "Stock"
}
```

#### `item_list.js`
```javascript
frappe.query_reports["Item List"] = {
    "filters": [
        {
            "fieldname": "item_group",
            "label": __("Item Group"),
            "fieldtype": "Link",
            "options": "Item Group"
        }
    ]
};
```

#### `item_list.sql`
```sql
SELECT
    item_code,
    item_name,
    item_group,
    stock_uom
FROM
    `tabItem`
WHERE
    item_group = %(item_group)s
ORDER BY
    item_name;
```

- **SQL Query**: The `.sql` file contains a standard SQL query.
- **Filters in SQL**: Filters from the `.js` file are available in the SQL query using the `%(fieldname)s` syntax.
- **Columns**: The columns are automatically inferred from the `SELECT` statement in the SQL query.

---

## 4. Important Note: General Ledger is a Script Report

It is a common misconception that the **General Ledger** is a Query Report. However, due to its complexity (handling opening/closing balances, grouping, and currency conversions), it is implemented as a **Script Report**. This is a prime example of why Script Reports are often necessary for advanced financial reporting. You can find its implementation in `erpnext-develop/erpnext/accounts/report/general_ledger/`.