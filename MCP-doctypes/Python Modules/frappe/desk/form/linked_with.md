# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/desk/form/linked_with.py`

## Classes

### `SubmittableDocumentTree`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, doctype, name` | `` | Construct a tree for the submitable linked documents.

* Node has properties like doctype and docnames. Represented as Node(doctype, docnames).
* Nodes are linked by doctype relationships like table, link and dynamic links.
* Node is referenced(linked) by many other documents and those are the child nodes.

NOTE: child document is a property of child node (not same as Frappe child docs of a table field). |
| `get_all_children` | `self, ignore_doctypes_on_cancel_all` | `` | Get all nodes of a tree except the root node (all the nested submitted
documents those are present in referencing tables dependent tables). |
| `get_next_level_children` | `self, parent_dt, parent_names` | `` | Get immediate children of a Node(parent_dt, parent_names) |
| `get_doctype_references` | `self, doctype` | `` | Get references for a given document. |
| `get_document_sources` | `self` | `` | Return list of doctypes from where we access submittable documents. |
| `get_link_sources` | `self` | `` | limit doctype links to these doctypes. |
| `get_submittable_doctypes` | `self` | `` | Return list of submittable doctypes. |





## Functions

### `get_submitted_linked_docs`
**Arguments:** `doctype, name, ignore_doctypes_on_cancel_all`
**Decorators:** ``

**Docstring:**
```
Get all the nested submitted documents those are present in referencing tables (dependent tables).

:param doctype: Document type
:param name: Name of the document

Use-case:
* User should be able to cancel the linked documents along with the one user trying to cancel.

Case1: If document sd1-n1 (document name n1 from submittable doctype sd1) is linked to sd2-n2 and sd2-n2 is linked to sd3-n3,
        Getting submittable linked docs of `sd1-n1`should give both sd2-n2 and sd3-n3.
Case2: If document sd1-n1 (document name n1 from submittable doctype sd1) is linked to d2-n2 and d2-n2 is linked to sd3-n3,
        Getting submittable linked docs of `sd1-n1`should give None. (because d2-n2 is not a submittable doctype)
Case3: If document sd1-n1 (document name n1 from submittable doctype sd1) is linked to d2-n2 & sd2-n2. d2-n2 is linked to sd3-n3.
        Getting submittable linked docs of `sd1-n1`should give sd2-n2.

Logic:
-----
1. We can find linked documents only if we know how the doctypes are related.
2. As we need only submittable documents, we can limit doctype relations search to submittable doctypes by
        finding the relationships(Foreign key references) across submittable doctypes.
3. Searching for links is going to be a tree like structure where at every level,
        you will be finding documents using parent document and parent document links.
```
### `get_child_tables_of_doctypes`
**Arguments:** `doctypes`
**Decorators:** ``

**Docstring:**
```
Return child tables by doctype.
```
### `get_references_across_doctypes`
**Arguments:** `to_doctypes, limit_link_doctypes`
**Decorators:** ``

**Docstring:**
```
Find doctype wise foreign key references.

:param to_doctypes: Get links of these doctypes.
:param limit_link_doctypes: limit links to these doctypes.

* Include child table, link and dynamic link references.
```
### `get_references_across_doctypes_by_link_field`
**Arguments:** `to_doctypes, limit_link_doctypes`
**Decorators:** ``

**Docstring:**
```
Find doctype wise foreign key references based on link fields.

:param to_doctypes: Get links to these doctypes.
:param limit_link_doctypes: limit links to these doctypes.
```
### `get_references_across_doctypes_by_dynamic_link_field`
**Arguments:** `to_doctypes, limit_link_doctypes`
**Decorators:** ``

**Docstring:**
```
Find doctype wise foreign key references based on dynamic link fields.

:param to_doctypes: Get links to these doctypes.
:param limit_link_doctypes: limit links to these doctypes.
```
### `get_referencing_documents`
**Arguments:** `reference_doctype, reference_names, link_info, get_parent_if_child_table_doc, parent_filters, child_filters, allowed_parents`
**Decorators:** ``

**Docstring:**
```
Get linked documents based on link_info.

:param reference_doctype: reference doctype to find links
:param reference_names: reference document names to find links for
:param link_info: linking details to get the linked documents
        Ex: {'doctype': 'Purchase Invoice Advance', 'fieldname': 'reference_name',
                'doctype_fieldname': 'reference_type', 'is_child': True}
:param get_parent_if_child_table_doc: Get parent record incase linked document is a child table record.
:param parent_filters: filters to apply on if not a child table.
:param child_filters: apply filters if it is a child table.
:param allowed_parents: list of parents allowed in case of get_parent_if_child_table_doc
        is enabled.
```
### `cancel_all_linked_docs`
**Arguments:** `docs, ignore_doctypes_on_cancel_all`
**Decorators:** ``

**Docstring:**
```
Cancel all linked doctype, optionally ignore doctypes specified in a list.

Arguments:
        docs (json str) - It contains list of dictionaries of a linked documents.
        ignore_doctypes_on_cancel_all (list) - List of doctypes to ignore while cancelling.
```
### `validate_linked_doc`
**Arguments:** `docinfo, ignore_doctypes_on_cancel_all`
**Decorators:** ``

**Docstring:**
```
Validate a document to be submitted and non-exempted from auto-cancel.

Arguments:
        docinfo (dict): The document to check for submitted and non-exempt from auto-cancel
        ignore_doctypes_on_cancel_all (list) - List of doctypes to ignore while cancelling.

Return:
        bool: True if linked document passes all validations, else False
```
### `get_exempted_doctypes`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
Get list of doctypes exempted from being auto-cancelled
```
### `get_linked_docs`
**Arguments:** `doctype, name, linkinfo`
**Decorators:** ``

**Docstring:**
```

```
### `get`
**Arguments:** `doctype, docname`
**Decorators:** ``

**Docstring:**
```

```
### `get_linked_doctypes`
**Arguments:** `doctype, without_ignore_user_permissions_enabled`
**Decorators:** ``

**Docstring:**
```
add list of doctypes this doctype is 'linked' with.

Example, for Customer:

        {"Address": {"fieldname": "customer"}..}
```
### `_get_linked_doctypes`
**Arguments:** `doctype, without_ignore_user_permissions_enabled`
**Decorators:** ``

**Docstring:**
```

```
### `get_linked_fields`
**Arguments:** `doctype, without_ignore_user_permissions_enabled`
**Decorators:** ``

**Docstring:**
```

```
### `get_dynamic_linked_fields`
**Arguments:** `doctype, without_ignore_user_permissions_enabled`
**Decorators:** ``

**Docstring:**
```

```

