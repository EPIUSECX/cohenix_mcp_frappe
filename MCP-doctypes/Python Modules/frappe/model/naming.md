# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/naming.py`

## Classes

### `InvalidNamingSeriesError`


**Docstring:**
```

```

**Methods:**
No methods found.

### `InvalidUUIDValue`


**Docstring:**
```

```

**Methods:**
No methods found.

### `NamingSeries`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, series` | `` |  |
| `validate` | `self` | `` |  |
| `generate_next_name` | `self, doc` | `` |  |
| `get_prefix` | `self` | `` | Naming series stores prefix to maintain a counter in DB. This prefix can be used to update counter or validations.

e.g. `SINV-.YY.-.####` has prefix of `SINV-22-` in database for year 2022. |
| `get_preview` | `self, doc` | `` | Generate preview of naming series without using DB counters |
| `update_counter` | `self, new_count` | `` | Warning: Incorrectly updating series can result in unusable transactions |
| `get_current_value` | `self` | `` |  |





## Functions

### `set_new_name`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Sets the `name` property for the document based on various rules.

1. If amended doc, set suffix.
2. If `autoname` method is declared, then call it.
3. If `autoname` property is set in the DocType (`meta`), then build it using the `autoname` property.
4. If no rule defined, use hash.

:param doc: Document to be named.
```
### `is_autoincremented`
**Arguments:** `doctype, meta`
**Decorators:** ``

**Docstring:**
```
Checks if the doctype has autoincrement autoname set
```
### `set_name_from_naming_options`
**Arguments:** `autoname, doc`
**Decorators:** ``

**Docstring:**
```
Get a name based on the autoname field option
```
### `set_naming_from_document_naming_rule`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Evaluate rules based on "Document Naming Series" doctype
```
### `set_name_by_naming_series`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```
Sets name by the `naming_series` property
```
### `make_autoname`
**Arguments:** `key, doctype, doc`
**Decorators:** ``

**Docstring:**
```
     Creates an autoname from the given key:

     **Autoname rules:**

              * The key is separated by '.'
              * '####' represents a series. The string before this part becomes the prefix:
                     Example: ABC.#### creates a series ABC0001, ABC0002 etc
              * 'MM' represents the current month
              * 'YY' and 'YYYY' represent the current year


*Example:*

              * DE./.YY./.MM./.##### will create a series like
                DE/09/01/00001 where 09 is the year, 01 is the month and 00001 is the series
```
### `_get_timestamp_prefix`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `_generate_random_string`
**Arguments:** `length`
**Decorators:** ``

**Docstring:**
```
Better version of frappe.generate_hash for naming.

This uses entire base32 instead of base16 used by generate_hash. So it has twice as many
characters and hence more likely to have shorter common prefixes. i.e. slighly faster comparisons and less conflicts.

Why not base36?
It's not in standard library else using all characters is probably better approach.
Why not base64?
MySQL is case-insensitive, we can't use both upper and lower case characters.
```
### `parse_naming_series`
**Arguments:** `parts, doctype, doc, number_generator`
**Decorators:** ``

**Docstring:**
```
Parse the naming series and get next name.

args:
        parts: naming series parts (split by `.`)
        doc: document to use for series that have parts using fieldnames
        number_generator: Use different counter backend other than `tabSeries`. Primarily used for testing.
```
### `has_custom_parser`
**Arguments:** `e`
**Decorators:** ``

**Docstring:**
```
Return True if the naming series part has a custom parser.
```
### `determine_consecutive_week_number`
**Arguments:** `datetime`
**Decorators:** ``

**Docstring:**
```
Determines the consecutive calendar week
```
### `getseries`
**Arguments:** `key, digits`
**Decorators:** ``

**Docstring:**
```

```
### `revert_series_if_last`
**Arguments:** `key, name, doc`
**Decorators:** ``

**Docstring:**
```
Reverts the series for particular naming series:
* key is naming series          - SINV-.YYYY-.####
* name is actual name           - SINV-2021-0001

1. This function split the key into two parts prefix (SINV-YYYY) & hashes (####).
2. Use prefix to get the current index of that naming series from Series table
3. Then revert the current index.

*For custom naming series:*
1. hash can exist anywhere, if it exist in hashes then it take normal flow.
2. If hash doesn't exit in hashes, we get the hash from prefix, then update name and prefix accordingly.

*Example:*
        1. key = SINV-.YYYY.-
                * If key doesn't have hash it will add hash at the end
                * prefix will be SINV-YYYY based on this will get current index from Series table.
        2. key = SINV-.####.-2021
                * now prefix = SINV-#### and hashes = 2021 (hash doesn't exist)
                * will search hash in key then accordingly get prefix = SINV-
        3. key = ####.-2021
                * prefix = #### and hashes = 2021 (hash doesn't exist)
                * will search hash in key then accordingly get prefix = ""
```
### `get_default_naming_series`
**Arguments:** `doctype`
**Decorators:** ``

**Docstring:**
```
get default value for `naming_series` property
```
### `validate_name`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```
### `append_number_if_name_exists`
**Arguments:** `doctype, value, fieldname, separator, filters`
**Decorators:** ``

**Docstring:**
```

```
### `_set_amended_name`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `_field_autoname`
**Arguments:** `autoname, doc, skip_slicing`
**Decorators:** ``

**Docstring:**
```
Generate a name using `DocType` field. This is called when the doctype's
`autoname` field starts with 'field:'
```
### `_prompt_autoname`
**Arguments:** `autoname, doc`
**Decorators:** ``

**Docstring:**
```
Generate a name using Prompt option. This simply means the user will have to set the name manually.
This is called when the doctype's `autoname` field starts with 'prompt'.
```
### `_format_autoname`
**Arguments:** `autoname, doc`
**Decorators:** ``

**Docstring:**
```
Generate autoname by replacing all instances of braced params (fields, date params ('DD', 'MM', 'YY'), series)
Independent of remaining string or separators.

Example pattern: 'format:LOG-{MM}-{fieldname1}-{fieldname2}-{#####}'
```

