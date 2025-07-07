# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/issue/test_issue.py`

## Classes

### `TestSetUp`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |


### `TestIssue`
**Inherits:** `TestSetUp`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_response_time_and_resolution_time_based_on_different_sla` | `self` | `` |  |
| `test_hold_time_on_replied` | `self` | `` |  |
| `test_issue_close_after_on_hold` | `self` | `` |  |
| `test_issue_open_after_closed` | `self` | `` |  |
| `test_recording_of_assignment_on_first_reponse_failure` | `self` | `` |  |
| `test_agreement_status_on_response` | `self` | `` |  |


### `TestFirstResponseTime`
**Inherits:** `TestSetUp`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_first_response_time_case1` | `self` | `` | Test frt when issue creation and first response are during working hours on the same day. |
| `test_first_response_time_case2` | `self` | `` | Test frt when issue creation was during working hours, but first response is sent after working hours on the same day. |
| `test_first_response_time_case3` | `self` | `` | Test frt when issue creation was before working hours but first response is sent during working hours on the same day. |
| `test_first_response_time_case4` | `self` | `` | Test frt when both issue creation and first response were after working hours on the same day. |
| `test_first_response_time_case5` | `self` | `` | Test frt when both issue creation and first response are on the same day, but it's not a work day. |
| `test_first_response_time_case6` | `self` | `` | Test frt when the issue was created before working hours and the first response is also sent before working hours, but on the next day. |
| `test_first_response_time_case7` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent during working hours, but on the next day. |
| `test_first_response_time_case8` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent after working hours, but on the next day. |
| `test_first_response_time_case9` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent on the next day, which is not a work day. |
| `test_first_response_time_case10` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent before working hours, but on the next day. |
| `test_first_response_time_case11` | `self` | `` | Test frt when the issue was created during working hours and the first response is also sent during working hours, but on the next day. |
| `test_first_response_time_case12` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent after working hours, but on the next day. |
| `test_first_response_time_case13` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent on the next day, which is not a work day. |
| `test_first_response_time_case14` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent before working hours, but on the next day. |
| `test_first_response_time_case15` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent during working hours, but on the next day. |
| `test_first_response_time_case16` | `self` | `` | Test frt when the issue was created after working hours and the first response is also sent after working hours, but on the next day. |
| `test_first_response_time_case17` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent on the next day, which is not a work day. |
| `test_first_response_time_case18` | `self` | `` | Test frt when the issue was created before working hours and the first response is also sent before working hours, but after a few days. |
| `test_first_response_time_case19` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent during working hours, but after a few days. |
| `test_first_response_time_case20` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent after working hours, but after a few days. |
| `test_first_response_time_case21` | `self` | `` | Test frt when the issue was created before working hours and the first response is sent after a few days, on a holiday. |
| `test_first_response_time_case22` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent before working hours, but after a few days. |
| `test_first_response_time_case23` | `self` | `` | Test frt when the issue was created during working hours and the first response is also sent during working hours, but after a few days. |
| `test_first_response_time_case24` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent after working hours, but after a few days. |
| `test_first_response_time_case25` | `self` | `` | Test frt when the issue was created during working hours and the first response is sent after a few days, on a holiday. |
| `test_first_response_time_case26` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent before working hours, but after a few days. |
| `test_first_response_time_case27` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent during working hours, but after a few days. |
| `test_first_response_time_case28` | `self` | `` | Test frt when the issue was created after working hours and the first response is also sent after working hours, but after a few days. |
| `test_first_response_time_case29` | `self` | `` | Test frt when the issue was created after working hours and the first response is sent after a few days, on a holiday. |





## Functions

### `create_issue_and_communication`
**Arguments:** `issue_creation, first_responded_on`
**Decorators:** ``

**Docstring:**
```

```
### `make_issue`
**Arguments:** `creation, customer, index, priority, issue_type`
**Decorators:** ``

**Docstring:**
```

```
### `create_customer`
**Arguments:** `name, customer_group, territory`
**Decorators:** ``

**Docstring:**
```

```
### `create_customer_group`
**Arguments:** `customer_group`
**Decorators:** ``

**Docstring:**
```

```
### `create_territory`
**Arguments:** `territory`
**Decorators:** ``

**Docstring:**
```

```
### `create_communication`
**Arguments:** `reference_name, sender, sent_or_received, creation`
**Decorators:** ``

**Docstring:**
```

```

