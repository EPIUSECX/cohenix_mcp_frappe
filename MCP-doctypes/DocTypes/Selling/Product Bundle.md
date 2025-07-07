# Master Control Plan: `Product Bundle`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Selling`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** Aggregate a group of Items into another Item. This is useful if you are maintaining the stock of the packed items and not the bundled item

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Stock Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Stock User | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| Sales User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `basic_section` | None | Section Break | None |  |  |  | None | None |
| `new_item_code` | Parent Item | Link | Item | ✅ |  |  | None | None |
| `description` | Description | Data | None |  |  |  | None | None |
| `column_break_eonk` | None | Column Break | None |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `item_section` | Items | Section Break | None |  |  |  | None | List items that form the package. |
| `items` | Items | Table | Product Bundle Item | ✅ |  |  | None | None |
| `section_break_4` | None | Section Break | None |  |  |  | None | None |
| `about` | None | HTML | <h3>About Product Bundle</h3>

<p>Aggregate group of <b>Items</b> into another <b>Item</b>. This is useful if you are bundling a certain <b>Items</b> into a package and you maintain stock of the packed <b>Items</b> and not the aggregate <b>Item</b>.</p>
<p>The package <b>Item</b> will have <code>Is Stock Item</code> as <b>No</b> and <code>Is Sales Item</code> as <b>Yes</b>.</p>
<h4>Example:</h4>
<p>If you are selling Laptops and Backpacks separately and have a special price if the customer buys both, then the Laptop + Backpack will be a new Product Bundle Item.</p> |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 1
- **Dynamic Link Fields:** 0
- **Table Fields:** 1

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/selling/doctype/product_bundle/product_bundle.js`
```javascript
// Copyright (c) 2021, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Product Bundle", {
	refresh: function (frm) {
		frm.toggle_enable("new_item_code", frm.is_new());
		frm.set_query("new_item_code", () => {
			return {
				query: "erpnext.selling.doctype.product_bundle.product_bundle.get_new_item_code",
			};
		});
	},
});

```




## 4. Workflow Automation
No active workflows found for this DocType.


## 5. Reports & Analytics
### Linked Reports
| Name | Type | Module |
|---|---|---|
| `Available Stock for Packing Items` | Script Report | Selling |



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
