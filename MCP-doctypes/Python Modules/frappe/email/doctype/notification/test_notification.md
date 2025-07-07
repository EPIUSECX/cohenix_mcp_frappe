# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/email/doctype/notification/test_notification.py`

## Classes

### `TestNotification`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUp` | `self` | `` |  |
| `tearDown` | `self` | `` |  |
| `test_new_and_save` | `self` | `` | Check creating a new communication triggers a notification. |
| `test_condition` | `self` | `` | Check notification is triggered based on a condition. |
| `test_invalid_condition` | `self` | `` |  |
| `test_value_changed` | `self` | `` |  |
| `test_minutes_positive_offset` | `self` | `` |  |
| `test_minutes_negative_offset` | `self` | `` |  |
| `test_minutes_offset_validation` | `self` | `` |  |
| `test_alert_disabled_on_wrong_field` | `self` | `` |  |
| `test_date_changed` | `self` | `` |  |
| `test_cc_jinja` | `self` | `` |  |
| `test_notification_to_assignee` | `self` | `` |  |
| `test_notification_by_child_table_field` | `self` | `` |  |
| `test_notification_value_change_casted_types` | `self` | `` | Make sure value change event dont fire because of incorrect type comparisons. |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_notification_with_jinja_template` | `self` | `` | Test Notification with Jinja Template |





## Functions

### `get_test_notification`
**Arguments:** `config`
**Decorators:** `contextmanager`

**Docstring:**
```

```

