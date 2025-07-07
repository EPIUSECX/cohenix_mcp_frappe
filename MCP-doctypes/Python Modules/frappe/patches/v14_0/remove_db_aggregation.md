# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/patches/v14_0/remove_db_aggregation.py`

## Classes

No classes found in this file.


## Functions

### `execute`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Replace temporarily available Database Aggregate APIs on frappe (develop)

APIs changed:
        * frappe.db.max => frappe.qb.max
        * frappe.db.min => frappe.qb.min
        * frappe.db.sum => frappe.qb.sum
        * frappe.db.avg => frappe.qb.avg
```

