# Master Control Plan: `Quality Inspection`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `1`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Quality Manager | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `naming_series` | Series | Select | MAT-QA-.YYYY.- | ✅ |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `report_date` | Report Date | Date | None | ✅ |  |  | Today | None |
| `status` | Status | Select | 
Accepted
Rejected | ✅ |  |  | Accepted | None |
| `child_row_reference` | Child Row Reference | Data | None |  | ✅ | ✅ | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `inspection_type` | Inspection Type | Select | 
Incoming
Outgoing
In Process | ✅ |  |  | None | None |
| `reference_type` | Reference Type | Select | 
Purchase Receipt
Purchase Invoice
Subcontracting Receipt
Delivery Note
Sales Invoice
Stock Entry
Job Card | ✅ |  |  | None | None |
| `reference_name` | Reference Name | Dynamic Link | reference_type | ✅ |  |  | None | None |
| `section_break_7` | None | Section Break | None |  |  |  | None | None |
| `item_code` | Item Code | Link | Item | ✅ |  |  | None | None |
| `item_serial_no` | Item Serial No | Link | Serial No |  |  |  | None | None |
| `batch_no` | Batch No | Link | Batch |  |  |  | None | None |
| `sample_size` | Sample Size | Float | None | ✅ |  |  | None | None |
| `column_break1` | None | Column Break | None |  |  |  | None | None |
| `item_name` | Item Name | Data | None |  |  | ✅ | None | None |
| `description` | Description | Small Text | None |  |  |  | None | None |
| `bom_no` | BOM No | Link | BOM |  |  | ✅ | None | None |
| `specification_details` | None | Section Break | Simple |  |  |  | None | None |
| `quality_inspection_template` | Quality Inspection Template | Link | Quality Inspection Template |  |  |  | None | None |
| `manual_inspection` | Manual Inspection | Check | None |  |  |  | 0 | None |
| `readings` | Readings | Table | Quality Inspection Reading |  |  |  | None | None |
| `section_break_14` | None | Section Break | None |  |  |  | None | None |
| `inspected_by` | Inspected By | Link | User | ✅ |  |  | user | None |
| `verified_by` | Verified By | Data | None |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `remarks` | Remarks | Text | None |  |  |  | None | None |
| `amended_from` | Amended From | Link | Quality Inspection |  |  | ✅ | None | None |
| `print_settings_section` | Print Settings | Section Break | None |  |  |  | None | None |
| `letter_head` | Letter Head | Link | Letter Head |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 9
- **Dynamic Link Fields:** 1
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/quality_inspection/quality_inspection.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

cur_frm.cscript.refresh = cur_frm.cscript.inspection_type;

frappe.ui.form.on("Quality Inspection", {
	onload(frm) {
		frm.trigger("set_default_company");
	},

	set_default_company(frm) {
		if (!frm.doc.company) {
			frm.set_value("company", frappe.defaults.get_default("company"));
		}
	},

	setup: function (frm) {
		frm.set_query("reference_name", function (doc) {
			let filters = { docstatus: ["!=", 2] };

			if (doc.company) {
				filters["company"] = doc.company;
			}

			return {
				filters: filters,
			};
		});

		frm.set_query("batch_no", function () {
			return {
				filters: {
					item: frm.doc.item_code,
				},
			};
		});

		// Serial No based on item_code
		frm.set_query("item_serial_no", function () {
			let filters = {};
			if (frm.doc.item_code) {
				filters = {
					item_code: frm.doc.item_code,
				};
			}
			return { filters: filters };
		});

		// item code based on GRN/DN
		frm.set_query("item_code", function (doc) {
			let doctype = doc.reference_type;

			if (doc.reference_type !== "Job Card") {
				doctype =
					doc.reference_type == "Stock Entry" ? "Stock Entry Detail" : doc.reference_type + " Item";
			}

			if (doc.reference_type && doc.reference_name) {
				let filters = {
					from: doctype,
					inspection_type: doc.inspection_type,
				};

				if (doc.reference_type == doctype) filters["reference_name"] = doc.reference_name;
				else filters["parent"] = doc.reference_name;

				return {
					query: "erpnext.stock.doctype.quality_inspection.quality_inspection.item_query",
					filters: filters,
				};
			}
		});
	},

	refresh: function (frm) {
		// Ignore cancellation of reference doctype on cancel all.
		frm.ignore_doctypes_on_cancel_all = [frm.doc.reference_type, "Serial and Batch Bundle"];
	},

	item_code: function (frm) {
		if (frm.doc.item_code && !frm.doc.quality_inspection_template) {
			return frm.call({
				method: "get_quality_inspection_template",
				doc: frm.doc,
				callback: function () {
					refresh_field(["quality_inspection_template", "readings"]);
				},
			});
		}
	},

	quality_inspection_template: function (frm) {
		if (frm.doc.quality_inspection_template) {
			return frm.call({
				method: "get_item_specification_details",
				doc: frm.doc,
				callback: function () {
					refresh_field("readings");
				},
			});
		}
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Quality Inspection Summary` | Script Report | Manufacturing |



### Dashboard Charts
No dashboard charts found.


### Number Cards
| Name | Label | Function | Module |
|---|---|---|---|
| `Monthly Quality Inspection` | Monthly Quality Inspections | Count | Manufacturing |



## 6. System Automations
### Email Alerts
No enabled email alerts found.


### Notifications
No enabled notifications found.


### Webhooks
No enabled webhooks found.
