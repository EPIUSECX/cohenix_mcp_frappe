# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/putaway_rule/putaway_rule.py`

## Classes

### `PutawayRule`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `validate_duplicate_rule` | `self` | `` |  |
| `validate_priority` | `self` | `` |  |
| `validate_warehouse_and_company` | `self` | `` |  |
| `validate_capacity` | `self` | `` |  |
| `set_stock_capacity` | `self` | `` |  |





## Functions

### `get_available_putaway_capacity`
**Arguments:** `rule`
**Decorators:** ``

**Docstring:**
```

```
### `apply_putaway_rule`
**Arguments:** `doctype, items, company, sync, purpose`
**Decorators:** ``

**Docstring:**
```
Applies Putaway Rule on line items.

items: List of Purchase Receipt/Stock Entry Items
company: Company in the Purchase Receipt/Stock Entry
doctype: Doctype to apply rule on
purpose: Purpose of Stock Entry
sync (optional): Sync with client side only for client side calls
```
### `_items_changed`
**Arguments:** `old, new, doctype`
**Decorators:** ``

**Docstring:**
```
Check if any items changed by application of putaway rules.

If not, changing item table can have side effects since `name` items also changes.
```
### `get_ordered_putaway_rules`
**Arguments:** `item_code, company, source_warehouse`
**Decorators:** ``

**Docstring:**
```
Returns an ordered list of putaway rules to apply on an item.
```
### `add_row`
**Arguments:** `item, to_allocate, warehouse, updated_table, rule`
**Decorators:** ``

**Docstring:**
```

```
### `show_unassigned_items_message`
**Arguments:** `items_not_accomodated`
**Decorators:** ``

**Docstring:**
```

```

