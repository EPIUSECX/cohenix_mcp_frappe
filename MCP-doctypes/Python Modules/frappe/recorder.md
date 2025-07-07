# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/recorder.py`

## Classes

### `RecorderConfig`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__post_init__` | `self` | `` |  |
| `store` | `self` | `` |  |
| `retrieve` | `cls` | `classmethod` |  |
| `delete` | `` | `staticmethod` |  |


### `Recorder`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, force` | `` |  |
| `register` | `self, data` | `` |  |
| `cleanup` | `self` | `` |  |
| `process_profiler` | `self` | `` |  |
| `dump` | `self` | `` |  |
| `_patch_sql` | `self, db` | `` |  |
| `_unpatch_sql` | `self` | `` |  |





## Functions

### `record_sql`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_current_stack_frames`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `post_process`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
post process all recorded values.

Any processing that can be done later should be done here to avoid overhead while
profiling. As of now following values are post-processed:
        - `EXPLAIN` output of queries.
        - SQLParse reformatting of queries
        - Mark duplicates
```
### `mark_duplicates`
**Arguments:** `request`
**Decorators:** ``

**Docstring:**
```

```
### `normalize_query`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```
Attempt to normalize query by removing variables.
This gives a different view of similar duplicate queries.

Example:
        These two are distinct queries:
                `select * from user where name = 'x'`
                `select * from user where name = 'z'`

        But their "normalized" form would be same:
                `select * from user where name = ?`
```
### `record`
**Arguments:** `force`
**Decorators:** ``

**Docstring:**
```

```
### `dump`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `do_not_record`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```

```
### `administrator_only`
**Arguments:** `function`
**Decorators:** ``

**Docstring:**
```

```
### `status`
**Arguments:** ``
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `start`
**Arguments:** `record_jobs, record_requests, record_sql, profile, capture_stack, explain, request_filter, jobs_filter`
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `stop`
**Arguments:** ``
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `get`
**Arguments:** `uuid`
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `export_data`
**Arguments:** ``
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `delete`
**Arguments:** ``
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```
### `record_queries`
**Arguments:** `func`
**Decorators:** ``

**Docstring:**
```
Decorator to profile a specific function using recorder.
```
### `import_data`
**Arguments:** `file`
**Decorators:** `do_not_record, administrator_only`

**Docstring:**
```

```

