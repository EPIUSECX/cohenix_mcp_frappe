# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/tests/test_utils.py`

## Classes

### `Capturing`
**Inherits:** `list`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__enter__` | `self` | `` |  |
| `__exit__` | `self` | `` |  |


### `TestFilters`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_simple_dict` | `self` | `` |  |
| `test_multiple_dict` | `self` | `` |  |
| `test_list_filters` | `self` | `` |  |
| `test_list_filters_as_list` | `self` | `` |  |
| `test_lt_gt` | `self` | `` |  |
| `test_date_time` | `self` | `` |  |
| `test_filter_evaluation` | `self` | `` |  |
| `test_timespan` | `self` | `` |  |


### `TestMoney`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_money_in_words` | `self` | `` |  |
| `test_money_in_words_without_fraction` | `self` | `` |  |


### `TestDataManipulation`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_scrub_urls` | `self` | `` |  |


### `TestFieldCasting`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_str_types` | `self` | `` |  |
| `test_float_types` | `self` | `` |  |
| `test_int_types` | `self` | `` |  |
| `test_datetime_types` | `self` | `` |  |
| `test_date_types` | `self` | `` |  |
| `test_time_types` | `self` | `` |  |


### `TestMathUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_floor` | `self` | `` |  |
| `test_ceil` | `self` | `` |  |


### `TestHTMLUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_clean_email_html` | `self` | `` |  |
| `test_sanitize_html` | `self` | `` |  |


### `TestValidationUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_valid_url` | `self` | `` |  |
| `test_valid_email` | `self` | `` |  |
| `test_valid_phone` | `self` | `` |  |
| `test_validate_name` | `self` | `` |  |


### `TestImage`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_strip_exif_data` | `self` | `` |  |
| `test_optimize_image` | `self` | `` |  |


### `TestPythonExpressions`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_validation_for_good_python_expression` | `self` | `` |  |
| `test_validation_for_bad_python_expression` | `self` | `` |  |


### `TestDiffUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `setUpClass` | `cls` | `classmethod` |  |
| `tearDownClass` | `cls` | `classmethod` |  |
| `test_version_query` | `self` | `` |  |
| `test_get_field_value_from_version` | `self` | `` |  |
| `test_get_version_diff` | `self` | `` |  |


### `TestDateUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_first_day_of_week` | `self` | `` |  |
| `test_last_day_of_week` | `self` | `` |  |
| `test_is_last_day_of_the_month` | `self` | `` |  |
| `test_get_time` | `self` | `` |  |
| `test_get_timedelta` | `self` | `` |  |
| `test_to_timedelta` | `self` | `` |  |
| `test_add_date_utils` | `self` | `` |  |
| `test_duration_to_sec` | `self` | `` |  |
| `test_get_timespan_date_range` | `self` | `` |  |
| `test_timesmap_utils` | `self` | `` |  |
| `test_get_datetime` | `self, original` | `` |  |
| `test_get_datetime_tz_aware` | `self, original` | `` |  |
| `test_pretty_date` | `self` | `` |  |
| `test_date_from_timegrain` | `self` | `` |  |


### `TestResponse`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_json_handler` | `self` | `` |  |


### `TestTimeDeltaUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_format_timedelta` | `self` | `` |  |
| `test_parse_timedelta` | `self` | `` |  |


### `TestXlsxUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_unescape` | `self` | `` |  |


### `TestLinkTitle`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_link_title_doctypes_in_boot_info` | `self` | `` | Test that doctypes are added to link_title_map in boot_info |
| `test_link_titles_on_getdoc` | `self` | `` | Test that link titles are added to the doctype on getdoc |


### `TestAppParser`
**Inherits:** `MockedRequestTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_app_name_parser` | `self` | `` |  |


### `TestIntrospectionMagic`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```
Test utils that inspect live objects
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_newargs` | `self` | `` |  |
| `test_strip_off_kwargs_when_not_supported` | `self` | `` |  |


### `TestMakeRandom`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_random` | `self` | `` |  |
| `test_can_make` | `self` | `` |  |
| `test_how_many` | `self` | `` |  |


### `TestLazyLoader`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_lazy_import_module` | `self` | `` |  |


### `TestIdenticon`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_gravatar` | `self` | `` |  |
| `test_generate_identicon` | `self` | `` |  |


### `TestContainerUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_dict_to_str` | `self` | `` |  |
| `test_remove_blanks` | `self` | `` |  |


### `TestLocks`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_locktimeout` | `self` | `` |  |
| `test_global_lock` | `self` | `` |  |


### `TestMiscUtils`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_file_timestamp` | `self` | `` |  |
| `test_execute_in_shell` | `self` | `` |  |
| `test_get_all_sites` | `self` | `` |  |
| `test_get_site_info` | `self` | `` |  |
| `test_get_url_to_form` | `self` | `` |  |
| `test_safe_json_load` | `self` | `` |  |
| `test_url_expansion` | `self` | `` |  |


### `TestTypingValidations`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_validate_whitelisted_api` | `self` | `` |  |
| `test_validate_whitelisted_doc_method` | `self` | `` |  |


### `TestTBSanitization`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_traceback_sanitzation` | `self` | `` |  |


### `TestRounding`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_normal_rounding` | `self` | `` |  |
| `test_normal_rounding_as_argument` | `self` | `` |  |
| `test_normal_rounding_property` | `self, number, precision` | `` |  |
| `test_bankers_rounding` | `self` | `` |  |
| `test_bankers_rounding_property` | `self, number, precision` | `` |  |
| `test_default_rounding` | `self` | `` |  |
| `test_cint` | `self, floating_point, integer` | `` |  |


### `TestArgumentTypingValidations`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_validate_argument_types` | `self` | `` |  |


### `TestChangeLog`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_get_remote_url` | `self` | `` |  |
| `test_parse_github_url` | `self` | `` |  |


### `TestCrypto`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_hashing` | `self` | `` |  |


### `TestURLTrackers`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_add_trackers_to_url` | `self` | `` |  |
| `test_parse_and_map_trackers_from_url` | `self` | `` |  |
| `test_map_trackers` | `self` | `` |  |





## Functions

No top-level functions found in this file.
