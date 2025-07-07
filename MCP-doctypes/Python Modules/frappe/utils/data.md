# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/utils/data.py`

## Classes

### `Weekday`
**Inherits:** `Enum`


**Docstring:**
```

```

**Methods:**
No methods found.

### `_UserInfo`


**Docstring:**
```

```

**Methods:**
No methods found.

### `UnicodeWithAttrs`
**Inherits:** `str`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, text` | `` |  |





## Functions

### `get_start_of_week_index`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_invalid_date_string`
**Arguments:** `date_string`
**Decorators:** ``

**Docstring:**
```
Return True if the date string is invalid or None or empty.
```
### `getdate`
**Arguments:** `string_date, parse_day_first`
**Decorators:** ``

**Docstring:**
```
Convert string date (yyyy-mm-dd) to datetime.date object.
If no input is provided, current date is returned.
```
### `get_datetime`
**Arguments:** `datetime_str`
**Decorators:** ``

**Docstring:**
```
Return the below mentioned values based on the given `datetime_str`:

* If `datetime_str` is None, returns datetime object of current datetime
* If `datetime_str` is already a datetime object, returns the same
* If `datetime_str` is a timedelta object, returns the same
* If `datetime_str` is a list or tuple, returns a datetime object
* If `datetime_str` is a date object, returns a datetime object
* If `datetime_str` is a valid date string, returns a datetime object for the same
* If `datetime_str` is an invalid date string, returns None
```
### `get_timedelta`
**Arguments:** `time`
**Decorators:** ``

**Docstring:**
```
Return `datetime.timedelta` object from string value of a valid time format.

Return None if `time` is not a valid format.

Args:
        time (str | datetime.timedelta): A valid time representation. This string is parsed
        using `dateutil.parser.parse`. Examples of valid inputs are:
        '0:0:0', '17:21:00', '2012-01-19 17:21:00'. Checkout
        https://dateutil.readthedocs.io/en/stable/parser.html#dateutil.parser.parse

Return:
        datetime.timedelta: Timedelta object equivalent of the passed `time` string
```
### `to_timedelta`
**Arguments:** `time_str`
**Decorators:** ``

**Docstring:**
```
Return a `datetime.timedelta` object from the given string or `datetime.time` object.
If the given argument is not a string or a `datetime.time` object, it is returned as is.
```
### `add_to_date`
**Arguments:** `date, years, months, weeks, days, hours, minutes, seconds, as_string, as_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `add_to_date`
**Arguments:** `date, years, months, weeks, days, hours, minutes, seconds, as_string, as_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `add_to_date`
**Arguments:** `date, years, months, weeks, days, hours, minutes, seconds, as_string, as_datetime`
**Decorators:** ``

**Docstring:**
```

```
### `add_to_date`
**Arguments:** `date, years, months, weeks, days, hours, minutes, seconds, as_string, as_datetime`
**Decorators:** ``

**Docstring:**
```
Adds `days` to the given date
```
### `add_days`
**Arguments:** `date, days`
**Decorators:** ``

**Docstring:**
```
Return a new date after adding the given number of `days` to the given `date`.
```
### `add_months`
**Arguments:** `date, months`
**Decorators:** ``

**Docstring:**
```
Return a new date after adding the given number of `months` to the given `date`.
```
### `add_years`
**Arguments:** `date, years`
**Decorators:** ``

**Docstring:**
```
Return a new date after adding the given number of `years` to the given `date`.
```
### `date_diff`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in days.
```
### `days_diff`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in days.
```
### `month_diff`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in months.
```
### `time_diff`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates as `datetime.timedelta` object.
```
### `time_diff_in_seconds`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in seconds.
```
### `time_diff_in_hours`
**Arguments:** `string_ed_date, string_st_date`
**Decorators:** ``

**Docstring:**
```
Return the difference between given two dates in hours.
```
### `now_datetime`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the current datetime in system timezone.
```
### `get_timestamp`
**Arguments:** `date`
**Decorators:** ``

**Docstring:**
```
Return the Unix timestamp (seconds since Epoch) for the given `date`.
If `date` is None, the current timestamp is returned.
```
### `get_eta`
**Arguments:** `from_time, percent_complete`
**Decorators:** ``

