# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/goal/test_goal.py`

## Classes

### `TestGoal`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_validate_parent_fields` | `self` | `` |  |
| `test_set_status` | `self` | `` |  |
| `test_update_parent_progress` | `self` | `` |  |
| `test_update_parent_progress_on_goal_deletion` | `self` | `` |  |
| `test_update_parent_progress_with_nested_goals` | `self` | `` | parent (12.5%)
|_ child1
|_ child2 (25%)
        |_ child3 (50%)
        |_ child4 |
| `test_update_old_parent_progress` | `self` | `` | BEFORE
parent1 (12.5%)
|_ child1 (12.5%)
        |_ child1_1 (25%)
        |_ child1_2

parent2 (25%)
|_ child2 (25%)
        |_ child2_1 (50%)
        |_ child2_2

AFTER
parent1 (16.667%)
|_ child1 (16.667%)
        |_ child1_1 (25%)
        |_ child1_2
        |_ child2 (25%)
                |_ child2_1 (50%)
                |_ child2_2

parent2 (0%) |
| `test_update_kra_in_child_goals` | `self` | `` |  |
| `test_update_status` | `self` | `` |  |





## Functions

### `create_goal`
**Arguments:** `employee, kra, is_group, parent_goal, appraisal_cycle, progress`
**Decorators:** ``

**Docstring:**
```

```

