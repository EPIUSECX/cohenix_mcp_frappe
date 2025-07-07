# Master Control Plan: `Pricing Rule`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `naming_series:`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ |
| Sales Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Purchase Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| Website Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `applicability_section` | None | Section Break | None |  |  |  | None | None |
| `naming_series` | Naming Series | Select | PRLE-.#### |  |  |  | PRLE-.#### | None |
| `title` | Title | Data | None | ✅ |  |  | None | None |
| `disable` | Disable | Check | None |  |  |  | 0 | None |
| `apply_on` | Apply On | Select | 
Item Code
Item Group
Brand
Transaction | ✅ |  |  | Item Code | None |
| `price_or_product_discount` | Price or Product Discount | Select | Price
Product | ✅ |  |  | None | None |
| `warehouse` | Warehouse | Link | Warehouse |  |  |  | None | None |
| `column_break_7` | None | Column Break | None |  |  |  | None | None |
| `items` | Apply Rule On Item Code | Table | Pricing Rule Item Code |  |  |  | None | None |
| `item_groups` | Apply Rule On Item Group | Table | Pricing Rule Item Group |  |  |  | None | None |
| `brands` | Apply Rule On Brand | Table | Pricing Rule Brand |  |  |  | None | None |
| `mixed_conditions` | Mixed Conditions | Check | None |  |  |  | 0 | Conditions will be applied on all the selected items combined.  |
| `is_cumulative` | Is Cumulative | Check | None |  |  |  | 0 | None |
| `coupon_code_based` | Coupon Code Based | Check | None |  |  |  | 0 | None |
| `section_break_18` | Discount on Other Item | Section Break | None |  |  |  | None | None |
| `apply_rule_on_other` | Apply Rule On Other | Select | 
Item Code
Item Group
Brand |  |  |  | None | None |
| `column_break_17` | None | Column Break | None |  |  |  | None | None |
| `other_item_code` | Item Code | Link | Item |  |  |  | None | None |
| `other_item_group` | Item Group | Link | Item Group |  |  |  | None | None |
| `other_brand` | Brand | Link | Brand |  |  |  | None | None |
| `section_break_7` | Party Information | Section Break | None |  |  |  | None | None |
| `selling` | Selling | Check | None |  |  |  | 0 | None |
| `buying` | Buying | Check | None |  |  |  | 0 | None |
| `column_break_11` | None | Column Break | None |  |  |  | None | None |
| `applicable_for` | Applicable For | Select | 
Customer
Customer Group
Territory
Sales Partner
Campaign
Supplier
Supplier Group |  |  |  | None | None |
| `customer` | Customer | Link | Customer |  |  |  | None | None |
| `customer_group` | Customer Group | Link | Customer Group |  |  |  | None | None |
| `territory` | Territory | Link | Territory |  |  |  | None | None |
| `sales_partner` | Sales Partner | Link | Sales Partner |  |  |  | None | None |
| `campaign` | Campaign | Link | UTM Campaign |  |  |  | None | None |
| `supplier` | Supplier | Link | Supplier |  |  |  | None | None |
| `supplier_group` | Supplier Group | Link | Supplier Group |  |  |  | None | None |
| `section_break_19` | Quantity and Amount | Section Break | None |  |  |  | None | None |
| `min_qty` | Min Qty (As Per Stock UOM) | Float | None |  |  |  | None | None |
| `max_qty` | Max Qty (As Per Stock UOM) | Float | None |  |  |  | None | None |
| `column_break_21` | None | Column Break | None |  |  |  | None | None |
| `min_amt` | Min Amt | Currency | currency |  |  |  | 0 | None |
| `max_amt` | Max Amt | Currency | currency |  |  |  | 0 | None |
| `product_discount_scheme_section` | Product Discount Scheme | Section Break | None |  |  |  | None | None |
| `same_item` | Same Item | Check | None |  |  |  | 0 | None |
| `free_item` | Free Item | Link | Item |  |  |  | None | None |
| `free_qty` | Qty | Float | None |  |  |  | 0 | None |
| `free_item_rate` | Free Item Rate | Currency | None |  |  |  | None | If rate is zero then item will be treated as "Free Item" |
| `column_break_42` | None | Column Break | None |  |  |  | None | None |
| `free_item_uom` | UOM | Link | UOM |  |  |  | None | None |
| `round_free_qty` | Round Free Qty | Check | None |  |  |  | 0 | None |
| `dont_enforce_free_item_qty` | Don't Enforce Free Item Qty | Check | None |  |  |  | 0 | None |
| `is_recursive` | Is Recursive | Check | None |  |  |  | 0 | Discounts to be applied in sequential ranges like buy 1 get 1, buy 2 get 2, buy 3 get 3 and so on |
| `recurse_for` | Recurse Every (As Per Transaction UOM) | Float | None |  |  |  | None | Give free item for every N quantity |
| `apply_recursion_over` | Apply Recursion Over (As Per Transaction UOM) | Float | None |  |  |  | 0 | Qty for which recursion isn't applicable. |
| `section_break_23` | Period Settings | Section Break | None |  |  |  | None | None |
| `valid_from` | Valid From | Date | None |  |  |  | Today | None |
| `valid_upto` | Valid Up To | Date | None |  |  |  | None | None |
| `col_break1` | None | Column Break | None |  |  |  | None | None |
| `company` | Company | Link | Company |  |  |  | None | None |
| `currency` | Currency | Link | Currency | ✅ |  |  | None | None |
| `margin` | Margin | Section Break | None |  |  |  | None | None |
| `margin_type` | Margin Type | Select | 
Percentage
Amount |  |  |  | Percentage | None |
| `column_break_33` | None | Column Break | None |  |  |  | None | None |
| `margin_rate_or_amount` | Margin Rate or Amount | Float | None |  |  |  | 0 | None |
| `price_discount_scheme_section` | Price Discount Scheme | Section Break | None |  |  |  | None | None |
| `rate_or_discount` | Rate or Discount | Select | 
Rate
Discount Percentage
Discount Amount |  |  |  | Discount Percentage | None |
| `apply_discount_on` | Apply Discount On | Select | Grand Total
Net Total |  |  |  | Grand Total | None |
| `col_break2` | None | Column Break | None |  |  |  | None | None |
| `rate` | Rate | Currency | currency |  |  |  | 0 | None |
| `discount_amount` | Discount Amount | Currency | currency |  |  |  | 0 | None |
| `discount_percentage` | Discount Percentage | Float | None |  |  |  | None | None |
| `for_price_list` | For Price List | Link | Price List |  |  |  | None | None |
| `dynamic_condition_tab` | Dynamic Condition | Tab Break | None |  |  |  | None | None |
| `condition` | Condition | Code | PythonExpression |  |  |  | None | Simple Python Expression, Example: territory != 'All Territories' |
| `section_break_13` | Advanced Settings | Tab Break | None |  |  |  | None | None |
| `apply_multiple_pricing_rules` | Apply Multiple Pricing Rules | Check | None |  |  |  | 0 | None |
| `apply_discount_on_rate` | Apply Discount on Discounted Rate | Check | None |  |  |  | 0 | None |
| `column_break_66` | None | Column Break | None |  |  |  | None | None |
| `threshold_percentage` | Threshold for Suggestion (In Percentage) | Percent | None |  |  |  | None | System will notify to increase or decrease quantity or amount  |
| `validate_pricing_rule_section` | Validate Pricing Rule | Section Break | None |  |  |  | None | None |
| `validate_applied_rule` | Validate Applied Rule | Check | None |  |  |  | 0 | If enabled, then system will only validate the pricing rule and not apply automatically. User has to manually set the discount percentage / margin / free items to validate the pricing rule |
| `column_break_texp` | None | Column Break | None |  |  |  | None | None |
| `rule_description` | Rule Description | Small Text | None |  |  |  | None | None |
| `priority_section` | Priority | Section Break | None |  |  |  | None | None |
| `has_priority` | Has Priority | Check | None |  |  |  | 0 | Enable this checkbox even if you want to set the zero priority |
| `column_break_sayg` | None | Column Break | None |  |  |  | None | None |
| `priority` | Priority | Select | 
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20 |  |  |  | None | Higher the number, higher the priority |
| `help_section` | Help Article | Tab Break | Simple |  |  |  | None | None |
| `pricing_rule_help` | Pricing Rule Help | HTML | None |  |  |  | None | None |
| `reference_section` | Reference | Section Break | None |  | ✅ |  | None | None |
| `promotional_scheme_id` | Promotional Scheme Id | Data | None |  | ✅ | ✅ | None | None |
| `promotional_scheme` | Promotional Scheme | Link | Promotional Scheme |  |  | ✅ | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 17
- **Dynamic Link Fields:** 0
- **Table Fields:** 3

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/pricing_rule/pricing_rule.js`
```javascript
// Copyright (c) 2015, Frappe Technologies Pvt. Ltd. and Contributors
// License: GNU General Public License v3. See license.txt