**Docstring:**
```

```
### `get_system_timezone`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the system timezone.
```
### `convert_utc_to_timezone`
**Arguments:** `utc_timestamp, time_zone`
**Decorators:** ``

**Docstring:**
```

```
### `get_datetime_in_timezone`
**Arguments:** `time_zone`
**Decorators:** ``

**Docstring:**
```
Return the current datetime in the given timezone (e.g. 'Asia/Kolkata').
```
### `convert_utc_to_system_timezone`
**Arguments:** `utc_timestamp`
**Decorators:** ``

**Docstring:**
```
Return the given UTC `datetime` timestamp in system timezone.
```
### `now`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return current datetime as `yyyy-mm-dd hh:mm:ss`.
```
### `nowdate`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return current date as `yyyy-mm-dd`.
```
### `today`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return today's date in `yyyy-mm-dd` format.
```
### `get_abbr`
**Arguments:** `string, max_len`
**Decorators:** ``

**Docstring:**
```
Return the abbreviation of the given string.

Examples:

* "John Doe" => "JD"
* "Jenny Jane Doe" => "JJ" (default, `max_len` = 2)
* "Jenny Jane Doe" => "JJD" (`max_len` = 3)

Return "?" if the given string is empty.
```
### `nowtime`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return current time (system timezone) in `hh:mm:ss` format.
```
### `get_first_day`
**Arguments:** `dt, d_years, d_months, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_first_day`
**Arguments:** `dt, d_years, d_months, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_first_day`
**Arguments:** `dt, d_years, d_months, as_str`
**Decorators:** ``

**Docstring:**
```
Return the first day of the month for the date specified by date object.

Also, add `d_years` and `d_months` if specified.
```
### `get_quarter_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_quarter_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_quarter_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```
Return the start date of the quarter for the given datetime like object (`dt`).

If `dt` is None, the current quarter start date is returned.
```
### `get_first_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_first_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_first_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```
Return the first day of the week (as per System Settings or Sunday by default) for the given datetime like object (`dt`).

If `as_str` is True, the first day of the week is returned as a string in `yyyy-mm-dd` format.
```
### `get_week_start_offset_days`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `get_normalized_weekday_index`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `get_year_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_year_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_year_start`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```
Return the start date of the year for the given date (`dt`).
```
### `get_last_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_last_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_last_day_of_week`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```
Return the last day of the week (first day is taken from System Settings or Sunday by default) for the given datetime like object (`dt`).

If `as_str` is True, the last day of the week is returned as a string in `yyyy-mm-dd` format.
```
### `get_last_day`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```
Return last day of the month using:

`get_first_day(dt, 0, 1) + datetime.timedelta(-1)`
```
### `is_last_day_of_the_month`
**Arguments:** `dt`
**Decorators:** ``

**Docstring:**
```

```
### `get_quarter_ending`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_quarter_ending`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_quarter_ending`
**Arguments:** `date, as_str`
**Decorators:** ``

**Docstring:**
```
Return the end date of the quarter for the given datetime like object (`date`).

If `date` is None, the current quarter end date is returned.
If `as_str` is True, the end date of the quarter is returned as a string in `yyyy-mm-dd` format.
```
### `get_year_ending`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_year_ending`
**Arguments:** `dt, as_str`
**Decorators:** ``

**Docstring:**
```

```
### `get_year_ending`
**Arguments:** `date, as_str`
**Decorators:** ``

**Docstring:**
```
Return the end date of the year for the given datetime like object (`date`).

If `date` is None, the current year end date is returned.
If `as_str` is True, the end date of the year is returned as a string in `yyyy-mm-dd` format.
```
### `get_time`
**Arguments:** `time_str`
**Decorators:** ``

**Docstring:**
```
Return a `datetime.time` object for the given `time_str`.

If the given argument is already a `datetime.time` object, it is returned as is.
```
### `get_datetime_str`
**Arguments:** `datetime_obj`
**Decorators:** ``

