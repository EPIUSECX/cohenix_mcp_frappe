# Master Control Plan: `Contract`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `CRM`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `CON-.YYYY.-.#####`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| HR Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `party_type` | Party Type | Select | Customer
Supplier
Employee | ✅ |  |  | Customer | None |
| `is_signed` | Signed | Check | None |  |  |  | 0 | None |
| `cb_party` | None | Column Break | None |  |  |  | None | None |
| `party_name` | Party Name | Dynamic Link | party_type | ✅ |  |  | None | None |
| `party_user` | Party User | Link | User |  |  |  | None | None |
| `status` | Status | Select | Unsigned
Active
Inactive |  | ✅ |  | None | None |
| `fulfilment_status` | Fulfilment Status | Select | N/A
Unfulfilled
Partially Fulfilled
Fulfilled
Lapsed |  | ✅ |  | None | None |
| `party_full_name` | Party Full Name | Data | None |  |  | ✅ | None | None |
| `sb_terms` | Contract Period | Section Break | None |  |  |  | None | None |
| `start_date` | Start Date | Date | None |  |  |  | None | None |
| `cb_date` | None | Column Break | None |  |  |  | None | None |
| `end_date` | End Date | Date | None |  |  |  | None | None |
| `sb_signee` | Signee Details | Section Break | None |  |  |  | None | None |
| `signee` | Signee | Data | None |  |  |  | None | None |
| `signed_on` | Signed On | Datetime | None |  |  |  | None | None |
| `cb_user` | None | Column Break | None |  |  |  | None | None |
| `ip_address` | IP Address | Data | None |  |  | ✅ | None | None |
| `sb_contract` | Contract Details | Section Break | None |  |  |  | None | None |
| `contract_template` | Contract Template | Link | Contract Template |  |  |  | None | None |
| `contract_terms` | Contract Terms | Text Editor | None | ✅ |  |  | None | None |
| `sb_fulfilment` | Fulfilment Details | Section Break | None |  |  |  | None | None |
| `requires_fulfilment` | Requires Fulfilment | Check | None |  |  |  | 0 | None |
| `fulfilment_deadline` | Fulfilment Deadline | Date | None |  |  |  | None | None |
| `fulfilment_terms` | Fulfilment Terms | Table | Contract Fulfilment Checklist |  |  |  | None | None |
| `authorised_by_section` | Authorised By | Section Break | None |  |  |  | None | None |
| `signee_company` | Signee (Company) | Signature | None |  |  |  | None | None |
| `signed_by_company` | Signed By (Company) | Link | User |  |  | ✅ | None | None |
| `sb_references` | References | Section Break | None |  |  |  | None | None |
| `document_type` | Document Type | Select | 
Quotation
Project
Sales Order
Purchase Order
Sales Invoice
Purchase Invoice |  |  |  | None | None |
| `cb_links` | None | Column Break | None |  |  |  | None | None |
| `document_name` | Document Name | Dynamic Link | document_type |  |  |  | None | None |
| `amended_from` | Amended From | Link | Contract |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 4
- **Dynamic Link Fields:** 2
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/crm/doctype/contract/contract.js`
```javascript
// Copyright (c) 2018, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Contract", {
	contract_template: function (frm) {
		if (frm.doc.contract_template) {
			frappe.call({
				method: "erpnext.crm.doctype.contract_template.contract_template.get_contract_template",
				args: {
					template_name: frm.doc.contract_template,
					doc: frm.doc,
				},
				callback: function (r) {
					if (r && r.message) {
						let contract_template = r.message.contract_template;
						frm.set_value("contract_terms", r.message.contract_terms);
						frm.set_value("requires_fulfilment", contract_template.requires_fulfilment);

						if (frm.doc.requires_fulfilment) {
							// Populate the fulfilment terms table from a contract template, if any
							r.message.contract_template.fulfilment_terms.forEach((element) => {
								let d = frm.add_child("fulfilment_terms");
								d.requirement = element.requirement;
							});
							frm.refresh_field("fulfilment_terms");
						}
					}
				},
			});
		}
	},
	party_name: function (frm) {
		let field = frm.doc.party_type.toLowerCase() + "_name";
		frappe.db.get_value(frm.doc.party_type, frm.doc.party_name, field, (r) => {
			frm.set_value("party_full_name", r[field]);
		});
	},
});

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
