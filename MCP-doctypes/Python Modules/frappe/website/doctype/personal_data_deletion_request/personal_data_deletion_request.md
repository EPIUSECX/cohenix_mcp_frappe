# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/website/doctype/personal_data_deletion_request/personal_data_deletion_request.py`

## Classes

### `PersonalDataDeletionRequest`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `generate_url_for_confirmation` | `self` | `` |  |
| `disable_user` | `self` | `` |  |
| `send_verification_mail` | `self` | `` |  |
| `notify_system_managers` | `self` | `` |  |
| `validate_data_anonymization` | `self` | `` |  |
| `trigger_data_deletion` | `self` | `` | Redact user data defined in current site's hooks under `user_data_fields` |
| `anonymize_data` | `self` | `` |  |
| `notify_user_after_deletion` | `self` | `` |  |
| `add_deletion_steps` | `self` | `` |  |
| `redact_partial_match_data` | `self, doctype` | `` |  |
| `rename_documents` | `self, doctype` | `` |  |
| `redact_full_match_data` | `self, ref, email` | `` | Replaces the entire field value by the values set in the anonymization_value_map |
| `generate_anonymization_dict` | `self, ref` | `` |  |
| `redact_doc` | `self, doc, ref` | `` |  |
| `_anonymize_data` | `self, email, anon, set_data, commit` | `` |  |
| `set_step_status` | `self, step, status` | `` |  |
| `__set_anonymization_data` | `self, email, anon` | `` |  |
| `__redact_partial_match_data` | `self, doctype` | `` |  |
| `put_on_hold` | `self` | `` |  |





## Functions

### `process_data_deletion_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `remove_unverified_record`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `confirm_deletion`
**Arguments:** `email, name, host_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_pattern`
**Arguments:** `full_match`
**Decorators:** ``

**Docstring:**
```

```