**Docstring:**
```
Return the given datetime like object (datetime.date, datetime.datetime, string) as a string in `yyyy-mm-dd hh:mm:ss` format.
```
### `get_date_str`
**Arguments:** `date_obj`
**Decorators:** ``

**Docstring:**
```
Return the given datetime like object (datetime.date, datetime.datetime, string) as a string in `yyyy-mm-dd` format.
```
### `get_time_str`
**Arguments:** `timedelta_obj`
**Decorators:** ``

**Docstring:**
```
Return the given timedelta object as a string in `hh:mm:ss` format.
```
### `get_user_date_format`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get the current user date format. The result will be cached.
```
### `get_user_time_format`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get the current user time format. The result will be cached.
```
### `format_date`
**Arguments:** `string_date, format_string, parse_day_first`
**Decorators:** ``

**Docstring:**
```
Convert the given string date to :data:`user_date_format`.

User format specified in defaults

Examples:

* dd-mm-yyyy
* mm-dd-yyyy
* dd/mm/yyyy
```
### `format_time`
**Arguments:** `time_string, format_string`
**Decorators:** ``

**Docstring:**
```
Convert the given string time to :data:`user_time_format`.

User format specified in defaults

Examples:

* HH:mm:ss
* HH:mm
```
### `format_datetime`
**Arguments:** `datetime_string, format_string`
**Decorators:** ``

**Docstring:**
```
Convert the given string time to :data:`user_datetime_format`
User format specified in defaults

Examples:

* dd-mm-yyyy HH:mm:ss
* mm-dd-yyyy HH:mm
```
### `format_duration`
**Arguments:** `seconds, hide_days`
**Decorators:** ``

**Docstring:**
```
Convert the given duration value in float(seconds) to duration format.

example: convert 12885 to '3h 34m 45s' where 12885 = seconds in float
```
### `duration_to_seconds`
**Arguments:** `duration`
**Decorators:** ``

**Docstring:**
```
Convert the given duration formatted value to duration value in seconds.

example: convert '3h 34m 45s' to 12885 (value in seconds)
```
### `validate_duration_format`
**Arguments:** `duration`
**Decorators:** ``

**Docstring:**
```

```
### `get_weekdays`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return a list of weekday names.

Return value: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
```
### `get_weekday`
**Arguments:** `datetime`
**Decorators:** ``

**Docstring:**
```
Return the weekday name (e.g. 'Sunday') for the given datetime like object (datetime.date, datetime.datetime, string).

If `datetime` argument is not provided, the current weekday name is returned.
```
### `get_month`
**Arguments:** `datetime`
**Decorators:** ``

**Docstring:**
```
Return the month name (e.g. 'January') for the given datetime like object (datetime.date, datetime.datetime, string).

If `datetime` argument is not provided, the current month name is returned.
```
### `get_timespan_date_range`
**Arguments:** `timespan`
**Decorators:** ``

**Docstring:**
```
Return the date range (start_date, end_date) tuple for the given timespan.
```
### `global_date_format`
**Arguments:** `date, format`
**Decorators:** ``

**Docstring:**
```
Return localized date in the form of 'January 1, 2012'.
```
### `has_common`
**Arguments:** `l1, l2`
**Decorators:** ``

**Docstring:**
```
Return truthy value if there are common elements in lists l1 and l2.
```
### `cast_fieldtype`
**Arguments:** `fieldtype, value, show_warning`
**Decorators:** ``

**Docstring:**
```

```
### `cast`
**Arguments:** `fieldtype, value`
**Decorators:** ``

**Docstring:**
```
Cast the value to the Python native object of the Frappe fieldtype provided.
If value is None, the first/lowest value of the `fieldtype` will be returned.
If value can't be cast as fieldtype due to an invalid input, None will be returned.

Mapping of Python types => Frappe types:
        * str => ("Data", "Text", "Small Text", "Long Text", "Text Editor", "Select", "Link", "Dynamic Link")
        * float => ("Currency", "Float", "Percent")
        * int => ("Int", "Check")
        * datetime.datetime => ("Datetime",)
        * datetime.date => ("Date",)
        * datetime.time => ("Time",)
```
### `flt`
**Arguments:** `s, precision`
**Decorators:** ``

**Docstring:**
```

