# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/appraisal/test_appraisal.py`

## Classes

### `TestAppraisal`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `test_validate_duplicate` | `self` | `` |  |
| `test_manual_kra_rating` | `self` | `` |  |
| `test_final_score` | `self` | `` |  |
| `test_final_score_using_formula` | `self` | `` |  |
| `setup_appraisal` | `self, cycle` | `` |  |
| `test_goal_score` | `self` | `` | parent1 (12.5%) (Quality)
|_ child1 (12.5%)
        |_ child1_1 (25%)
        |_ child1_2

parent2 (50%) (Development)
|_ child2_1 (100%)
|_ child2_2 |
| `test_goal_score_after_parent_goal_change` | `self` | `` | BEFORE
parent1 (50%) (Quality)
|_ child1 (50%)

parent2 (25%) (Development)
|_ child2_1 (50%)
|_ child2_2

AFTER
parent1 (50%) (Quality)
|_ child1 (50%)
|_ child2_1 (50%)

parent2 (0%) (Development)
|_ child2_2 |
| `test_goal_score_after_kra_change` | `self` | `` |  |
| `test_goal_score_after_goal_deletion` | `self` | `` |  |
| `test_calculate_self_appraisal_score` | `self` | `` |  |
| `test_cycle_completion` | `self` | `` |  |
| `test_cycle_summary` | `self` | `` |  |





## Functions

No top-level functions found in this file.
