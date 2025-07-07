# Master Control Plan: `Buying Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Buying`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Accounts Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock Manager | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Purchase User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `supplier_and_price_defaults_section` | Naming Series and Price Defaults | Tab Break | None |  |  |  | None | None |
| `supp_master_name` | Supplier Naming By | Select | Supplier Name
Naming Series
Auto Name |  |  |  | Supplier Name | None |
| `supplier_group` | Default Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `buying_price_list` | Default Buying Price List | Link | Price List |  |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `maintain_same_rate_action` | Action If Same Rate is Not Maintained | Select | Stop
Warn |  |  |  | Stop | Configure the action to stop the transaction or just warn if the same rate is not maintained. |
| `role_to_override_stop_action` | Role Allowed to Override Stop Action | Link | Role |  |  |  | None | None |
| `section_break_xmlt` | None | Section Break | None |  |  |  | None | None |
| `po_required` | Is Purchase Order Required for Purchase Invoice & Receipt Creation? | Select | No
Yes |  |  |  | None | None |
| `blanket_order_allowance` | Blanket Order Allowance (%) | Float | None |  |  |  | 0 | Percentage you are allowed to order beyond the Blanket Order quantity. |
| `column_break_sbwq` | None | Column Break | None |  |  |  | None | None |
| `pr_required` | Is Purchase Receipt Required for Purchase Invoice Creation? | Select | No
Yes |  |  |  | None | None |
| `project_update_frequency` | Update frequency of Project | Select | Each Transaction
Manual |  |  |  | Each Transaction | How often should Project be updated of Total Purchase Cost ? |
| `transaction_settings_section` | Transaction Settings | Tab Break | None |  |  |  | None | None |
| `column_break_fcyl` | None | Column Break | None |  |  |  | None | None |
| `set_landed_cost_based_on_purchase_invoice_rate` | Set Landed Cost Based on Purchase Invoice Rate | Check | None |  |  |  | 0 | Users can enable the checkbox If they want to adjust the incoming rate (set using purchase receipt) based on the purchase invoice rate. |
| `allow_zero_qty_in_supplier_quotation` | Allow Supplier Quotation with Zero Quantity | Check | None |  |  |  | 0 | Allows users to submit Supplier Quotations with zero quantity. Useful when rates are fixed but the quantities are not. Eg. Rate Contracts. |
| `use_transaction_date_exchange_rate` | Use Transaction Date Exchange Rate | Check | None |  |  |  | 0 | While making Purchase Invoice from Purchase Order, use Exchange Rate on Invoice's transaction date rather than inheriting it from Purchase Order. Only applies for Purchase Invoice. |
| `allow_zero_qty_in_request_for_quotation` | Allow Request for Quotation with Zero Quantity | Check | None |  |  |  | 0 | Allows users to submit Request for Quotations with zero quantity. Useful when rates are fixed but the quantities are not. Eg. Rate Contracts. |
| `column_break_12` | None | Column Break | None |  |  |  | None | None |
| `maintain_same_rate` | Maintain Same Rate Throughout the Purchase Cycle | Check | None |  |  |  | 0 | None |
| `allow_multiple_items` | Allow Item To Be Added Multiple Times in a Transaction | Check | None |  |  |  | 0 | None |
| `bill_for_rejected_quantity_in_purchase_invoice` | Bill for Rejected Quantity in Purchase Invoice | Check | None |  |  |  | 1 | If checked, Rejected Quantity will be included while making Purchase Invoice from Purchase Receipt. |
| `set_valuation_rate_for_rejected_materials` | Set Valuation Rate for Rejected Materials | Check | None |  |  |  | 0 | If enabled, the system will generate an accounting entry for materials rejected in the Purchase Receipt. |
| `disable_last_purchase_rate` | Disable Last Purchase Rate | Check | None |  |  |  | 0 | None |
| `show_pay_button` | Show Pay Button in Purchase Order Portal | Check | None |  |  |  | 1 | None |
| `allow_zero_qty_in_purchase_order` | Allow Purchase Order with Zero Quantity | Check | None |  |  |  | 0 | Allows users to submit Purchase Orders with zero quantity. Useful when rates are fixed but the quantities are not. Eg. Rate Contracts. |
| `subcontract` | Subcontracting Settings | Tab Break | None |  |  |  | None | None |
| `backflush_raw_materials_of_subcontract_based_on` | Backflush Raw Materials of Subcontract Based On | Select | BOM
Material Transferred for Subcontract |  |  |  | BOM | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `over_transfer_allowance` | Over Transfer Allowance (%) | Float | None |  |  |  | None | Percentage you are allowed to transfer more against the quantity ordered. For example: If you have ordered 100 units. and your Allowance is 10% then you are allowed to transfer 110 units. |
| `section_break_xcug` | None | Section Break | None |  |  |  | None | None |
| `auto_create_subcontracting_order` | Auto Create Subcontracting Order | Check | None |  |  |  | 0 | Subcontracting Order (Draft) will be auto-created on submission of Purchase Order. |
| `column_break_izrr` | None | Column Break | None |  |  |  | None | None |
| `auto_create_purchase_receipt` | Auto Create Purchase Receipt | Check | None |  |  |  | 0 | Purchase Receipt (Draft) will be auto-created on submission of Subcontracting Receipt. |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 3
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/buying/doctype/buying_settings/buying_settings.js`
```javascript
// Copyright (c) 2019, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Buying Settings", {
	// refresh: function(frm) {
	// }
});

frappe.tour["Buying Settings"] = [
	{
		fieldname: "supp_master_name",
		title: "Supplier Naming By",
		description: __(
			"By default, the Supplier Name is set as per the Supplier Name entered. If you want Suppliers to be named by a <a href='https://docs.erpnext.com/docs/user/manual/en/setting-up/settings/naming-series' target='_blank'>Naming Series</a> choose the 'Naming Series' option."
		),
	},
	{
		fieldname: "buying_price_list",
		title: "Default Buying Price List",
		description: __(
			"Configure the default Price List when creating a new Purchase transaction. Item prices will be fetched from this Price List."
		),
	},
	{
		fieldname: "po_required",
		title: "Purchase Order Required for Purchase Invoice & Receipt Creation",
		description: __(
			"If this option is configured 'Yes', ERPNext will prevent you from creating a Purchase Invoice or Receipt without creating a Purchase Order first. This configuration can be overridden for a particular supplier by enabling the 'Allow Purchase Invoice Creation Without Purchase Order' checkbox in the Supplier master."
		),
	},
	{
		fieldname: "pr_required",
		title: "Purchase Receipt Required for Purchase Invoice Creation",
		description: __(
			"If this option is configured 'Yes', ERPNext will prevent you from creating a Purchase Invoice without creating a Purchase Receipt first. This configuration can be overridden for a particular supplier by enabling the 'Allow Purchase Invoice Creation Without Purchase Receipt' checkbox in the Supplier master."
		),
	},
];

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
No linked reports found.


### Dashboard Charts
No dashboard charts found.


### Number Cards
No number cards found.


## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