frappe.ui.form.on("Pricing Rule", {
	setup: function (frm) {
		frm.fields_dict["for_price_list"].get_query = function (doc) {
			return {
				filters: {
					selling: doc.selling,
					buying: doc.buying,
					currency: doc.currency,
				},
			};
		};

		["items", "item_groups", "brands"].forEach((d) => {
			frm.fields_dict[d].grid.get_field("uom").get_query = function (doc, cdt, cdn) {
				var row = locals[cdt][cdn];
				return {
					query: "erpnext.accounts.doctype.pricing_rule.pricing_rule.get_item_uoms",
					filters: { value: row[frappe.scrub(doc.apply_on)], apply_on: doc.apply_on },
				};
			};
		});
	},

	onload: function (frm) {
		if (frm.doc.__islocal && !frm.doc.applicable_for && (frm.doc.customer || frm.doc.supplier)) {
			if (frm.doc.customer) {
				frm.doc.applicable_for = "Customer";
				frm.doc.selling = 1;
			} else {
				frm.doc.applicable_for = "Supplier";
				frm.doc.buying = 1;
			}
		}
	},

	refresh: function (frm) {
		var help_content = `<table class="table table-bordered" style="background-color: var(--scrollbar-track-color);">
				<tr><td>
					<h4>
						<i class="fa fa-hand-right"></i>
						{{__('Notes')}}
					</h4>
					<ul>
						<li>
							{{__("Pricing Rule is made to overwrite Price List / define discount percentage, based on some criteria.")}}
						</li>
						<li>
							{{__("If selected Pricing Rule is made for 'Rate', it will overwrite Price List. Pricing Rule rate is the final rate, so no further discount should be applied. Hence, in transactions like Sales Order, Purchase Order etc, it will be fetched in 'Rate' field, rather than 'Price List Rate' field.")}}
						</li>
						<li>
							{{__('Discount Percentage can be applied either against a Price List or for all Price List.')}}
						</li>
						<li>
							{{__('To not apply Pricing Rule in a particular transaction, all applicable Pricing Rules should be disabled.')}}
						</li>
					</ul>
				</td></tr>
				<tr><td>
					<h4><i class="fa fa-question-sign"></i>
						{{__('How Pricing Rule is applied?')}}
					</h4>
					<ol>
						<li>
							{{__("Pricing Rule is first selected based on 'Apply On' field, which can be Item, Item Group or Brand.")}}
						</li>
						<li>
							{{__("Then Pricing Rules are filtered out based on Customer, Customer Group, Territory, Supplier, Supplier Type, Campaign, Sales Partner etc.")}}
						</li>
						<li>
							{{__('Pricing Rules are further filtered based on quantity.')}}
						</li>
						<li>
							{{__('If two or more Pricing Rules are found based on the above conditions, Priority is applied. Priority is a number between 0 to 20 while default value is zero (blank). Higher number means it will take precedence if there are multiple Pricing Rules with same conditions.')}}
						</li>
						<li>
							{{__('Even if there are multiple Pricing Rules with highest priority, then following internal priorities are applied:')}}
							<ul>
								<li>
									{{__('Item Code > Item Group > Brand')}}
								</li>
								<li>
									{{__('Customer > Customer Group > Territory')}}
								</li>
								<li>
									{{__('Supplier > Supplier Type')}}
								</li>
							</ul>
						</li>
						<li>
							{{__('If multiple Pricing Rules continue to prevail, users are asked to set Priority manually to resolve conflict.')}}
						</li>
					</ol>
				</td></tr>
			</table>`;

		frm.set_df_property("pricing_rule_help", "options", help_content);
		frm.events.set_options_for_applicable_for(frm);
		frm.trigger("toggle_reqd_apply_on");
	},

	apply_on: function (frm) {
		frm.trigger("toggle_reqd_apply_on");
	},

	toggle_reqd_apply_on: function (frm) {
		const fields = {
			"Item Code": "items",
			"Item Group": "item_groups",
			Brand: "brands",
		};

		for (var key in fields) {
			frm.toggle_reqd(fields[key], frm.doc.apply_on === key ? 1 : 0);
		}
	},

	rate_or_discount: function (frm) {
		if (frm.doc.rate_or_discount == "Rate") {
			frm.set_value("for_price_list", "");
		}
	},

	selling: function (frm) {
		frm.events.set_options_for_applicable_for(frm);
	},

	buying: function (frm) {
		frm.events.set_options_for_applicable_for(frm);
	},

	//Dynamically change the description based on type of margin
	margin_type: function (frm) {
		frm.set_df_property(
			"margin_rate_or_amount",
			"description",
			frm.doc.margin_type == "Percentage" ? "In Percentage %" : "In Amount"
		);
	},

	set_options_for_applicable_for: function (frm) {
		var options = [""];
		var applicable_for = frm.doc.applicable_for;

		if (frm.doc.selling) {
			options = $.merge(options, [
				"Customer",
				"Customer Group",
				"Territory",
				"Sales Partner",
				"Campaign",
			]);
		}
		if (frm.doc.buying) {
			$.merge(options, ["Supplier", "Supplier Group"]);
		}

		set_field_options("applicable_for", options.join("\n"));

		if (!in_list(options, applicable_for)) applicable_for = null;
		frm.set_value("applicable_for", applicable_for);
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
