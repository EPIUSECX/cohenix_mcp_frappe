# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/putaway_rule/test_putaway_rule.py`

## Classes

### `TestPutawayRule`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `assertUnchangedItemsOnResave` | `self, doc` | `` | Check if same items remain even after reapplication of rules.

This is required since some business logic like subcontracting
depends on `name` of items to be same if item isn't changed. |
| `test_putaway_rules_priority` | `self` | `` | Test if rule is applied by priority, irrespective of free space. |
| `test_putaway_rules_with_same_priority` | `self` | `` | Test if rule with more free space is applied,
among two rules with same priority and capacity. |
| `test_putaway_rules_with_insufficient_capacity` | `self` | `` | Test if qty exceeding capacity, is handled. |
| `test_putaway_rules_multi_uom` | `self` | `` | Test rules applied on uom other than stock uom. |
| `test_putaway_rules_multi_uom_whole_uom` | `self` | `` | Test if whole UOMs are handled. |
| `test_putaway_rules_with_reoccurring_item` | `self` | `` | Test rules on same item entered multiple times with different rate. |
| `test_validate_over_receipt_in_warehouse` | `self` | `` | Test if overreceipt is blocked in the presence of putaway rules. |
| `test_putaway_rule_on_stock_entry_material_transfer` | `self` | `` | Test if source warehouse is considered while applying rules. |
| `test_putaway_rule_on_stock_entry_material_transfer_reoccuring_item` | `self` | `` | Test if reoccuring item is correctly considered. |
| `test_putaway_rule_on_stock_entry_material_transfer_batch_serial_item` | `self` | `` | Test if batch and serial items are split correctly. |
| `test_putaway_rule_on_stock_entry_material_receipt` | `self` | `` | Test if rules are applied in Stock Entry of type Receipt. |
| `test_warehouse_capacity_dashbord` | `self` | `` |  |





## Functions

### `create_putaway_rule`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

