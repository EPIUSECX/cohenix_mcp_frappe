# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/background_jobs.py`

## Classes

### `FrappeWorker`
**Inherits:** `Worker`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `work` | `self` | `` |  |
| `run_maintenance_tasks` | `self` | `` | Attempt to start a scheduler in case the worker doing scheduling died. |
| `start_frappe_scheduler` | `self` | `` |  |


### `FrappeWorkerNoFork`
**Inherits:** `FrappeWorker`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `work` | `self` | `` |  |
| `execute_job` | `self, job, queue` | `` | Execute job in same thread/process, do not fork() |
| `no_fork_exception_handler` | `self, job, exc_type, exc_value, traceback` | `` |  |
| `get_heartbeat_ttl` | `self, job` | `` |  |
| `kill_horse` | `self, sig` | `` |  |





## Functions

### `get_queues_timeout`
**Arguments:** ``
**Decorators:** `lru_cache`

**Docstring:**
```
Method returning a mapping of queue name to timeout for that queue

:return: Dictionary of queue name to timeout
```
### `enqueue`
**Arguments:** `method, queue, timeout, event, is_async, job_name, now, enqueue_after_commit`
**Decorators:** ``

**Docstring:**
```
Enqueue method to be executed using a background worker

:param method: method string or method object
:param queue: should be either long, default or short
:param timeout: should be set according to the functions
:param event: this is passed to enable clearing of jobs from queues
:param is_async: if is_async=False, the method is executed immediately, else via a worker
:param job_name: [DEPRECATED] can be used to name an enqueue call, which can be used to prevent
duplicate calls
:param now: if now=True, the method is executed via frappe.call()
:param enqueue_after_commit: if True, the job will be enqueued after the current transaction is
committed
:param on_success: Success callback
:param on_failure: Failure callback
:param at_front: Enqueue the job at the front of the queue or not
:param kwargs: keyword arguments to be passed to the method
:param deduplicate: do not re-queue job if it's already queued, requires job_id.
:param job_id: Assigning unique job id, which can be checked using `is_job_enqueued`
:param at_front_when_starved: If the queue appears to be starved then new jobs are
automatically inserted in LIFO fashion.
```
### `enqueue_doc`
**Arguments:** `doctype, name, method, queue, timeout, now`
**Decorators:** ``

**Docstring:**
```
Enqueue a method to be run on a document

:param doctype: DocType of the document on which you want to run the event
:param name: Name of the document on which you want to run the event
:param method: method string or method object
:param queue: (optional) should be either long, default or short
:param timeout: (optional) should be set according to the functions
:param kwargs: keyword arguments to be passed to the method
```
### `run_doc_method`
**Arguments:** `doctype, name, doc_method`
**Decorators:** ``

**Docstring:**
```

```
### `execute_job`
**Arguments:** `site, method, event, job_name, kwargs, user, is_async, retry`
**Decorators:** ``

**Docstring:**
```
Executes job in a worker, performs commit/rollback and logs if there is any error
```
### `start_worker`
**Arguments:** `queue, quiet, rq_username, rq_password, burst, strategy`
**Decorators:** ``

**Docstring:**
```
Wrapper to start rq worker. Connects to redis and monitors these queues.
```
### `start_worker_pool`
**Arguments:** `queue, num_workers, quiet, burst`
**Decorators:** ``

**Docstring:**
```
Start worker pool with specified number of workers.

WARNING: This feature is considered "EXPERIMENTAL".
```
### `get_worker_name`
**Arguments:** `queue`
**Decorators:** ``

**Docstring:**
```
When limiting worker to a specific queue, also append queue name to default worker name
```
### `get_jobs`
**Arguments:** `site, queue, key`
**Decorators:** ``

**Docstring:**
```
Gets jobs per queue or per site or both
```
### `get_queue_list`
**Arguments:** `queue_list, build_queue_name`
**Decorators:** ``

**Docstring:**
```
Defines possible queues. Also wraps a given queue in a list after validating.
```
### `get_workers`
**Arguments:** `queue`
**Decorators:** ``

**Docstring:**
```
Return a list of Worker objects tied to a queue object if queue is passed, else return a list of all workers.
```
### `get_running_jobs_in_queue`
**Arguments:** `queue`
**Decorators:** ``

**Docstring:**
```
Return a list of Jobs objects that are tied to a queue object and are currently running.
```
### `get_queue`
**Arguments:** `qtype, is_async`
**Decorators:** ``

**Docstring:**
```
Return a Queue object tied to a redis connection.

:param qtype: Queue type, should be either long, default or short
:param is_async: Whether the job should be executed asynchronously or in the same process
:return: Queue object
```
### `validate_queue`
**Arguments:** `queue, default_queue_list`
**Decorators:** ``

**Docstring:**
```
Validates if the queue is in the list of default queues.

:param queue: The queue to be validated
:param default_queue_list: Optionally, a custom list of queues to validate against
:return:
```
### `get_redis_conn`
**Arguments:** `username, password`
**Decorators:** ``

**Docstring:**
```

```
### `get_redis_connection_without_auth`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_queues`
**Arguments:** `connection`
**Decorators:** ``

**Docstring:**
```
Get all the queues linked to the current bench.
```
### `generate_qname`
**Arguments:** `qtype`
**Decorators:** ``

**Docstring:**
```
Generate qname by combining bench ID and queue type.

qnames are useful to define namespaces of customers.
```
### `is_queue_accessible`
**Arguments:** `qobj`
**Decorators:** ``

**Docstring:**
```
Checks whether queue is relate to current bench or not.
```
### `enqueue_test_job`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `test_job`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```

```
### `create_job_id`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```
Generate unique job id for deduplication

:param job_id: Optional job id, if not provided, a UUID is generated for it
:return: Unique job id, namespaced by site
```
### `is_job_enqueued`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```

```
### `get_job_status`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```
Get RQ job status, returns None if job is not found.
```
### `get_job`
**Arguments:** `job_id`
**Decorators:** ``

**Docstring:**
```

```
### `set_niceness`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Background processes should have slightly lower priority than web processes.

Calling this function increments the niceness of process by configured value or default.
Note: This function should be called only once in process' lifetime.
```
### `truncate_failed_registry`
**Arguments:** `job, connection, type, value, traceback`
**Decorators:** ``

**Docstring:**
```
Ensures that number of failed jobs don't exceed specified limits.
```
### `_check_queue_size`
**Arguments:** `q`
**Decorators:** ``

**Docstring:**
```

```
### `_site_count`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_start_sentry`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```

