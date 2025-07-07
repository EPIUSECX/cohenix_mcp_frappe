# Python Module Analysis: `/workspace/cohenix-bench/apps/insights/insights/insights/doctype/insights_data_source_v3/ibis/functions.py`

## Classes

No classes found in this file.


## Functions

### `count`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def count(column=None, where=None)

Count the number of non-null values in a column.

Examples:
- count()
- count(user_id)
- count(user_id, status == 'Active')
- count(user_id, group_by=month(date), order_by=asc(date))
```
### `count_if`
**Arguments:** `condition, column, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def count_if(condition)

Count the number of rows that satisfy a condition.

Examples:
- count_if(status == 'Active')
- count_if(status == 'Active', user_id)
- count_if(status == 'Active', user_id, group_by=month(date), order_by=asc(date))
```
### `min`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def min(column, where=None)

Find the minimum value in a column.

Examples:
- min(column)
- min(column, where=status == 'Active')
- min(column, group_by=user_id, order_by=date)
- min(column, group_by=[user_id, month(date)], order_by=asc(date))
```
### `max`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def max(column, where=None)

Find the maximum value in a column.

Examples:
- max(column)
- max(column, status == 'Active')
- max(column, group_by=user_id, order_by=date)
```
### `sum`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def sum(column, where=None)

Find the sum of values in a column.

Examples:
- sum(column)
- sum(column, status == 'Active')
- sum(column, group_by=user_id, order_by=date)
```
### `avg`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def avg(column, where=None)

Find the average of values in a column.

Examples:
- avg(column)
- avg(column, status == 'Active')
- avg(column, group_by=user_id, order_by=date)
```
### `median`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def median(column, where=None)

Find the median value in a column.

Examples:
- median(column)
- median(column, status == 'Active')
- median(column, group_by=user_id, order_by=date)
```
### `group_concat`
**Arguments:** `column, sep, where`
**Decorators:** ``

**Docstring:**
```
def group_concat(column, sep=',', where=None)

Concatenate values of a column into a single string.

Examples:
- group_concat(column)
- group_concat(column, '-', status == 'Active')
```
### `distinct_count`
**Arguments:** `column, where, group_by, order_by`
**Decorators:** ``

**Docstring:**
```
def distinct_count(column, where=None)

Count the number of unique values in a column.

Examples:
- distinct_count(column)
- distinct_count(column, status == 'Active')
- distinct_count(column, group_by=user_id, order_by=date)
```
### `sum_if`
**Arguments:** `condition, column`
**Decorators:** ``

**Docstring:**
```
def sum_if(condition, column)

Find the sum of values in a column that satisfy a condition.

Examples:
- sum_if(status == 'Active', column)
```
### `distinct_count_if`
**Arguments:** `condition, column`
**Decorators:** ``

**Docstring:**
```
def distinct_count_if(condition, column)

Count the number of unique values in a column that satisfy a condition.

Examples:
- distinct_count_if(status == 'Active', column)
```
### `is_in`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def is_in(column, *values)

Check if value is in a list of values.

Examples:
- is_in(status, 'Active', 'Inactive')
- is_in(user_id, 1, 2, 3)
```
### `is_not_in`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def is_not_in(column, *values)

Check if value is not in a list of values.

Examples:
- is_not_in(status, 'Active', 'Inactive')
- is_not_in(user_id, 1, 2, 3)
```
### `is_set`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def is_set(column)

Check if value is not null.

Examples:
- is_set(email)
```
### `is_not_set`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def is_not_set(column)

Check if value is null.

Examples:
- is_not_set(email)
```
### `is_between`
**Arguments:** `column, start, end`
**Decorators:** ``

**Docstring:**
```
def is_between(column, start, end)

Check if value is between start and end.

Examples:
- is_between(age, 18, 60)
```
### `is_not_between`
**Arguments:** `column, start, end`
**Decorators:** ``

**Docstring:**
```
def is_not_between(column, start, end)

Check if value is not between start and end.

Examples:
- is_not_between(age, 18, 60)
```
### `if_else`
**Arguments:** `condition, true_value, false_value`
**Decorators:** ``

**Docstring:**
```
def if_else(condition, true_value, false_value)

Return true_value if condition is true, else return false_value.

Examples:
- if_else(status == 'Active', 1, 0)
```
### `case`
**Arguments:** `condition, value`
**Decorators:** ``

