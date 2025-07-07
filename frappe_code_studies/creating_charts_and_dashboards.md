# How to Create Frappe Charts and Dashboards

This document explains how to create and structure Dashboards, Dashboard Charts, and Number Cards in Frappe. These components are all managed as standard DocTypes, allowing for easy creation and customization.

---

## 1. Core Concepts

Dashboards in Frappe are composed of three main DocTypes:

- **Dashboard**: The main container that holds and arranges charts and number cards.
- **Dashboard Chart**: A visual representation of data, typically from a Report.
- **Number Card**: A card that displays a single, aggregated value from a DocType.

---

## 2. Creating a Dashboard Chart

A Dashboard Chart visualizes data from a source Report.

**Example**: `Sales Order Trends` (`erpnext-develop/erpnext/selling/dashboard_chart/sales_order_trends/sales_order_trends.json`)

### Key Properties

To create a Dashboard Chart, you create a new record of the "Dashboard Chart" DocType with the following properties:

```json
{
    "doctype": "Dashboard Chart",
    "chart_name": "Sales Order Trends",
    "chart_type": "Report",
    "report_name": "Sales Order Trends",
    "type": "Line",
    "is_public": 1,
    "filters_json": "{\\"period\\":\\"Monthly\\",\\"based_on\\":\\"Item\\"}",
    "dynamic_filters_json": "{\\"company\\":\\"frappe.defaults.get_user_default(\\\\\\"Company\\\\\\")\\"}"
}
```

- **`"chart_name"`**: The name of the chart record.
- **`"chart_type"`**: The source of the data. Set to `"Report"` to use a Frappe Report.
- **`"report_name"`**: The name of the source Report (e.g., "Sales Order Trends").
- **`"type"`**: The type of chart to display (e.g., "Line", "Bar", "Pie").
- **`"filters_json"`**: A JSON string of static filters to apply to the source report.
- **`"dynamic_filters_json"`**: A JSON string of dynamic filters, which can use Frappe's JavaScript API to get values (e.g., the current user's company).

---

## 3. Creating a Number Card

A Number Card displays a single, aggregated value from a DocType.

**Example**: `Sales Orders to Bill` (`erpnext-develop/erpnext/selling/number_card/sales_orders_to_bill/sales_orders_to_bill.json`)

### Key Properties

To create a Number Card, you create a new record of the "Number Card" DocType:

```json
{
    "doctype": "Number Card",
    "label": "Sales Orders to Bill",
    "document_type": "Sales Order",
    "function": "Count",
    "type": "Document Type",
    "is_public": 1,
    "filters_json": "[[\"Sales Order\",\"status\",\"in\",[\"To Deliver and Bill\",\"To Bill\"]],[\"Sales Order\",\"docstatus\",\"=\",\"1\"]]",
    "dynamic_filters_json": "[[\"Sales Order\",\"company\",\"=\",\"frappe.defaults.get_user_default(\\\"Company\\\")\"]]"
}
```

- **`"label"`**: The text displayed on the card.
- **`"document_type"`**: The source DocType to query (e.g., "Sales Order").
- **`"function"`**: The aggregation function to apply ("Count", "Sum", "Average", "Min", "Max").
- **`"type"`**: The type of data source. Set to `"Document Type"` for DocTypes.
- **`"filters_json"`** and **`"dynamic_filters_json"`**: JSON strings of filters to apply to the DocType records before aggregation.

---

## 4. Assembling a Dashboard

A Dashboard is a record of the "Dashboard" DocType that links to your charts and number cards.

**Example**: `Selling` Dashboard (`erpnext-develop/erpnext/selling/selling_dashboard/selling/selling.json`)

### Key Properties

To create a Dashboard, you create a new record of the "Dashboard" DocType:

```json
{
    "doctype": "Dashboard",
    "dashboard_name": "Selling",
    "is_standard": 1,
    "charts": [
        {
            "chart": "Sales Order Trends",
            "width": "Full"
        },
        {
            "chart": "Top Customers",
            "width": "Half"
        }
    ],
    "cards": [
        {
            "card": "Annual Sales"
        },
        {
            "card": "Sales Orders to Bill"
        }
    ]
}
```

- **`"dashboard_name"`**: The name of the dashboard.
- **`"charts"`**: A child table listing the "Dashboard Chart" records to display.
    - **`"chart"`**: The name of the Dashboard Chart record.
    - **`"width"`**: The width of the chart on the dashboard ("Full" or "Half").
- **`"cards"`**: A child table listing the "Number Card" records to display.
    - **`"card"`**: The name of the Number Card record.

By creating these three types of documents and linking them together, you can build powerful and informative dashboards for any module in your Frappe application.