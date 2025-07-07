# Python Module Analysis: `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/landed_cost_voucher/test_landed_cost_voucher.py`

## Classes

### `TestLandedCostVoucher`
**Inherits:** `IntegrationTestCase`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `test_landed_cost_voucher` | `self` | `` |  |
| `assertPurchaseReceiptLCVGLEntries` | `self, pr` | `` |  |
| `test_landed_cost_voucher_stock_impact` | `self` | `` | Test impact of LCV on future stock balances. |
| `test_landed_cost_voucher_for_zero_purchase_rate` | `self` | `` | Test impact of LCV on future stock balances. |
| `test_landed_cost_voucher_against_purchase_invoice` | `self` | `` |  |
| `test_landed_cost_voucher_for_serialized_item` | `self` | `` |  |
| `test_serialized_lcv_delivered` | `self` | `` | In some cases you'd want to deliver before you can know all the
landed costs, this should be allowed for serial nos too.

Case:
                - receipt a serial no @ X rate
                - delivery the serial no @ X rate
                - add LCV to receipt X + Y
                - LCV should be successful
                - delivery should reflect X+Y valuation. |
| `test_landed_cost_voucher_for_odd_numbers` | `self` | `` |  |
| `test_multiple_landed_cost_voucher_against_pr` | `self` | `` |  |
| `test_multi_currency_lcv` | `self` | `` |  |
| `test_asset_lcv` | `self` | `` | Check if LCV for an Asset updates the Assets Gross Purchase Amount correctly. |
| `test_landed_cost_voucher_with_serial_batch_for_legacy_pr` | `self` | `` |  |
| `test_do_not_validate_landed_cost_voucher_with_serial_batch_for_legacy_pr` | `self` | `` |  |
| `test_do_not_validate_against_landed_cost_voucher_for_serial_for_legacy_pr` | `self` | `` |  |
| `test_lcv_for_work_order_scr` | `self` | `` |  |





## Functions

### `make_landed_cost_voucher`
**Arguments:** ``
**Decorators:** ``

**Docstring:**
```

```
### `create_landed_cost_voucher`
**Arguments:** `receipt_document_type, receipt_document, company, charges`
**Decorators:** ``

**Docstring:**
```

```
### `distribute_landed_cost_on_items`
**Arguments:** `lcv`
**Decorators:** ``

**Docstring:**
```

```

