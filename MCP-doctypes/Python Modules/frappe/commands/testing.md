# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/commands/testing.py`

## Classes

No classes found in this file.


## Functions

### `main`
**Arguments:** `site, app, module, doctype, module_def, verbose, tests, force, profile, junit_xml_output, doctype_list_path, failfast, case, skip_before_tests, debug, debug_exceptions, selected_categories, lightmode`
**Decorators:** ``

**Docstring:**
```
Main function to run tests
```
### `run_tests_in_light_mode`
**Arguments:** `test_params`
**Decorators:** ``

**Docstring:**
```

```
### `_setup_xml_output`
**Arguments:** `junit_xml_output`
**Decorators:** ``

**Docstring:**
```
Setup XML output for test results if specified
```
### `_load_doctype_list`
**Arguments:** `doctype_list_path`
**Decorators:** ``

**Docstring:**
```
Load the list of doctypes from the specified file
```
### `_run_module_def_tests`
**Arguments:** `app, module_def, runner, force`
**Decorators:** ``

**Docstring:**
```
Run tests for the specified module definition
```
### `_get_doctypes_for_module_def`
**Arguments:** `app, module_def`
**Decorators:** ``

**Docstring:**
```
Get the list of doctypes for the specified module definition
```
### `run_tests`
**Arguments:** `context, app, module, doctype, module_def, test, profile, coverage, junit_xml_output, doctype_list_path, skip_test_records, skip_before_tests, failfast, case, test_category, lightmode, debug`
**Decorators:** `pass_context`

**Docstring:**
```
Run python unit-tests
```
### `run_parallel_tests`
**Arguments:** `context, app, build_number, total_builds, with_coverage, use_orchestrator, dry_run, lightmode`
**Decorators:** `pass_context`

**Docstring:**
```

```
### `run_ui_tests`
**Arguments:** `context, app, headless, parallel, with_coverage, browser, ci_build_id, cypressargs`
**Decorators:** `pass_context`

**Docstring:**
```
Run UI tests
```

