# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/setup/doctype/transaction_deletion_record/transaction_deletion_record.py`

## Classes

### `TransactionDeletionRecord`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `validate_doctypes_to_be_ignored` | `self` | `` |  |
| `generate_job_name_for_task` | `self, task` | `` |  |
| `generate_job_name_for_next_tasks` | `self, task` | `` |  |
| `generate_job_name_for_all_tasks` | `self` | `` |  |
| `before_submit` | `self` | `` |  |
| `reset_task_flags` | `self` | `` |  |
| `before_save` | `self` | `` |  |
| `on_submit` | `self` | `` |  |
| `on_cancel` | `self` | `` |  |
| `enqueue_task` | `self, task` | `` |  |
| `execute_task` | `self, task_to_execute` | `` |  |
| `delete_notifications` | `self` | `` |  |
| `populate_doctypes_to_be_ignored_table` | `self` | `` |  |
| `validate_running_task_for_doc` | `self, job_names` | `` |  |
| `validate_doc_status` | `self` | `` |  |
| `start_deletion_tasks` | `self` | `` |  |
| `delete_bins` | `self` | `` |  |
| `delete_lead_addresses` | `self` | `` | Delete addresses to which leads are linked |
| `reset_company_values` | `self` | `` |  |
| `initialize_doctypes_to_be_deleted_table` | `self` | `` |  |
| `delete_company_transactions` | `self` | `` |  |
| `get_doctypes_to_be_ignored_list` | `self` | `` |  |
| `get_doctypes_with_company_field` | `self, doctypes_to_be_ignored_list` | `` |  |
| `get_all_child_doctypes` | `self` | `` |  |
| `get_number_of_docs_linked_with_specified_company` | `self, doctype, company_fieldname` | `` |  |
| `populate_doctypes_table` | `self, tables, doctype, fieldname, no_of_docs` | `` |  |
| `delete_child_tables` | `self, doctype, reference_doc_names` | `` |  |
| `delete_docs_linked_with_specified_company` | `self, doctype, reference_doc_names` | `` |  |
| `update_naming_series` | `self, naming_series, doctype_name` | `` |  |
| `delete_version_log` | `self, doctype, docnames` | `` |  |
| `delete_communications` | `self, doctype, reference_doc_names` | `` |  |
| `delete_comments` | `self, doctype, reference_doc_names` | `` |  |
| `unlink_attachments` | `self, doctype, reference_doc_names` | `` |  |





## Functions

### `get_doctypes_to_be_ignored`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_deletion_doc_running`
**Arguments:** `company, err_msg`
**Decorators:** ``

**Docstring:**
```

```
### `check_for_running_deletion_job`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```

```

