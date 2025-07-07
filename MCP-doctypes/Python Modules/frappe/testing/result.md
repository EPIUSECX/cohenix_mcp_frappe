# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/testing/result.py`

## Classes

### `TestResult`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, stream, descriptions, verbosity` | `` |  |
| `_setupStdout` | `self` | `` |  |
| `_restoreStdout` | `self` | `` |  |
| `startTestRun` | `self` | `` |  |
| `stopTestRun` | `self` | `` |  |
| `startTest` | `self, test` | `` |  |
| `stopTest` | `self, test` | `` |  |
| `getTestMethodName` | `self, test` | `` |  |
| `addSuccess` | `self, test` | `` |  |
| `addError` | `self, test, err` | `` |  |
| `addFailure` | `self, test, err` | `` |  |
| `addSkip` | `self, test, reason` | `` |  |
| `addExpectedFailure` | `self, test, err` | `` |  |
| `addUnexpectedSuccess` | `self, test` | `` |  |
| `printErrors` | `self` | `` |  |
| `printErrorList` | `self, flavour, errors, color` | `` |  |
| `__str__` | `self` | `` |  |
| `_write_result` | `self, test, status, color, suffix` | `` |  |


### `FrappeTestResult`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, stream, descriptions, verbosity` | `` |  |
| `startTest` | `self, test` | `` |  |
| `getTestMethodName` | `self, test` | `` |  |
| `addSuccess` | `self, test` | `` |  |
| `addError` | `self, test, err` | `` |  |
| `addFailure` | `self, test, err` | `` |  |
| `addSkip` | `self, test, reason` | `` |  |
| `addExpectedFailure` | `self, test, err` | `` |  |
| `addUnexpectedSuccess` | `self, test` | `` |  |





## Functions

No top-level functions found in this file.
