# Python Module Analysis: `/workspace/cohenix-bench/apps/frappe/frappe/integrations/doctype/google_contacts/google_contacts.py`

## Classes

### `GoogleContacts`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `get_access_token` | `self` | `` |  |





## Functions

### `authorize_access`
**Arguments:** `g_contact, reauthorize, code`
**Decorators:** ``

**Docstring:**
```
If no Authorization code get it from Google and then request for Refresh Token.
Google Contact Name is set to flags to set_value after Authorization Code is obtained.
```
### `get_google_contacts_object`
**Arguments:** `g_contact`
**Decorators:** ``

**Docstring:**
```
Return an object of Google Calendar along with Google Calendar doc.
```
### `sync`
**Arguments:** `g_contact`
**Decorators:** ``

**Docstring:**
```

```
### `sync_contacts_from_google_contacts`
**Arguments:** `g_contact`
**Decorators:** ``

**Docstring:**
```
Syncs Contacts from Google Contacts.
https://developers.google.com/people/api/rest/v1/people.connections/list
```
### `insert_contacts_to_google_contacts`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Syncs Contacts from Google Contacts.
https://developers.google.com/people/api/rest/v1/people/createContact
```
### `update_contacts_to_google_contacts`
**Arguments:** `doc, method`
**Decorators:** ``

**Docstring:**
```
Syncs Contacts from Google Contacts.
https://developers.google.com/people/api/rest/v1/people/updateContact
```
### `get_indexed_value`
**Arguments:** `d, index, key`
**Decorators:** ``

**Docstring:**
```

```

