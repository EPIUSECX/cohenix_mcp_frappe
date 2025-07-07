# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/lead/lead.py`

## Classes

### `Lead`
**Inherits:** `SellingController, CRMNote`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `before_insert` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `on_trash` | `self` | `` |  |
| `set_full_name` | `self` | `` |  |
| `set_lead_name` | `self` | `` |  |
| `set_title` | `self` | `` |  |
| `check_email_id_is_unique` | `self` | `` |  |
| `validate_email_id` | `self` | `` |  |
| `link_to_contact` | `self` | `` |  |
| `update_prospect` | `self` | `` |  |
| `remove_link_from_prospect` | `self` | `` |  |
| `get_linked_prospects` | `self` | `` |  |
| `has_customer` | `self` | `` |  |
| `has_opportunity` | `self` | `` |  |
| `has_quotation` | `self` | `` |  |
| `has_lost_quotation` | `self` | `` |  |
| `create_prospect_and_contact` | `self, data` | `` |  |
| `create_contact` | `self` | `` |  |
| `create_prospect` | `self, company_name` | `` |  |





## Functions

### `make_customer`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_make_customer`
**Arguments:** `source_name, target_doc, ignore_permissions`
**Decorators:** ``

**Docstring:**
```

```
### `make_opportunity`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `_set_missing_values`
**Arguments:** `source, target`
**Decorators:** ``

**Docstring:**
```

```
### `get_lead_details`
**Arguments:** `lead, posting_date, company`
**Decorators:** ``

**Docstring:**
```

```
### `make_lead_from_communication`
**Arguments:** `communication, ignore_communication_links`
**Decorators:** ``

**Docstring:**
```
raise a issue from email
```
### `get_lead_with_phone_number`
**Arguments:** `number`
**Decorators:** ``

**Docstring:**
```

```
### `add_lead_to_prospect`
**Arguments:** `lead, prospect`
**Decorators:** ``

**Docstring:**
```

```

