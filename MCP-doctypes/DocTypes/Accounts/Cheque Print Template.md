# Master Control Plan: `Cheque Print Template`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Accounts`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `field:bank_name`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Accounts User | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `settings` | None | HTML | <div>
<h3> All dimensions in centimeter only </h3>
</div> |  |  |  | None | None |
| `has_print_format` | Has Print Format | Check | None |  | ✅ | ✅ | 0 | None |
| `primary_settings` | Primary Settings | Section Break | None |  |  |  | None | None |
| `bank_name` | Bank Name | Data | None | ✅ |  |  | None | None |
| `cheque_size` | Cheque Size | Select | 
Regular
A4 |  |  |  | Regular | None |
| `starting_position_from_top_edge` | Starting position from top edge | Float | None |  |  |  | None | None |
| `cheque_width` | Cheque Width | Float | None |  |  |  | 20.00 | None |
| `cheque_height` | Cheque Height | Float | None |  |  |  | 9.00 | None |
| `scanned_cheque` | Scanned Cheque | Attach | None |  |  |  | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `is_account_payable` | Is Account Payable | Check | None |  |  |  | 1 | None |
| `acc_pay_dist_from_top_edge` | Distance from top edge | Float | None |  |  |  | 1.00 | None |
| `acc_pay_dist_from_left_edge` | Distance from left edge | Float | None |  |  |  | 9.00 | None |
| `message_to_show` | Message to show | Data | None |  |  |  | Acc. Payee | None |
| `date_and_payer_settings` | None | Section Break | None |  |  |  | None | None |
| `date_settings` | Date Settings | HTML | <label class="control-label" style="margin-bottom: 0px;">Date Settings</label> |  |  |  | None | None |
| `date_dist_from_top_edge` | Distance from top edge | Float | None |  |  |  | 1.00 | None |
| `date_dist_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 15.00 | None |
| `payer_settings` | Payer Settings | Column Break | None |  |  |  | None | None |
| `payer_name_from_top_edge` | Distance from top edge | Float | None |  |  |  | 2.00 | None |
| `payer_name_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 3.00 | None |
| `amount_in_words_and_figure_settings` | None | Section Break | None |  |  |  | None | None |
| `html_19` | None | HTML | <label class="control-label" style="margin-bottom: 0px;">Amount In Words</label> |  |  |  | None | None |
| `amt_in_words_from_top_edge` | Distance from top edge | Float | None |  |  |  | 3.00 | None |
| `amt_in_words_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 4.00 | None |
| `amt_in_word_width` | Width of amount in word | Float | None |  |  |  | 15.00 | None |
| `amt_in_words_line_spacing` | Line spacing for amount in words | Float | None |  |  |  | 0.50 | None |
| `amount_in_figure` | Amount In Figure | Column Break | None |  |  |  | None | None |
| `amt_in_figures_from_top_edge` | Distance from top edge | Float | None |  |  |  | 3.50 | None |
| `amt_in_figures_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 16.00 | None |
| `account_number_and_signatory_settings` | None | Section Break | None |  |  |  | None | None |
| `account_no_settings` | None | HTML | <label class="control-label" style="margin-bottom: 0px;">Account Number Settings</label> |  |  |  | None | None |
| `acc_no_dist_from_top_edge` | Distance from top edge | Float | None |  |  |  | 5.00 | None |
| `acc_no_dist_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 4.00 | None |
| `signatory_position` | Signatory Position | Column Break | None |  |  |  | None | None |
| `signatory_from_top_edge` | Distance from top edge | Float | None |  |  |  | 6.00 | None |
| `signatory_from_left_edge` | Starting location from left edge | Float | None |  |  |  | 15.00 | None |
| `preview` | Preview | Section Break | None |  |  |  | None | None |
| `cheque_print_preview` | None | HTML | None |  |  |  | None | None |


### Custom Fields
No custom fields found.


### Links & Relationships
- **Link Fields:** 0
- **Dynamic Link Fields:** 0
- **Table Fields:** 0

## 2. Server-Side Controller (`.py`)
Could not get document class.


## 3. Client-Side Scripts (`.js` & Custom Script)
### File-Based Script
**Path:** `/workspace/cohenix-bench/apps/erpnext/erpnext/accounts/doctype/cheque_print_template/cheque_print_template.js`
```javascript
// Copyright (c) 2016, Frappe Technologies Pvt. Ltd. and contributors
// For license information, please see license.txt

