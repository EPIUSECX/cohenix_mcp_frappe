# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/serial_no/test_serial_no.py`

## Classes

### `TestSerialNo`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `tearDown` | `self` | `` |  |
| `test_cannot_create_direct` | `self` | `` |  |
| `test_inter_company_transfer` | `self` | `` |  |
| `test_inter_company_transfer_intermediate_cancellation` | `self` | `` | Receive into and Deliver Serial No from one company.
Then Receive into and Deliver from second company.
Try to cancel intermediate receipts/deliveries to test if it is blocked. |
| `test_inter_company_transfer_fallback_on_cancel` | `self` | `` | Test Serial No state changes on cancellation.
If Delivery cancelled, it should fall back on last Receipt in the same company.
If Receipt is cancelled, it should be Inactive in the same company. |
| `test_correct_serial_no_incoming_rate` | `self` | `` | Check correct consumption rate based on serial no record. |
| `test_auto_fetch` | `self` | `` |  |





## Functions

### `get_auto_serial_nos`
**Arguments:** `kwargs`
**Decorators:** ``

**Docstring:**
```

```

