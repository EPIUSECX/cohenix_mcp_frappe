# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/regional/doctype/import_supplier_invoice/import_supplier_invoice.py`

## Classes

### `ImportSupplierInvoice`
**Inherits:** `Document`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `validate` | `self` | `` |  |
| `autoname` | `self` | `` |  |
| `import_xml_data` | `self` | `` |  |
| `prepare_data_for_import` | `self, file_content, file_name, encoded_content` | `` |  |
| `prepare_items_for_invoice` | `self, file_content, invoices_args` | `` |  |
| `process_file_data` | `self` | `` |  |
| `publish` | `self, title, message, count, total` | `` |  |





## Functions

### `get_file_content`
**Arguments:** `file_name, zip_file_object`
**Decorators:** ``

**Docstring:**
```

```
### `get_supplier_details`
**Arguments:** `file_content`
**Decorators:** ``

**Docstring:**
```

```
### `get_taxes_from_file`
**Arguments:** `file_content, tax_account`
**Decorators:** ``

**Docstring:**
```

```
### `get_payment_terms_from_file`
**Arguments:** `file_content`
**Decorators:** ``

**Docstring:**
```

```
### `get_destination_code_from_file`
**Arguments:** `file_content`
**Decorators:** ``

**Docstring:**
```

```
### `create_supplier`
**Arguments:** `supplier_group, args`
**Decorators:** ``

**Docstring:**
```

```
### `create_address`
**Arguments:** `supplier_name, args`
**Decorators:** ``

**Docstring:**
```

```
### `create_purchase_invoice`
**Arguments:** `supplier_name, file_name, args, name`
**Decorators:** ``

**Docstring:**
```

```
### `get_country`
**Arguments:** `code`
**Decorators:** ``

**Docstring:**
```

```
### `create_uom`
**Arguments:** `uom`
**Decorators:** ``

**Docstring:**
```

```

