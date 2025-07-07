# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/telephony/doctype/incoming_call_settings/incoming_call_settings.py`

## Classes

### `IncomingCallSettings`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` | List of validations
* Make sure that to time slot is ahead of from time slot in call schedule
* Make sure that no overlapping timeslots for a given day |
| `validate_call_schedule_timeslot` | `self, schedule` | `` | Make sure that to time slot is ahead of from time slot. |
| `validate_call_schedule_overlaps` | `self, schedule` | `` | Check if any time slots are overlapped in a day schedule. |
| `check_timeslots_overlap` | `ts1, ts2` | `staticmethod` |  |
| `time_to_seconds` | `time` | `staticmethod` | Convert time string of format HH:MM:SS into seconds |





## Functions

No top-level functions found in this file.
