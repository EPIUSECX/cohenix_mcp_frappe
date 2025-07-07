# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/hr/doctype/interview/interview.py`

## Classes

### `DuplicateInterviewRoundError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `Interview`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `validate_duplicate_interview` | `self` | `` |  |
| `validate_designation` | `self` | `` |  |
| `show_job_applicant_update_dialog` | `self` | `` |  |
| `get_job_applicant_status` | `self` | `` |  |
| `reschedule_interview` | `self, scheduled_on, from_time, to_time` | `` |  |





## Functions

### `get_interviewers`
**Arguments:** `interview_round`
**Decorators:** ``

**Docstring:**
```

```
### `get_recipients`
**Arguments:** `name, for_feedback`
**Decorators:** ``

**Docstring:**
```

```
### `get_feedback`
**Arguments:** `interview`
**Decorators:** ``

**Docstring:**
```

```
### `get_skill_wise_average_rating`
**Arguments:** `interview`
**Decorators:** ``

**Docstring:**
```

```
### `update_job_applicant_status`
**Arguments:** `status, job_applicant`
**Decorators:** ``

**Docstring:**
```

```
### `send_interview_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_daily_feedback_reminder`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_expected_skill_set`
**Arguments:** `interview_round`
**Decorators:** ``

**Docstring:**
```

```
### `create_interview_feedback`
**Arguments:** `data, interview_name, interviewer, job_applicant`
**Decorators:** ``

**Docstring:**
```

```
### `get_interviewer_list`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `get_events`
**Arguments:** `start, end, filters`
**Decorators:** ``

**Docstring:**
```
Returns events for Gantt / Calendar view rendering.

:param start: Start date-time.
:param end: End date-time.
:param filters: Filters (JSON).
```

