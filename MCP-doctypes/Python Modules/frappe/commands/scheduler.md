# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/commands/scheduler.py`

## Classes

No classes found in this file.


## Functions

### `trigger_scheduler_event`
**Arguments:** `context, event`
**Decorators:** `pass_context`

**Docstring:**
```

```
### `enable_scheduler`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Enable scheduler
```
### `disable_scheduler`
**Arguments:** `context`
**Decorators:** `pass_context`

**Docstring:**
```
Disable scheduler
```
### `scheduler`
**Arguments:** `context, state, format, verbose, site`
**Decorators:** `pass_context`

**Docstring:**
```
Control scheduler state.
```
### `set_maintenance_mode`
**Arguments:** `context, state, site`
**Decorators:** `pass_context`

**Docstring:**
```
Put the site in maintenance mode for upgrades.
```
### `doctor`
**Arguments:** `context, site`
**Decorators:** `pass_context`

**Docstring:**
```
Get diagnostic info about background workers
```
### `show_pending_jobs`
**Arguments:** `context, site`
**Decorators:** `pass_context`

**Docstring:**
```
Get diagnostic info about background jobs
```
### `purge_jobs`
**Arguments:** `site, queue, event`
**Decorators:** ``

**Docstring:**
```
Purge any pending periodic tasks, if event option is not given, it will purge everything for the site
```
### `start_scheduler`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Start scheduler process which is responsible for enqueueing the scheduled job types.
```
### `start_worker`
**Arguments:** `queue, quiet, rq_username, rq_password, burst, strategy`
**Decorators:** ``

**Docstring:**
```
Start a background worker
```
### `start_worker_pool`
**Arguments:** `queue, quiet, num_workers, burst`
**Decorators:** ``

**Docstring:**
```
Start a pool of background workers
```
### `ready_for_migration`
**Arguments:** `context, site`
**Decorators:** `pass_context`

**Docstring:**
```

```