```
### `flt`
**Arguments:** `s, precision`
**Decorators:** ``

**Docstring:**
```

```
### `flt`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```

```
### `flt`
**Arguments:** `s, precision, rounding_method`
**Decorators:** ``

**Docstring:**
```
Convert to float (ignoring commas in string).

:param s: Number in string or other numeric format.
:param precision: optional argument to specify precision for rounding.
:returns: Converted number in python float type.

Return 0 if input can not be converted to float.

Examples:

>>> flt("43.5", precision=0)
44
>>> flt("42.5", precision=0)
42
>>> flt("10,500.5666", precision=2)
10500.57
>>> flt("a")
0.0
>>> flt(None)
0.0
```
### `cint`
**Arguments:** `s, default`
**Decorators:** ``

**Docstring:**
```
Convert to integer.

:param s: Number in string or other numeric format.
:returns: Converted number in python integer type.

Return default if input cannot be converted to integer.

Examples:
>>> cint("100")
100
>>> cint("a")
0
>>> cint(None)
0
```
### `floor`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```
Return a number representing the largest integer less than or equal to the specified number.
```
### `ceil`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```
Return the smallest integer greater than or equal to the given number.
```
### `cstr`
**Arguments:** `s, encoding`
**Decorators:** ``

**Docstring:**
```
Convert the given argument to string.
```
### `sbool`
**Arguments:** `x`
**Decorators:** ``

**Docstring:**
```
Convert str object to Boolean if possible.

Example:
        "true" becomes True
        "1" becomes True
        "{}" remains "{}"

Args:
        x (str): String to be converted to Bool

Return Boolean or x.
```
### `rounded`
**Arguments:** `num, precision, rounding_method`
**Decorators:** ``

**Docstring:**
```
Round according to method set in system setting, defaults to banker's rounding
```
### `_bankers_rounding_legacy`
**Arguments:** `num, precision`
**Decorators:** ``

**Docstring:**
```

```
### `_round_away_from_zero`
**Arguments:** `num, precision`
**Decorators:** ``

**Docstring:**
```

```
### `_bankers_rounding`
**Arguments:** `num, precision`
**Decorators:** ``

**Docstring:**
```

```
### `remainder`
**Arguments:** `numerator, denominator, precision`
**Decorators:** ``

**Docstring:**
```
Return the remainder of the division of `numerator` by `denominator`.
```
### `safe_div`
**Arguments:** `numerator, denominator, precision`
**Decorators:** ``

**Docstring:**
```
SafeMath division that returns zero when divided by zero.
```
### `round_based_on_smallest_currency_fraction`
**Arguments:** `value, currency, precision`
**Decorators:** ``

**Docstring:**
```

```
### `encode`
**Arguments:** `obj, encoding`
**Decorators:** ``

**Docstring:**
```

```
### `parse_val`
**Arguments:** `v`
**Decorators:** ``

**Docstring:**
```
Convert to simple datatypes from SQL query results.
```
### `fmt_money`
**Arguments:** `amount, precision, currency, format`
**Decorators:** ``

**Docstring:**
```
Convert to string with commas for thousands, millions etc.
```
### `__getattr__`
**Arguments:** `name`
**Decorators:** ``

**Docstring:**
```

```
### `money_in_words`
**Arguments:** `number, main_currency, fraction_currency`
**Decorators:** ``

**Docstring:**
```
Return string in words with currency and fraction currency.
```
### `in_words`
**Arguments:** `integer, in_million`
**Decorators:** ``

**Docstring:**
```
Return string in words for the given integer.
```
### `is_html`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```
Return True if the given `text` contains any HTML tags.
```
### `is_image`
**Arguments:** `filepath`
**Decorators:** ``

**Docstring:**
```
Return True if the given `filepath` points to an image file.
```
### `get_thumbnail_base64_for_image`
**Arguments:** `src`
**Decorators:** ``

**Docstring:**
```
Return the base64 encoded string for the thumbnail of the given image source path.

Example return value:

{
        "base64": "data:image/ext;base64,...",
        "width": 50,
        "height": 50
}
```
### `image_to_base64`
**Arguments:** `image, extn`
**Decorators:** ``

**Docstring:**
```
Return the base64 encoded string for the given PIL `ImageFile`.
```
### `pdf_to_base64`
**Arguments:** `filename`
**Decorators:** ``

**Docstring:**
```
Return the base64 encoded string for the given PDF file.

Return None if the file is not found or is not a PDF file.
```
### `strip_html`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```
Remove anything enclosed in and including <>.
```
### `escape_html`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```
Return the given text with HTML special characters escaped.

e.g. '<h1>Hello</h1>' -> '&lt;h1&gt;Hello&lt;/h1&gt;'
```
### `pretty_date`
**Arguments:** `iso_datetime, mini`
**Decorators:** ``

**Docstring:**
```
Return a localized string representation of the delta to the current system time.

For example, "1 hour ago", "2 days ago", "in 5 seconds", etc.
```
### `comma_or`
**Arguments:** `some_list, add_quotes`
**Decorators:** ``

**Docstring:**
```
Return the given list or tuple as a comma separated string with the last item joined by 'or'.
e.g. ['a', 'b', 'c'] -> 'a, b or c'

If `add_quotes` is True, each item in the list will be wrapped in single quotes.
e.g. ['a', 'b', 'c'] -> "'a', 'b' or 'c'"
```
### `comma_and`
**Arguments:** `some_list, add_quotes`
**Decorators:** ``

**Docstring:**
```
Return the given list or tuple as a comma separated string with the last item joined by 'and'.
e.g. ['a', 'b', 'c'] -> 'a, b and c'

If `add_quotes` is True, each item in the list will be wrapped in single quotes.
e.g. ['a', 'b', 'c'] -> "'a', 'b' and 'c'"
```
### `comma_sep`
**Arguments:** `some_list, pattern, add_quotes`
**Decorators:** ``

**Docstring:**
```
Return the given list or tuple as a comma separated string, with the last item joined by the given string format pattern.

If `add_quotes` is True, each item in the list will be wrapped in single quotes.

e.g. if `some_list` is ['a', 'b', 'c'] and `pattern` is '{0} or {1}', the output will be 'a, b or c'
```
### `new_line_sep`
**Arguments:** `some_list`
**Decorators:** ``

**Docstring:**
```
Return the given list or tuple as a new line separated string.

       e.g. ['', 'Paid', 'Unpaid'] -> '
Paid
Unpaid'
       
```
### `filter_strip_join`
**Arguments:** `some_list, sep`
**Decorators:** ``

**Docstring:**
```
given a list, filter None values, strip spaces and join
```
### `get_url`
**Arguments:** `uri, full_address, allow_header_override`
**Decorators:** ``

**Docstring:**
```
Get app url from request.
```
### `get_host_name_from_request`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the hostname (`request.host`) from the request headers.
```
### `url_contains_port`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Return True if the given url contains a port number.

e.g. 'http://localhost:8000' -> True, 'http://localhost' -> False.
```
### `get_host_name`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Return the hostname of the current site.

e.g. If site is 'https://cloud.frappe.io', returns 'cloud.frappe.io'.
```
### `get_link_to_form`
**Arguments:** `doctype, name, label`
**Decorators:** ``

**Docstring:**
```
Return the HTML link to the given document's form view.

e.g. get_link_to_form("Sales Invoice", "INV-0001", "Link Label") returns:
    '<a href="https://frappe.io/app/sales-invoice/INV-0001">Link Label</a>'.
```
### `get_link_to_report`
**Arguments:** `name, label, report_type, doctype, filters`
**Decorators:** ``

**Docstring:**
```
Return the HTML link to the given report.

e.g. get_link_to_report("Revenue Report", "Link Label") returns:
        '<a href="https://frappe.io/app/query-report/Revenue%20Report">Link Label</a>'.
```
### `get_absolute_url`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Return the absolute route for the form view of the given document in the desk.