**Docstring:**
```
def case(condition, value, *args)

Return value if condition is true, else return value of the next condition.

Examples:
- case(age > 18, 'Eligible', 'Not Eligible')
- case(age > 30, 'Above 30', age > 20, 'Above 20')
```
### `abs`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def abs(column)

Return the absolute value of a column.

Examples:
- abs(column)
```
### `round`
**Arguments:** `column, decimals`
**Decorators:** ``

**Docstring:**
```
def round(column, decimals=0)

Round the values of a column to the nearest integer.

Examples:
- round(column)
- round(column, 2)
```
### `floor`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def floor(column)

Return the floor of a column.

Examples:
- floor(column)
```
### `ceil`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def ceil(column)

Return the ceiling of a column.

Examples:
- ceil(column)
```
### `lower`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def lower(column)

Convert the values of a column to lowercase.

Examples:
- lower(column)
```
### `upper`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def upper(column)

Convert the values of a column to uppercase.

Examples:
- upper(column)
```
### `concat`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def concat(column, *args)

Concatenate values of multiple strings or string columns into one string.

Examples:
- concat(first_name, ' ', last_name)
```
### `replace`
**Arguments:** `column, old, new`
**Decorators:** ``

**Docstring:**
```
def replace(column, old, new)

Replace a substring with another substring in a column.

Examples:
- replace(email, '@', ' at ')
```
### `find`
**Arguments:** `column, sub`
**Decorators:** ``

**Docstring:**
```
def find(column, sub)

Find the position of a substring in a column.

Examples:
- find(email, '@')
```
### `substring`
**Arguments:** `column, start, length`
**Decorators:** ``

**Docstring:**
```
def substring(column, start, length=None)

Extract a substring from a column.

Examples:
- substring(email, 0, 3)
- substring(email, find(email, '@'))
```
### `contains`
**Arguments:** `column, sub`
**Decorators:** ``

**Docstring:**
```
def contains(column, sub)

Check if a substring is present in a column.

Examples:
- contains(email, '@')
- contains(name, first_name)
```
### `not_contains`
**Arguments:** `column, sub`
**Decorators:** ``

**Docstring:**
```
def not_contains(column, sub)

Check if a substring is not present in a column.

Examples:
- not_contains(email, '@')
- not_contains(name, first_name)
```
### `starts_with`
**Arguments:** `column, sub`
**Decorators:** ``

**Docstring:**
```
def starts_with(column, sub)

Check if a column starts with a substring.

Examples:
- starts_with(email, 'info')
```
### `ends_with`
**Arguments:** `column, sub`
**Decorators:** ``

**Docstring:**
```
def ends_with(column, sub)

Check if a column ends with a substring.

Examples:
- ends_with(email, '.com')
```
### `length`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def length(column)

Find the length of a column.

Examples:
- length(column)
```
### `year`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def year(column)

Extract the year from a date column.

Examples:
- year(order_date)
```
### `quarter`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def quarter(column)

Extract the quarter from a date column.

Examples:
- quarter(order_date)
```
### `month`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def month(column)

Extract the month from a date column.

Examples:
- month(order_date)
```
### `week_of_year`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def week_of_year(column)

Extract the week of the year (1-53) from a date column.

Examples:
- week_of_year(order_date)
```
### `day_of_year`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def day_of_year(column)

Extract the day of the year (1-366) from a date column.

Examples:
- day_of_year(order_date)
```
### `day_of_week`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def day_of_week(column)

Extract the day of the week (0-6) from a date column.

Examples:
- day_of_week(order_date)
```
### `day_name`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def day_name(column)

Extract the name of the day (Monday-Sunday) from a date column.

Examples:
- day_name(order_date)
```
### `day`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def day(column)

Extract the day from a date column.

Examples:
- day(order_date)
```
### `hour`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def hour(column)

Extract the hour from a time column.

Examples:
- hour(time_column)
```
### `minute`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def minute(column)

Extract the minute from a time column.

Examples:
- minute(time_column)
```
### `second`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def second(column)

Extract the second from a time column.

Examples:
- second(time_column)
```
### `microsecond`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def microsecond(column)

Extract the microsecond from a time column.

Examples:
- microsecond(time_column)
```
### `format_date`
**Arguments:** `column, format_str`
**Decorators:** ``

**Docstring:**
```
def format_date(column, format_str)

Format a date column according to a format string.

Examples:
- format_date(order_date, '%Y-%m-%d')
```
### `date_diff`
**Arguments:** `column, other, unit`
**Decorators:** ``

**Docstring:**
```
def date_diff(column, other, unit)

