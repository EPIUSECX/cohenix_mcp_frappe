# Master Control Plan: `Item Variant Settings`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Stock`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Item Manager | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `section_break_3` | None | Section Break | None |  |  |  | None | None |
| `do_not_update_variants` | Do not update variants on save | Check | None |  |  |  | 0 | Fields will be copied over only at time of creation. |
| `allow_rename_attribute_value` | Allow Rename Attribute Value | Check | None |  |  |  | 0 | Rename Attribute Value in Item Attribute. |
| `allow_different_uom` | Allow Variant UOM to be different from Template UOM | Check | None |  |  |  | 0 | None |
| `copy_fields_to_variant` | Copy Fields to Variant | Section Break | None |  |  |  | None | None |
| `fields` | Fields | Table | Variant Field |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/stock/doctype/item_variant_settings/item_variant_settings.js`
```javascript
// Copyright (c) 2017, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.ui.form.on("Item Variant Settings", {
	refresh: function (frm) {
		const allow_fields = [];

		const existing_fields = frm.doc.fields.map((row) => row.field_name);
		const exclude_fields = [
			...existing_fields,
			"naming_series",
			"item_code",
			"item_name",
			"published_in_website",
			"standard_rate",
			"opening_stock",
			"image",
			"variant_of",
			"valuation_rate",
			"barcodes",
			"has_variants",
			"attributes",
		];

		const exclude_field_types = ["HTML", "Section Break", "Column Break", "Button", "Read Only"];

		frappe.model.with_doctype("Item", () => {
			const field_label_map = {};
			frappe.get_meta("Item").fields.forEach((d) => {
				field_label_map[d.fieldname] = __(d.label, null, d.parent) + ` (${d.fieldname})`;

				if (
					!in_list(exclude_field_types, d.fieldtype) &&
					!d.no_copy &&
					!in_list(exclude_fields, d.fieldname)
				) {
					allow_fields.push({
						label: field_label_map[d.fieldname],
						value: d.fieldname,
					});
				}
			});

			if (allow_fields.length == 0) {
				allow_fields.push({
					label: __("No additional fields available"),
					value: "",
				});
			}

			frm.fields_dict.fields.grid.update_docfield_property("field_name", "options", allow_fields);
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
