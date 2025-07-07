# Master Control Plan: `Inventory Dimension`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:dimension_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `dimension_details_tab` | Dimension Details | Tab Break | None |  |  |  | None | None |
| `dimension_name` | Dimension Name | Data | None | ✅ |  |  | None | None |
| `reference_document` | Reference Document | Link | DocType | ✅ |  |  | None | None |
| `column_break_4` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `field_mapping_section` | Field Mapping | Section Break | None |  | ✅ |  | None | None |
| `source_fieldname` | Source Fieldname | Data | None |  |  | ✅ | None | None |
| `column_break_9` | None | Column Break | None |  |  |  | None | None |
| `target_fieldname` | Target Fieldname (Stock Ledger Entry) | Data | None |  |  | ✅ | None | None |
| `applicable_for_documents_tab` | Applicable For | Tab Break | None |  |  |  | None | None |
| `apply_to_all_doctypes` | Apply to All Inventory Documents | Check | None |  |  |  | 1 | None |
| `column_break_niy2u` | None | Column Break | None |  |  |  | None | None |
| `validate_negative_stock` | Validate Negative Stock | Check | None |  |  |  | 0 | None |
| `column_break_13` | None | Section Break | None |  |  |  | None | None |
| `document_type` | Apply to Document | Link | DocType |  |  |  | None | None |
| `type_of_transaction` | Type of Transaction | Select | 
Inward
Outward
Both |  |  |  | None | None |
| `fetch_from_parent` | Fetch Value From | Select | None |  |  |  | None | Set fieldname from which you want to fetch the data from the parent form. |
| `istable` |  Is Child Table | Check | None |  | ✅ | ✅ | 0 | None |
| `applicable_condition_example_section` | None | Column Break | None |  |  |  | None | None |
| `condition` | Conditional Rule | Code | None |  |  |  | None | None |
| `conditional_mandatory_section` | Mandatory Section | Section Break | None |  |  |  | None | None |
| `reqd` | Mandatory | Check | None |  |  |  | 0 | None |
| `mandatory_depends_on` | Mandatory Depends On | Small Text | None |  |  |  | None | To apply condition on parent field use parent.field_name and to apply condition on child table use doc.field_name. Here field_name could be based on the actual column name of the respective field. |
| `conditional_rule_examples_section` | Conditional Rule Examples | Section Break | None |  |  |  | None | None |
| `html_19` | None | HTML | <table class="table table-bordered table-condensed">
<thead>
  <tr>
         <th class="table-sr" style="width: 50%;">Child Document</th>
         <th class="table-sr" style="width: 50%;">Non Child Document</th>
   </tr>
</thead>
<tbody>
<tr>
         <td>
                  <p> To access parent document field use parent.fieldname and to access child table document field use doc.fieldname </p>

         </td>
         <td>
                    <p>To access document field use doc.fieldname </p>
         </td>
</tr>
<tr>
        <td>
                   <p><b>Example: </b> parent.doctype == "Stock Entry" and doc.item_code == "Test" </p>

        </td>
         <td>
                   <p><b>Example: </b> doc.doctype == "Stock Entry" and doc.purpose == "Manufacture"</p>    
          </td>
</tr>

</tbody>
</table>






 |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 2
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/inventory_dimension/inventory_dimension.js`
```javascript
// Copyright (c) 2022, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Inventory Dimension", {
	setup(frm) {
		frm.trigger("set_query_on_fields");
	},

	set_query_on_fields(frm) {
		frm.set_query("reference_document", () => {
			let invalid_doctypes = frappe.model.core_doctypes_list;
			invalid_doctypes.push(
				"Batch",
				"Serial No",
				"Warehouse",
				"Item",
				"Inventory Dimension",
				"Accounting Dimension",
				"Accounting Dimension Filter"
			);

			return {
				filters: {
					istable: 0,
					issingle: 0,
					name: ["not in", invalid_doctypes],
				},
			};
		});

		frm.set_query("document_type", () => {
			return {
				query: "erpnext.stock.doctype.inventory_dimension.inventory_dimension.get_inventory_documents",
			};
		});
	},

	onload(frm) {
		frm.trigger("render_traget_field");
		frm.trigger("set_parent_fields");
	},

	refresh(frm) {
		if (
			frm.doc.__onload &&
			frm.doc.__onload.has_stock_ledger &&
			frm.doc.__onload.has_stock_ledger.length
		) {
			let allow_to_edit_fields = [
				"disabled",
				"fetch_from_parent",
				"type_of_transaction",
				"condition",
				"mandatory_depends_on",
				"validate_negative_stock",
			];

			frm.fields.forEach((field) => {
				if (!in_list(allow_to_edit_fields, field.df.fieldname)) {
					frm.set_df_property(field.df.fieldname, "read_only", "1");
				}
			});
		}

		if (!frm.is_new()) {
			frm.add_custom_button(__("Delete Dimension"), () => {
				frm.trigger("delete_dimension");
			});
		}
	},

	document_type(frm) {
		frm.trigger("set_parent_fields");
	},

	set_parent_fields(frm) {
		if (frm.doc.apply_to_all_doctypes) {
			frm.set_df_property("fetch_from_parent", "options", frm.doc.reference_document);
		} else if (frm.doc.document_type && frm.doc.istable) {
			frappe.call({
				method: "erpnext.stock.doctype.inventory_dimension.inventory_dimension.get_parent_fields",
				args: {
					child_doctype: frm.doc.document_type,
					dimension_name: frm.doc.reference_document,
				},
				callback: (r) => {
					if (r.message && r.message.length) {
						frm.set_df_property("fetch_from_parent", "options", [""].concat(r.message));
					} else {
						frm.set_df_property("fetch_from_parent", "hidden", 1);
					}
				},
			});
		}
	},

	delete_dimension(frm) {
		let msg = `
			Custom fields related to this dimension will be deleted on deletion of dimension.
			<br> Do you want to delete {0} dimension?
		`;

		frappe.confirm(__(msg, [frm.doc.name.bold()]), () => {
			frappe.call({
				method: "erpnext.stock.doctype.inventory_dimension.inventory_dimension.delete_dimension",
				args: {
					dimension: frm.doc.name,
				},
				callback: function () {
					frappe.set_route("List", "Inventory Dimension");
				},
			});
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