Calculate the difference between two date columns. The unit can be year, quarter, month, week, or day.

Examples:
- date_diff(order_date, delivery_date, 'day')
- date_diff(order_date, delivery_date, 'week')
```
### `time_diff`
**Arguments:** `column, other, unit`
**Decorators:** ``

**Docstring:**
```
def time_diff(column, other, unit)

Calculate the difference between two time columns. The unit can be hour, minute, second, millisecond, microsecond, nanosecond

Examples:
- time_diff(start_time, end_time, 'hour')
- time_diff(start_time, end_time, 'minute')
```
### `date_add`
**Arguments:** `column, value, unit`
**Decorators:** ``

**Docstring:**
```
def date_add(column, value, unit)

Add a value to a date column. The unit can be seconds, minutes, hours, days, weeks, months, or years.

Examples:
- date_add(order_date, 1, 'days')
- date_add(order_date, 1, 'weeks')
```
### `date_sub`
**Arguments:** `column, value, unit`
**Decorators:** ``

**Docstring:**
```
def date_sub(column, value, unit)

Subtract a value from a date column. The unit can be seconds, minutes, hours, days, weeks, months, or years.

Examples:
- date_sub(order_date, 1, 'days')
- date_sub(order_date, 1, 'weeks')
```
### `within`
**Arguments:** `column, timespan`
**Decorators:** ``

**Docstring:**
```
def within(column, timespan)

Filter rows within a timespan. The timespan can be 'Last [N] [Parts]', 'Current [Parts]', or 'Next [N] [Parts]'.
Parts can be 'day', 'week', 'month', 'quarter', 'year' or 'fiscal year'.

Examples:
- within(order_date, 'Last 7 days')
- within(order_date, 'Current month')
- within(order_date, 'Next 2 weeks')
```
### `now`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
def now()

Get the current timestamp.

Examples:
- now()
```
### `today`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
def today()

Get the current date.

Examples:
- today()
```
### `to_inr`
**Arguments:** `curr, amount, rate`
**Decorators:** ``

**Docstring:**
```
def to_inr(curr, amount, rate=83)

Convert an amount from USD to INR.

Examples:
- to_inr('USD', amount)
- to_inr('USD', amount, 75)
- to_inr('USD', amount, exchange_rate)
```
### `to_usd`
**Arguments:** `curr, amount, rate`
**Decorators:** ``

**Docstring:**
```
def to_usd(curr, amount, rate=83)

Convert an amount from INR to USD.

Examples:
- to_usd('INR', amount)
- to_usd('INR', amount, 75)
- to_usd('INR', amount, exchange_rate)
```
### `literal`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```
def literal(value)

Create a literal value.

Examples:
- literal(1)
- literal('Active')
```
### `constant`
**Arguments:** `value`
**Decorators:** ``

**Docstring:**
```
def constant(value)

Create a constant value.

Examples:
- constant(1)
- constant('Active')
```
### `row_number`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
def row_number()

Assign a unique number to each row.
```
### `sql`
**Arguments:** `query`
**Decorators:** ``

**Docstring:**
```
def sql(query)

Execute a SQL query.

Examples:
- sql('SELECT * FROM table')
```
### `coalesce`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
def coalesce(*args)

Return the first non-null value in a list of columns.

Examples:
- coalesce(column1, column2, column3)
```
### `if_null`
**Arguments:** `column, value`
**Decorators:** ``

**Docstring:**
```
def if_null(column, value)

Replace null values in a column with a default value.

Examples:
- if_null(email, 'No Email')
```
### `asc`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def asc(column)

Sort a column in ascending order.

Examples:
- asc(column)
```
### `desc`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def desc(column)

Sort a column in descending order.

Examples:
- desc(column)
```
### `previous_value`
**Arguments:** `column, group_by, order_by, offset`
**Decorators:** ``

**Docstring:**
```
def previous_value(column, group_by=None, order_by=None, offset=1)

Get the value of a column in the previous row. Provide group_by and order_by columns for partitioning and ordering.

Examples:
- previous_value(amount)
- previous_value(amount, group_by=user_id, order_by=date)
- previous_value(amount, group_by=[user_id, month(date)], order_by=asc(date))
```
### `next_value`
**Arguments:** `column, group_by, order_by, offset`
**Decorators:** ``

**Docstring:**
```
def next_value(column, group_by=None, order_by=None, offset=1)

Get the value of a column in the next row. Provide group_by and order_by columns for partitioning and ordering.

