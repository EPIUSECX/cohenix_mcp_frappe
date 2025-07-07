# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/google_calendar/google_calendar.py`

## Classes

### `RecurrenceParameters`
**Inherits:** `TypedDict`


**Docstring:**
```

```

**Methods:**
No methods found.

### `GoogleCalendar`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `get_access_token` | `self` | `` |  |





## Functions

### `authorize_access`
**Arguments:** `g_calendar, reauthorize`
**Decorators:** ``

**Docstring:**
```
If no Authorization code get it from Google and then request for Refresh Token.
Google Calendar Name is set to flags to set_value after Authorization Code is obtained.
```
### `get_authentication_url`
**Arguments:** `client_id, redirect_uri`
**Decorators:** ``

**Docstring:**
```

```
### `google_callback`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```
Authorization code is sent to callback as per the API configuration
```
### `sync`
**Arguments:** `g_calendar`
**Decorators:** ``

**Docstring:**
```

```
### `get_google_calendar_object`
**Arguments:** `g_calendar`
**Decorators:** ``

**Docstring:**
```
Return an object of Google Calendar along with Google Calendar doc.
```
### `check_google_calendar`
**Arguments:** `account, google_calendar`
**Decorators:** ``

**Docstring:**
```
Checks if Google Calendar is present with the specified name.
If not, creates one.
```
### `sync_events_from_google_calendar`
**Arguments:** `g_calendar, method`
**Decorators:** ``

**Docstring:**
```
Sync Events from Google Calendar in Framework Calendar.

Google Calendar returns nextSyncToken when all the events in Google Calendar are fetched.
nextSyncToken is returned at the very last page
https://developers.google.com/calendar/v3/sync
```
### `insert_event_to_calendar`
**Arguments:** `account, event, recurrence`
**Decorators:** ``

**Docstring:**
```
Inserts event in Frappe Calendar during Sync
```
### `update_participants_in_event`
**Arguments:** `calendar_event, google_event`
**Decorators:** ``

**Docstring:**
```

```
### `update_event_in_calendar`
**Arguments:** `account, event, recurrence`
**Decorators:** ``

**Docstring:**
```
Updates Event in Frappe Calendar if any existing Google Calendar Event is updated
```
### `insert_event_in_google_calendar`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Insert Events in Google Calendar if sync_with_google_calendar is checked.
```
### `update_event_in_google_calendar`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Updates Events in Google Calendar if any existing event is modified in Frappe Calendar
```
### `delete_event_from_google_calendar`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Delete Events from Google Calendar if Frappe Event is deleted.
```
### `parse_google_calendar_date`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `google_calendar_to_repeat_on`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
recurrence is in the form ['RRULE:FREQ=WEEKLY;BYDAY=MO,TU,TH']
has the frequency and then the days on which the event recurs

Both have been mapped in a dict for easier mapping.
```
### `format_date_according_to_google_calendar`
**Arguments:** `all_day, starts_on, ends_on`
**Decorators:** ``

**Docstring:**
```

```
### `parse_google_calendar_recurrence_rule`
**Arguments:** `repeat_day_week_number, repeat_day_name`
**Decorators:** ``

**Docstring:**
```
Return (repeat_on) exact date for combination eg 4TH viz. 4th thursday of a month.
```
### `repeat_on_to_google_calendar_recurrence_rule`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Return event (repeat_on) in Google Calendar format ie RRULE:FREQ=WEEKLY;BYDAY=MO,TU,TH.
```
### `get_week_number`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```
Return the week number of the month for the specified date.

https://stackoverflow.com/questions/3806473/python-week-number-of-the-month/16804556
```
### `get_recurrence_parameters`
**Arguments:** `recurrence`
**Decorators:** ``

**Docstring:**
```

```
### `get_conference_data`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_attendees`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Return a list of dicts with attendee emails, if available in event_participants table.
```

