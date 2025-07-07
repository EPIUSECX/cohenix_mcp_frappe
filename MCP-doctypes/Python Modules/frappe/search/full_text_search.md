# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/search/full_text_search.py`

## Classes

### `FullTextSearch`


**Docstring:**
```
Frappe Wrapper for Whoosh
```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, index_name` | `` |  |
| `get_schema` | `self` | `` |  |
| `get_fields_to_search` | `self` | `` |  |
| `get_id` | `self` | `` |  |
| `get_items_to_index` | `self` | `` | Get all documents to be indexed conforming to the schema |
| `get_document_to_index` | `self` | `` |  |
| `build` | `self` | `` | Build search index for all documents |
| `update_index_by_name` | `self, doc_name` | `` | Wraps `update_index` method, gets the document from name
and updates the index. This function changes the current user
and should only be run as administrator or in a background job.

Args:
        self (object): FullTextSearch Instance
        doc_name (str): name of the document to be updated |
| `remove_document_from_index` | `self, doc_name` | `` | Remove document from search index

Args:
        self (object): FullTextSearch Instance
        doc_name (str): name of the document to be removed |
| `update_index` | `self, document` | `` | Update search index for a document

Args:
        self (object): FullTextSearch Instance
        document (_dict): A dictionary with title, path and content |
| `get_index` | `self` | `` |  |
| `create_index` | `self` | `` |  |
| `build_index` | `self` | `` | Build index for all parsed documents |
| `search` | `self, text, scope, limit` | `` | Search from the current index.

Args:
        text: String to search for
        scope: Scope to limit the search. Defaults to None.
        limit: Limit number of search results. Defaults to 20. |


### `FuzzyTermExtended`
**Inherits:** `FuzzyTerm`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, fieldname, text, boost, maxdist, prefixlength, constantscore` | `` |  |





## Functions

### `get_index_path`
**Arguments:** `index_name`
**Decorators:** ``

**Docstring:**
```

```