Examples:
- next_value(amount)
- next_value(amount, group_by=user_id, order_by=date)
- next_value(amount, group_by=[user_id, month(date)], order_by=asc(date))
```
### `previous_period_value`
**Arguments:** `column, date_column, offset`
**Decorators:** ``

**Docstring:**
```
def previous_period_value(column, date_column, offset=1)

Get the value of a column in the previous period. If the date values are at month level then the previous month value will be returned. Similarly, at year level, the previous year value will be returned.

Examples:
- previous_period_value(amount, date)
- previous_period_value(amount, date, 2)
```
### `next_period_value`
**Arguments:** `column, date_column, offset`
**Decorators:** ``

**Docstring:**
```
def next_period_value(column, date_column, offset=1)

Get the value of a column in the next period. If the date values are at month level then the next month value will be returned. Similarly, at year level, the next year value will be returned.

Examples:
- next_period_value(amount, date)
- next_period_value(amount, date, 2)
```
### `percentage_change`
**Arguments:** `column, date_column, offset`
**Decorators:** ``

**Docstring:**
```
def percentage_change(column, date_column, offset=1)

Calculate the percentage change of a column in the previous period. If the date values are at month level then percentage change from the previous month will be calculated. Similarly, at year level, percentage change from the previous year will be calculated.

Examples:
- percentage_change(amount, date)
- percentage_change(amount, date, 2)
```
### `is_first_row`
**Arguments:** `group_by, order_by, sort_order`
**Decorators:** ``

**Docstring:**
```
def is_first_row(group_by=None, order_by=None, sort_order="asc")

Check if the row is the first row in the group. Provide group_by and order_by columns for partitioning and ordering.

Examples:
- is_first_row()
- is_first_row(group_by=user_id, order_by=date)
- is_first_row(group_by=[user_id, month(date)], order_by=asc(date))
```
### `is_last_row`
**Arguments:** `group_by, order_by, sort_order`
**Decorators:** ``

**Docstring:**
```
def is_last_row(group_by=None, order_by=None, sort_order="asc")

Check if the row is the last row in the group. Provide group_by and order_by columns for partitioning and ordering.

Examples:
- is_last_row()
- is_last_row(group_by=user_id, order_by=date)
- is_last_row(group_by=[user_id, month(date)], order_by=asc(date))
```
### `filter_first_row`
**Arguments:** `group_by, order_by, sort_order`
**Decorators:** ``

**Docstring:**
```
def filter_first_row(group_by=None, order_by=None, sort_order="asc")

Filter to keep only the first row of each group. Provide group_by and order_by columns for partitioning and ordering.

Examples:
- filter_first_row()
- filter_first_row(group_by=user_id, order_by=date)
- filter_first_row(group_by=[user_id, month(date)], order_by=asc(date))
```
### `create_buckets`
**Arguments:** `column, num_buckets`
**Decorators:** ``

**Docstring:**
```
def create_buckets(column, num_buckets)

Create buckets based on the values in a column. The number of buckets will be equal to num_buckets.

Examples:
- create_buckets(age, 3)
  -> 0-33, 34-66, 67-100
```
### `week_start`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def week_start(column)

Get the start date of the week for a given date.

Examples:
- week_start(order_date)
```
### `month_start`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def month_start(column)

Get the start date of the month for a given date.

Examples:
- month_start(order_date)
```
### `quarter_start`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def quarter_start(column)

Get the start date of the quarter for a given date.

Examples:
- quarter_start(order_date)
```
### `year_start`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def year_start(column)

Get the start date of the year for a given date.

Examples:
- year_start(order_date)
```
### `fiscal_year_start`
**Arguments:** `column`
**Decorators:** ``

**Docstring:**
```
def fiscal_year_start(column)

Get the start date of the fiscal year for a given date.

Examples:
- fiscal_year_start(order_date)
```
### `get_retention_data`
**Arguments:** `date_column, id_column, unit`
**Decorators:** ``

**Docstring:**
```
def get_retention_data(date_column, id_column, unit)

Calculate retention data based on the cohort analysis. The unit can be day, week, month, or year.

Examples:
- get_retention_data(date, user_id, 'day')
```
### `pad_number`
**Arguments:** `number, digits`
**Decorators:** ``

**Docstring:**
```
def pad_number(number, digits)

Convert an integer into an n digit string.

Examples:
- pad_number(1, 2) -> '01'
- pad_number(1, 3) -> '001'
```

