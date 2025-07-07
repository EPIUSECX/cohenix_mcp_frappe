# Master Control Plan: `Client Script`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Custom`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** Adds a custom client script to a DocType

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Administrator | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `dt` | DocType | Link | DocType | ✅ |  |  | None | None |
| `view` | Apply To | Select | List
Form |  |  |  | Form | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `module` | Module (for export) | Link | Module Def |  |  |  | None | None |
| `enabled` | Enabled | Check | None |  |  |  | 0 | None |
| `section_break_6` | None | Section Break | None |  |  |  | None | None |
| `script` | Script | Code | JS |  |  |  | None | None |
| `sample` | Sample | HTML | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/custom/doctype/client_script/client_script.js`
```javascript
// Copyright (c) 2016, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Client Script", {
	setup(frm) {
		frm.get_field("sample").html(SAMPLE_HTML);
	},
	refresh(frm) {
		if (frm.doc.dt && frm.doc.script) {
			frm.add_custom_button(__("Go to {0}", [frm.doc.dt]), () =>
				frappe.set_route("List", frm.doc.dt, "List")
			);
		}

		if (frm.doc.view == "Form") {
			frm.add_custom_button(__("Add script for Child Table"), () => {
				frappe.model.with_doctype(frm.doc.dt, () => {
					const child_tables = frappe.meta
						.get_docfields(frm.doc.dt, null, {
							fieldtype: ["in", ["Table", "Table MultiSelect"]],
						})
						.map((df) => df.options);

					const d = new frappe.ui.Dialog({
						title: __("Select Child Table"),
						fields: [
							{
								label: __("Select Child Table"),
								fieldtype: "Link",
								fieldname: "cdt",
								options: "DocType",
								get_query: () => {
									return {
										filters: {
											istable: 1,
											name: ["in", child_tables],
										},
									};
								},
							},
						],
						primary_action: ({ cdt }) => {
							cdt = d.get_field("cdt").value;
							frm.events.add_script_for_doctype(frm, cdt);
							d.hide();
						},
					});

					d.show();
				});
			});

			if (!frm.is_new()) {
				frm.add_custom_button(__("Compare Versions"), () => {
					new frappe.ui.DiffView("Client Script", "script", frm.doc.name);
				});
			}
		}

		frm.set_query("dt", {
			filters: {
				istable: 0,
			},
		});
	},

	dt(frm) {
		frm.toggle_display("view", !frappe.boot.single_types.includes(frm.doc.dt));

		if (!frm.doc.script) {
			frm.events.add_script_for_doctype(frm, frm.doc.dt);
		}

		if (frm.doc.script && !frm.doc.script.includes(frm.doc.dt)) {
			frm.doc.script = "";
			frm.events.add_script_for_doctype(frm, frm.doc.dt);
		}
	},

	view(frm) {
		let has_form_boilerplate = frm.doc.script.includes("frappe.ui.form.on");
		if (frm.doc.view === "List" && has_form_boilerplate) {
			frm.set_value("script", "");
		}
		if (frm.doc.view === "Form" && !has_form_boilerplate) {
			frm.trigger("dt");
		}
	},

	add_script_for_doctype(frm, doctype) {
		if (!doctype) return;
		let boilerplate = `
frappe.ui.form.on('${doctype}', {
	refresh(frm) {
		// your code here
	}
})
		`.trim();
		let script = frm.doc.script || "";
		if (script) {
			script += "\n\n";
		}
		frm.set_value("script", script + boilerplate);
	},
});

const SAMPLE_HTML = `<h3>Client Script Help</h3>
<p>Client Scripts are executed only on the client-side (i.e. in Forms). Here are some examples to get you started</p>
<pre><code>

// fetch local_tax_no on selection of customer
// cur_frm.add_fetch(link_field,  source_fieldname,  target_fieldname);
cur_frm.add_fetch("customer",  "local_tax_no',  'local_tax_no');

// additional validation on dates
frappe.ui.form.on('Task',  'validate',  function(frm) {
    if (frm.doc.from_date &lt; get_today()) {
        msgprint('You can not select past date in From Date');
        validated = false;
    }
});

// make a field read-only after saving
frappe.ui.form.on('Task',  {
    refresh: function(frm) {
        // use the __islocal value of doc,  to check if the doc is saved or not
        frm.set_df_property('myfield',  'read_only',  frm.doc.__islocal ? 0 : 1);
    }
});

// additional permission check
frappe.ui.form.on('Task',  {
    validate: function(frm) {
        if(user=='user1@example.com' &amp;&amp; frm.doc.purpose!='Material Receipt') {
            msgprint('You are only allowed Material Receipt');
            validated = false;
        }
    }
});

// calculate sales incentive
frappe.ui.form.on('Sales Invoice',  {
    validate: function(frm) {
        // calculate incentives for each person on the deal
        total_incentive = 0
        $.each(frm.doc.sales_team,  function(i,  d) {
            // calculate incentive
            var incentive_percent = 2;
            if(frm.doc.base_grand_total &gt; 400) incentive_percent = 4;
            // actual incentive
            d.incentives = flt(frm.doc.base_grand_total) * incentive_percent / 100;
            total_incentive += flt(d.incentives)
        });
        frm.doc.total_incentive = total_incentive;
    }
})

</code></pre>`;

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