e.g. when doctype="Sales Invoice" and name="INV-00001", returns '/app/sales-invoice/INV-00001'
```
### `get_url_to_form`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Return the absolute URL for the form view of the given document in the desk.

e.g. when doctype="Sales Invoice" and your site URL is "https://frappe.io",
         returns 'https://frappe.io/app/sales-invoice/INV-00001'
```
### `get_url_to_list`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
Return the absolute URL for the list view of the given document in the desk.

e.g. when doctype="Sales Invoice" and your site URL is "https://frappe.io",
         returns 'https://frappe.io/app/sales-invoice'
```
### `get_url_to_report`
**Arguments:** `name, report_type, doctype`
**Decorators:** ``

**Docstring:**
```
Return the absolute URL for the report in the desk.

e.g. when name="Sales Register" and your site URL is "https://frappe.io",
         returns 'https://frappe.io/app/query-report/Sales%20Register'

You can optionally pass `report_type` and `doctype` to get the URL for a Report Builder report.

get_url_to_report("Revenue", "Report Builder", "Sales Invoice") -> 'https://frappe.io/app/sales-invoice/view/report/Revenue'
```
### `get_url_to_report_with_filters`
**Arguments:** `name, filters, report_type, doctype`
**Decorators:** ``

**Docstring:**
```
Return the absolute URL for the report in the desk with filters.
```
### `sql_like`
**Arguments:** `value, pattern`
**Decorators:** ``

**Docstring:**
```

```
### `filter_operator_is`
**Arguments:** `value, pattern`
**Decorators:** ``

**Docstring:**
```
Operator `is` can have two values: 'set' or 'not set'.
```
### `filter_operator_timespan`
**Arguments:** `value, pattern`
**Decorators:** ``

**Docstring:**
```

```
### `evaluate_filters`
**Arguments:** `doc, filters`
**Decorators:** ``

**Docstring:**
```
Return True if doc matches filters.
```
### `compare`
**Arguments:** `val1, condition, val2, fieldtype`
**Decorators:** ``

**Docstring:**
```

```
### `get_filter`
**Arguments:** `doctype, filters, filters_config`
**Decorators:** ``

**Docstring:**
```
Return a `_dict` like:

{
        "doctype": ...
        "fieldname": ...
        "operator": ...
        "value": ...
        "fieldtype": ...
}
```
### `make_filter_tuple`
**Arguments:** `doctype, key, value`
**Decorators:** ``

**Docstring:**
```
return a filter tuple like [doctype, key, operator, value]
```
### `make_filter_dict`
**Arguments:** `filters`
**Decorators:** ``

**Docstring:**
```
convert this [[doctype, key, operator, value], ..]
to this { key: (operator, value), .. }
```
### `sanitize_column`
**Arguments:** `column_name`
**Decorators:** ``

**Docstring:**
```

```
### `_sanitize_column`
**Arguments:** `column_name, db_type`
**Decorators:** ``

**Docstring:**
```

```
### `scrub_urls`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```
Expand relative urls in the given `html`.

e.g. If HTML is '<a href="/files/abc.jpeg">View Image</a>' and site URL is 'https://frappe.io',
        returns '<a href="https://frappe.io/files/abc.jpeg">View Image</a>'.
```
### `expand_relative_urls`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```
Expand relative urls in the given `html`.

e.g. If HTML is '<a href="/files/abc.jpeg">View Image</a>' and site URL is 'https://frappe.io',
        returns '<a href="https://frappe.io/files/abc.jpeg">View Image</a>'.
```
### `quoted`
**Arguments:** `url`
**Decorators:** ``

**Docstring:**
```
Return the given `url` quoted.

e.g. 'https://frappe.io/files/my Image file.jpeg' -> 'https://frappe.io/files/my%20Image%20file.jpeg'
```
### `quote_urls`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```

```
### `unique`
**Arguments:** `seq`
**Decorators:** ``

**Docstring:**
```
use this instead of list(set()) to preserve order of the original list.
Thanks to Stackoverflow: http://stackoverflow.com/questions/480214/how-do-you-remove-duplicates-from-a-list-in-python-whilst-preserving-order
```
### `strip`
**Arguments:** `val, chars`
**Decorators:** ``

**Docstring:**
```
Strip the given characters from the given string.

