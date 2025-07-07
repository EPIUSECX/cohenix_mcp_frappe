# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/contacts/doctype/contact/contact.py`

## Classes

### `Contact`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `autoname` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_user` | `self` | `` |  |
| `get_link_for` | `self, link_doctype` | `` | Return the link name, if exists for the given link DocType |
| `has_link` | `self, doctype, name` | `` |  |
| `has_common_link` | `self, doc` | `` |  |
| `add_email` | `self, email_id, is_primary, autosave` | `` |  |
| `add_phone` | `self, phone, is_primary_phone, is_primary_mobile_no, autosave` | `` |  |
| `set_primary_email` | `self` | `` |  |
| `set_primary` | `self, fieldname` | `` |  |
| `_get_full_name` | `self` | `` |  |
| `get_vcard` | `self` | `` |  |





## Functions

### `download_vcard`
**Arguments:** `contact`
**Decorators:** ``

**Docstring:**
```
Download vCard for the contact
```
### `download_vcards`
**Arguments:** `contacts`
**Decorators:** ``

**Docstring:**
```
Download vCard for the contact
```
### `get_default_contact`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```
Return default contact for the given doctype, name.
```
### `invite_user`
**Arguments:** `contact`
**Decorators:** ``

**Docstring:**
```

```
### `get_contact_details`
**Arguments:** `contact`
**Decorators:** ``

**Docstring:**
```

```
### `update_contact`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Update contact when user is updated, if contact is found. Called via hooks
```
### `contact_query`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```
### `address_query`
**Arguments:** `links`
**Decorators:** ``

**Docstring:**
```

```
### `get_contact_with_phone_number`
**Arguments:** `number`
**Decorators:** ``

**Docstring:**
```

```
### `get_contact_name`
**Arguments:** `email_id`
**Decorators:** ``

**Docstring:**
```
Return the contact ID for the given email ID.
```
### `get_contacts_linking_to`
**Arguments:** `doctype, docname, fields`
**Decorators:** ``

**Docstring:**
```
Return a list of contacts containing a link to the given document.
```
### `get_contacts_linked_from`
**Arguments:** `doctype, docname, fields`
**Decorators:** ``

**Docstring:**
```
Return a list of contacts that are contained in (linked from) the given document.
```
### `get_full_name`
**Arguments:** `first, middle, last, company`
**Decorators:** ``

**Docstring:**
```

```
### `get_contact_display_list`
**Arguments:** `doctype, name`
**Decorators:** ``

**Docstring:**
```

```

