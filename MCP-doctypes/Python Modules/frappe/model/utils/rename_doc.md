# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/model/utils/rename_doc.py`

## Classes

No classes found in this file.


## Functions

### `update_linked_doctypes`
**Arguments:** `doctype, docname, linked_to, value, ignore_doctypes`
**Decorators:** ``

**Docstring:**
```
linked_doctype_info_list = list formed by get_fetch_fields() function
docname = Master DocType's name in which modification are made
value = Value for the field thats set in other DocType's by fetching from Master DocType
```
### `get_fetch_fields`
**Arguments:** `doctype, linked_to, ignore_doctypes`
**Decorators:** ``

**Docstring:**
```
doctype = Master DocType in which the changes are being made
linked_to = DocType name of the field thats being updated in Master
This function fetches list of all DocType where both doctype and linked_to is found
as link fields.
Forms a list of dict in the form -
        [{doctype: , master_fieldname: , linked_to_fieldname: ]
where
        doctype = DocType where changes need to be made
        master_fieldname = Fieldname where options = doctype
        linked_to_fieldname = Fieldname where options = linked_to
```