e.g. strip(',hello,bye,', ',') -> 'hello,bye'
```
### `get_string_between`
**Arguments:** `start, string, end`
**Decorators:** ``

**Docstring:**
```

```
### `to_markdown`
**Arguments:** `html`
**Decorators:** ``

**Docstring:**
```
Convert the given HTML to markdown and returns it.
```
### `md_to_html`
**Arguments:** `markdown_text`
**Decorators:** ``

**Docstring:**
```
Convert the given markdown text to HTML and returns it.
```
### `markdown`
**Arguments:** `markdown_text`
**Decorators:** ``

**Docstring:**
```
Convert the given markdown text to HTML and returns it.
```
### `is_subset`
**Arguments:** `list_a, list_b`
**Decorators:** ``

**Docstring:**
```
Return whether list_a is a subset of list_b.
```
### `generate_hash`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Generates a random hash using best available randomness source and returns it.

You can optionally provide the `length` of the hash to be generated. Default is 56.
```
### `sha256_hash`
**Arguments:** `input`
**Decorators:** ``

**Docstring:**
```
Return hash of the string using sha256 algorithm.
```
### `dict_with_keys`
**Arguments:** `dict, keys`
**Decorators:** ``

**Docstring:**
```
Return a new dict with a subset of keys.
```
### `guess_date_format`
**Arguments:** `date_string`
**Decorators:** ``

**Docstring:**
```

```
### `validate_json_string`
**Arguments:** `string`
**Decorators:** ``

**Docstring:**
```

```
### `parse_json`
**Arguments:** `val`
**Decorators:** ``

**Docstring:**
```
Parses json if string else return
```
### `orjson_dumps`
**Arguments:** `obj, default, option, decode`
**Decorators:** ``

**Docstring:**
```
A wrapper around `orjson.dumps`, with some default options set
```
### `get_user_info_for_avatar`
**Arguments:** `user_id`
**Decorators:** ``

**Docstring:**
```
Return user info for the given `user_id` suitable for use in an avatar.

e.g. {
        "email": "faris@frappe.io",
        "image": "/assets/frappe/images/ui/avatar.png",
        "name": "Faris Ansari"
}
```
### `validate_python_code`
**Arguments:** `string, fieldname, is_expression`
**Decorators:** ``

**Docstring:**
```
Validate python code fields by using compile_command to ensure that expression is valid python.

args:
        fieldname: name of field being validated.
        is_expression: true for validating simple single line python expression, else validated as script.
```
### `format_timedelta`
**Arguments:** `o`
**Decorators:** ``

**Docstring:**
```

```
### `parse_timedelta`
**Arguments:** `s`
**Decorators:** ``

**Docstring:**
```

```
### `get_job_name`
**Arguments:** `key, doctype, doc_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_imaginary_pixel_response`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `is_site_link`
**Arguments:** `link`
**Decorators:** ``

**Docstring:**
```

```
### `bold`
**Arguments:** `text`
**Decorators:** ``

**Docstring:**
```
Return `text` wrapped in `<strong>` tags.
```
### `safe_encode`
**Arguments:** `param, encoding`
**Decorators:** ``

**Docstring:**
```

```
### `safe_decode`
**Arguments:** `param, encoding, fallback_map`
**Decorators:** ``

**Docstring:**
```
Method to safely decode data into a string

:param param: The data to be decoded
:param encoding: The encoding to decode into
:param fallback_map: A fallback map to reference in case of a LookupError
:return:
```
### `as_unicode`
**Arguments:** `text, encoding`
**Decorators:** ``

**Docstring:**
```
Convert to unicode if required.
```
### `mock`
**Arguments:** `type, size, locale`
**Decorators:** ``

**Docstring:**
```

```
### `recursive_defaultdict`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_get_rss_memory_usage`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `add_trackers_to_url`
**Arguments:** `url, source, campaign, medium, content`
**Decorators:** ``

**Docstring:**
```

```
### `parse_and_map_trackers_from_url`
**Arguments:** `url, create`
**Decorators:** ``

**Docstring:**
```

```
### `map_trackers`
**Arguments:** `url_trackers, create`
**Decorators:** ``

**Docstring:**
```

```

