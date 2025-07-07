# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/support/doctype/service_level_agreement/service_level_agreement.py`

## Classes

### `ServiceLevelAgreement`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `check_priorities` | `self` | `` |  |
| `check_support_and_resolution` | `self` | `` |  |
| `validate_doc` | `self` | `` |  |
| `validate_selected_doctype` | `self` | `` |  |
| `validate_status_field` | `self` | `` |  |
| `validate_condition` | `self` | `` |  |
| `get_service_level_agreement_priority` | `self, priority` | `` |  |
| `before_insert` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `clear_cache` | `self` | `` |  |
| `create_docfields` | `self, meta, service_level_agreement_fields` | `` |  |
| `create_custom_fields` | `self, meta, service_level_agreement_fields` | `` |  |
| `reset_field_properties` | `self, field, field_dt, sla_field` | `` |  |





## Functions

### `check_agreement_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_active_service_level_agreement_for`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_context`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_group`
**Arguments:** `customer`
**Decorators:** ``

**Docstring:**
```

```
### `get_customer_territory`
**Arguments:** `customer`
**Decorators:** ``

**Docstring:**
```

```
### `get_service_level_agreement_filters`
**Arguments:** `doctype, name, customer`
**Decorators:** ``

**Docstring:**
```

```
### `get_repeated`
**Arguments:** `values`
**Decorators:** ``

**Docstring:**
```

```
### `get_documents_with_active_service_level_agreement`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `set_documents_with_active_service_level_agreement`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `apply`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```
### `remove_sla_if_applied`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `process_sla`
**Arguments:** `doc, sla`
**Decorators:** ``

**Docstring:**
```

```
### `handle_status_change`
**Arguments:** `doc, apply_sla_for_resolution`
**Decorators:** ``

**Docstring:**
```

```
### `get_fulfillment_statuses`
**Arguments:** `service_level_agreement`
**Decorators:** ``

**Docstring:**
```

```
### `get_hold_statuses`
**Arguments:** `service_level_agreement`
**Decorators:** ``

**Docstring:**
```

```
### `update_response_and_resolution_metrics`
**Arguments:** `doc, apply_sla_for_resolution`
**Decorators:** ``

**Docstring:**
```

```
### `get_expected_time_for`
**Arguments:** `parameter, service_level, start_date_time`
**Decorators:** ``

**Docstring:**
```

```
### `get_allotted_seconds`
**Arguments:** `parameter, service_level`
**Decorators:** ``

**Docstring:**
```

```
### `get_support_days`
**Arguments:** `service_level`
**Decorators:** ``

**Docstring:**
```

```
### `set_resolution_time`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `change_service_level_agreement_and_priority`
**Arguments:** `self`
**Decorators:** ``

**Docstring:**
```

```
### `get_response_and_resolution_duration`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `reset_service_level_agreement`
**Arguments:** `doctype, docname, reason, user`
**Decorators:** ``

**Docstring:**
```

```
### `reset_resolution_metrics`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `on_communication_update`
**Arguments:** `doc, status`
**Decorators:** ``

**Docstring:**
```

```
### `reset_expected_response_and_resolution`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_response_by`
**Arguments:** `doc, start_date_time, priority`
**Decorators:** ``

**Docstring:**
```

```
### `set_resolution_by`
**Arguments:** `doc, start_date_time, priority`
**Decorators:** ``

**Docstring:**
```

```
### `record_assigned_users_on_failure`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_service_level_agreement_fields`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `update_agreement_status_on_custom_status`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `update_agreement_status`
**Arguments:** `doc, apply_sla_for_resolution`
**Decorators:** ``

**Docstring:**
```

```
### `is_holiday`
**Arguments:** `date, holidays`
**Decorators:** ``

**Docstring:**
```

```
### `get_time_in_timedelta`
**Arguments:** `time`
**Decorators:** ``

**Docstring:**
```
Converts datetime.time(10, 36, 55, 961454) to datetime.timedelta(seconds=38215).
```
### `now_datetime`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `convert_utc_to_user_timezone`
**Arguments:** `utc_timestamp, user`
**Decorators:** ``

**Docstring:**
```

```
### `get_tz`
**Arguments:** `user`
**Decorators:** ``

**Docstring:**
```

```
### `get_user_time`
**Arguments:** `user, to_string`
**Decorators:** ``

**Docstring:**
```

```
### `get_sla_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_sla_doctypes`
**Arguments:** `bootinfo`
**Decorators:** ``

**Docstring:**
```

```