frappe.provide("erpnext.cheque_print");

frappe.ui.form.on("Cheque Print Template", {
	refresh: function (frm) {
		if (!frm.doc.__islocal) {
			frm.add_custom_button(
				frm.doc.has_print_format ? __("Update Print Format") : __("Create Print Format"),
				function () {
					erpnext.cheque_print.view_cheque_print(frm);
				}
			).addClass("btn-primary");

			$(frm.fields_dict.cheque_print_preview.wrapper).empty();

			var template =
				'<div style="position: relative; overflow-x: scroll;">\
				<div id="cheque_preview" style="width: {{ cheque_width }}cm; \
					height: {{ cheque_height }}cm;\
					background-repeat: no-repeat;\
					background-size: cover;">\
					<span style="top: {{ acc_pay_dist_from_top_edge }}cm;\
						left: {{ acc_pay_dist_from_left_edge }}cm;\
						border-bottom: solid 1px;border-top:solid 1px;\
						position: absolute;"> {{ message_to_show || __("Account Pay Only") }} </span>\
					<span style="top: {{ date_dist_from_top_edge }}cm;\
						left: {{ date_dist_from_left_edge }}cm;\
						position: absolute;"> {{ frappe.datetime.obj_to_user() }} </span>\
					<span style="top: {{ acc_no_dist_from_top_edge }}cm;\
						left: {{ acc_no_dist_from_left_edge }}cm;\
						position: absolute;"> Acc. No. </span>\
					<span style="top: {{ payer_name_from_top_edge }}cm;\
						left: {{ payer_name_from_left_edge }}cm;\
						position: absolute;"> Payer Name </span>\
					<span style="top:{{ amt_in_words_from_top_edge }}cm;\
						left: {{ amt_in_words_from_left_edge }}cm;\
						position: absolute;\
						display: block;\
						width: {{ amt_in_word_width }}cm;\
						line-height: {{ amt_in_words_line_spacing }}cm;\
						word-wrap: break-word;"> Amount in Words </span>\
					<span style="top: {{ amt_in_figures_from_top_edge }}cm;\
						left: {{ amt_in_figures_from_left_edge }}cm;\
						position: absolute;"> 1000 </span>\
					<span style="top: {{ signatory_from_top_edge }}cm;\
						left: {{ signatory_from_left_edge }}cm;\
						position: absolute;"> Signatory Name </span>\
				</div>\
			</div>';

			$(frappe.render(template, frm.doc)).appendTo(frm.fields_dict.cheque_print_preview.wrapper);

			if (frm.doc.scanned_cheque) {
				$(frm.fields_dict.cheque_print_preview.wrapper)
					.find("#cheque_preview")
					.css("background-image", "url(" + frm.doc.scanned_cheque + ")");
			}
		}
	},
});

erpnext.cheque_print.view_cheque_print = function (frm) {
	frappe.call({
		method: "erpnext.accounts.doctype.cheque_print_template.cheque_print_template.create_or_update_cheque_print_format",
		args: {
			template_name: frm.doc.name,
		},
		callback: function (r) {
			if (!r.exe && !frm.doc.has_print_format) {
				var doc = frappe.model.sync(r.message);
				frappe.set_route("Form", r.message.doctype, r.message.name);
			} else {
				frappe.msgprint(__("Print settings updated in respective print format"));
			}
		},
	});
};

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
