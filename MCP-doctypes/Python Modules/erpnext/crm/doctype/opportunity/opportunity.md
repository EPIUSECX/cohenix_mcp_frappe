# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/opportunity/opportunity.py`

## Classes

### `Opportunity`
**Inherits:** `TransactionBase, CRMNote`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `onload` | `self` | `` |  |
| `after_insert` | `self` | `` |  |
| `validate` | `self` | `` |  |
| `on_update` | `self` | `` |  |
| `map_fields` | `self` | `` |  |
| `set_exchange_rate` | `self` | `` |  |
| `calculate_totals` | `self` | `` |  |
| `update_prospect` | `self` | `` |  |
| `make_new_lead_if_required` | `self` | `` | Set lead against new opportunity |
| `declare_enquiry_lost` | `self, lost_reasons_list, competitors, detailed_reason` | `` |  |
| `has_active_quotation` | `self` | `` |  |
| `has_ordered_quotation` | `self` | `` |  |
| `has_lost_quotation` | `self` | `` |  |
| `validate_cust_name` | `self` | `` |  |
| `validate_item_details` | `self` | `` |  |





## Functions

### `get_item_details`
**Arguments:** `item_code`
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
### `make_request_for_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_customer`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `make_supplier_quotation`
**Arguments:** `source_name, target_doc`
**Decorators:** ``

**Docstring:**
```

```
### `set_multiple_status`
**Arguments:** `names, status`
**Decorators:** ``

**Docstring:**
```

```
### `auto_close_opportunity`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```
auto close the `Replied` Opportunities after 7 days
```
### `make_opportunity_from_communication`
**Arguments:** `communication, company, ignore_communication_links`
**Decorators:** ``

**Docstring:**
```

```

