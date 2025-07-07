# Python Module Analysis: `/workspace/cohenix-bench/apps/hrms/hrms/controllers/employee_reminders.py`

## Classes

No classes found in this file.


## Functions

### `send_reminders_in_advance_weekly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_reminders_in_advance_monthly`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `send_advance_holiday_reminders`
**Arguments:** `frequency`
**Decorators:** ``

**Docstring:**
```
Send Holiday Reminders in Advance to Employees
`frequency` (str): 'Weekly' or 'Monthly'
```
### `send_holidays_reminder_in_advance`
**Arguments:** `employee, holidays`
**Decorators:** ``

**Docstring:**
```

```
### `send_birthday_reminders`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Send Employee birthday reminders if no 'Stop Birthday Reminders' is not set.
```
### `get_birthday_reminder_text_and_message`
**Arguments:** `birthday_persons`
**Decorators:** ``

**Docstring:**
```

```
### `send_birthday_reminder`
**Arguments:** `recipients, reminder_text, birthday_persons, message, sender`
**Decorators:** ``

**Docstring:**
```

```
### `get_employees_who_are_born_today`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get all employee born today & group them based on their company
```
### `get_employees_having_an_event_today`
**Arguments:** `event_type`
**Decorators:** ``

**Docstring:**
```
Get all employee who have `event_type` today
& group them based on their company. `event_type`
can be `birthday` or `work_anniversary`
```
### `send_work_anniversary_reminders`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Send Employee Work Anniversary Reminders if 'Send Work Anniversary Reminders' is checked
```
### `get_work_anniversary_reminder_text`
**Arguments:** `anniversary_persons`
**Decorators:** ``

**Docstring:**
```

```
### `send_work_anniversary_reminder`
**Arguments:** `recipients, reminder_text, anniversary_persons, message, sender`
**Decorators:** ``

**Docstring:**
```

```
### `get_sender_email`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

