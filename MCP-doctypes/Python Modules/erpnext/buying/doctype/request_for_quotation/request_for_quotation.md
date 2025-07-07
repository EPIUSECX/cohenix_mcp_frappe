# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/request_for_quotation/request_for_quotation.py`

## Classes

### `RequestforQuotation`
**Inherits:** `BuyingController`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `before_validate` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `set_has_unit_price_items` | `self` | `` | If permitted in settings and any item has 0 qty, the RFQ has unit price items. |
| `validate_duplicate_supplier` | `self` | `` |  |
| `validate_supplier_list` | `self` | `` |  |
| `update_email_id` | `self` | `` |  |
| `validate_email_id` | `self, args` | `` |  |
| `on_submit` | `self` | `` |  |
| `before_print` | `self, settings` | `` | Use the first suppliers data to render the print preview. |
| `on_cancel` | `self` | `` |  |
| `get_supplier_email_preview` | `self, supplier` | `` | Returns formatted email preview as string. |
| `send_to_supplier` | `self` | `` | Sends RFQ mail to involved suppliers. |
| `get_link` | `self` | `` |  |
| `update_supplier_part_no` | `self, supplier` | `` |  |
| `update_supplier_contact` | `self, rfq_supplier, link` | `` | Create a new user for the supplier if not set in contact |
| `link_supplier_contact` | `self, rfq_supplier, user` | `` | If no Contact, create a new contact against Supplier. If Contact exists, check if email and user id set. |
| `update_user_in_supplier` | `self, supplier, user` | `` | Update user in Supplier. |
| `create_user` | `self, rfq_supplier, link` | `` |  |
| `supplier_rfq_mail` | `self, data, update_password_link, rfq_link, preview` | `` |  |
| `send_email` | `self, data, sender, subject, message, attachments` | `` |  |
| `get_attachments` | `self` | `` |  |
| `update_rfq_supplier_status` | `self, sup_name` | `` |  |





## Functions

### `send_supplier_emails`
**Arguments:** `rfq_name`
**Decorators:** ``

**Docstring:**
```

```
### `check_portal_enabled`
**Arguments:** `reference_doctype`
**Decorators:** ``

**Docstring:**
```

```
### `get_list_context`
**Arguments:** `context`
**Decorators:** ``

**Docstring:**
```

```
### `make_supplier_quotation_from_rfq`
**Arguments:** `source_name, target_doc, for_supplier`
**Decorators:** ``

**Docstring:**
```

```
### `create_supplier_quotation`
**Arguments:** `doc`
**Decorators:** ``

**Docstring:**
```

```
### `add_items`
**Arguments:** `sq_doc, supplier, items`
**Decorators:** ``

**Docstring:**
```

```
### `create_rfq_items`
**Arguments:** `sq_doc, supplier, data`
**Decorators:** ``

**Docstring:**
```

```
### `get_pdf`
**Arguments:** `name, supplier, print_format, language, letterhead`
**Decorators:** ``

**Docstring:**
```

```
### `get_item_from_material_requests_based_on_supplier`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `get_supplier_tag`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `get_rfq_containing_supplier`
**Arguments:** `doctype, txt, searchfield, start, page_len, filters`
**Decorators:** ``

**Docstring:**
```

```

