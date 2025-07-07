# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/scheduler.py`

## Classes

No classes found in this file.


## Functions

### `cprint`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Prints only if called from STDOUT
```
### `start_scheduler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Run enqueue_events_for_all_sites based on scheduler tick.
Specify scheduler_tick_interval in seconds in common_site_config.json
```
### `_get_scheduler_lock_file`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_schduler_process_running`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Checks if any other process is holding the lock.

Note: FLOCK is held by process until it exits, this function just checks if process is
running or not. We can't determine if process is stuck somehwere.
```
### `sleep_duration`
**Arguments:** `tick`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_events_for_all_sites`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Loop through sites and enqueue events that are not already queued
```
### `enqueue_events_for_site`
**Arguments:** `site`
**Decorators:** ``

**Docstring:**
```

```
### `enqueue_events`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_scheduler_inactive`
**Arguments:** `verbose`
**Decorators:** ``

**Docstring:**
```

```
### `is_scheduler_disabled`
**Arguments:** `verbose`
**Decorators:** ``

**Docstring:**
```

```
### `toggle_scheduler`
**Arguments:** `enable`
**Decorators:** ``

**Docstring:**
```

```
### `enable_scheduler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `disable_scheduler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `schedule_jobs_based_on_activity`
**Arguments:** `check_time`
**Decorators:** ``

**Docstring:**
```
Return True for active sites as defined by `Activity Log`.
Also return True for inactive sites once every 24 hours based on `Scheduled Job Log`.
```
### `is_dormant`
**Arguments:** `check_time`
**Decorators:** ``

**Docstring:**
```

```
### `_get_last_creation_timestamp`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```

```
### `activate_scheduler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_scheduler_status`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_scheduler_tick`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

