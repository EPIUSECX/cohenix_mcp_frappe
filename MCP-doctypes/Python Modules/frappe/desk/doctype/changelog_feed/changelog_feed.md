# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/doctype/changelog_feed/changelog_feed.py`

## Classes

### `ChangelogFeed`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
No methods found.




## Functions

### `fetch_changelog_feed`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Fetches changelog feed items from source using `get_changelog_feed` hook and stores in the db
```
### `get_changelog_feed_items`
**Arguments:** ``
**Decorators:** `redis_cache`

**Docstring:**
```
Returns a list of latest 10 changelog feed items
```
### `_app_title`
**Arguments:** `app_name`
**Decorators:** ``

**Docstring:**
```

```
### `get_feed`
**Arguments:** `since`
**Decorators:** ``

**Docstring:**
```
'What's New' feed implementation for Frappe
```

