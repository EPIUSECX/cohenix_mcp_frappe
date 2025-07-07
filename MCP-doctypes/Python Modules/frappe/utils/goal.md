# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/goal.py`

## Classes

No classes found in this file.


## Functions

### `get_monthly_results`
**Arguments:** `goal_doctype, goal_field, date_col, filters, aggregation`
**Decorators:** ``

**Docstring:**
```
Get monthly aggregation values for given field of doctype
```
### `get_monthly_goal_graph_data`
**Arguments:** `title, doctype, docname, goal_value_field, goal_total_field, goal_history_field, goal_doctype, goal_doctype_link, goal_field, date_field, aggregation, filters`
**Decorators:** ``

**Docstring:**
```
Get month-wise graph data for a doctype based on aggregation values of a field in the goal doctype

:param title: Graph title
:param doctype: doctype of graph doc
:param docname: of the doc to set the graph in
:param goal_value_field: goal field of doctype
:param goal_total_field: current month value field of doctype
:param goal_history_field: cached history field
:param goal_doctype: doctype the goal is based on
:param goal_doctype_link: doctype link field in goal_doctype
:param goal_field: field from which the goal is calculated
:param aggregation: a value like 'count', 'sum', 'avg'
:param filters: optional filters

:return: dict of graph data
```

