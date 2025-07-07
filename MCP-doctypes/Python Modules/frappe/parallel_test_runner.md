# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/parallel_test_runner.py`

## Classes

### `ParallelTestRunner`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, app, site, build_number, total_builds, dry_run, lightmode` | `` |  |
| `setup_and_run` | `self` | `` |  |
| `setup_test_site` | `self` | `` |  |
| `before_test_setup` | `self` | `` |  |
| `setup_test_file_list` | `self` | `` |  |
| `run_tests` | `self` | `` |  |
| `run_tests_for_file` | `self, file_info` | `` |  |
| `get_module` | `self, path, filename` | `` |  |
| `print_result` | `self` | `` |  |
| `get_test_file_list` | `self` | `` |  |
| `get_test_weight` | `test` | `staticmethod` | Get approximate count of tests inside a file |


### `ParallelTestWithOrchestrator`
**Inherits:** `ParallelTestRunner`


**Docstring:**
```
This can be used to balance-out test time across multiple instances
This is dependent on external orchestrator which returns next test to run

orchestrator endpoints
- register-instance (<build_id>, <instance_id>, test_spec_list)
- get-next-test-spec (<build_id>, <instance_id>)
- test-completed (<build_id>, <instance_id>)
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, app, site` | `` |  |
| `run_tests` | `self` | `` |  |
| `get_test_file_list` | `self` | `` |  |
| `register_instance` | `self` | `` |  |
| `get_next_test` | `self` | `` |  |
| `print_result` | `self` | `` |  |
| `call_orchestrator` | `self, endpoint, data` | `` |  |





## Functions

### `split_by_weight`
**Arguments:** `work, weights, chunk_count`
**Decorators:** ``

**Docstring:**
```
Roughly split work by respective weight while keep ordering.
```
### `get_all_tests`
**Arguments:** `app`
**Decorators:** ``

**Docstring:**
```

```

