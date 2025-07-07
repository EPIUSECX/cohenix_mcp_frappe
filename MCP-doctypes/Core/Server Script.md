# Master Control Plan: `Server Script`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `Prompt`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Script Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `script_type` | Script Type | Select | DocType Event
Scheduler Event
Permission Query
API | ✅ |  |  | None | None |
| `reference_doctype` | Reference Document Type | Link | DocType |  |  |  | None | None |
| `event_frequency` | Event Frequency | Select | All
Hourly
Daily
Weekly
Monthly
Yearly
Hourly Long
Daily Long
Weekly Long
Monthly Long
Cron |  |  |  | None | None |
| `cron_format` | Cron Format | Data | None |  |  |  | None | <pre>*  *  *  *  *
┬  ┬  ┬  ┬  ┬
│  │  │  │  │
│  │  │  │  └ day of week (0 - 6) (0 is Sunday)
│  │  │  └───── month (1 - 12)
│  │  └────────── day of month (1 - 31)
│  └─────────────── hour (0 - 23)
└──────────────────── minute (0 - 59)

---

* - Any value
/ - Step values
</pre>
 |
| `doctype_event` | DocType Event | Select | Before Insert
Before Validate
Before Save
After Insert
After Save
Before Rename
After Rename
Before Submit
After Submit
Before Cancel
After Cancel
Before Discard
After Discard
Before Delete
After Delete
Before Save (Submitted Document)
After Save (Submitted Document)
Before Print
On Payment Authorization
On Payment Paid
On Payment Failed
On Payment Charge Processed
On Payment Mandate Charge Processed
On Payment Mandate Acquisition Processed |  |  |  | None | None |
| `api_method` | API Method | Data | None |  |  |  | None | None |
| `allow_guest` | Allow Guest | Check | None |  |  |  | 0 | None |
| `column_break_3` | None | Column Break | None |  |  |  | None | None |
| `module` | Module (for export) | Link | Module Def |  |  |  | None | None |
| `disabled` | Disabled | Check | None |  |  |  | 0 | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `script` | Script | Code | Python | ✅ |  |  | None | None |
| `rate_limiting_section` | Rate Limiting | Section Break | None |  |  |  | None | None |
| `enable_rate_limit` | Enable Rate Limit | Check | None |  |  |  | 0 | None |
| `rate_limit_count` | Request Limit | Int | None |  |  |  | 5 | None |
| `rate_limit_seconds` | Time Window (Seconds) | Int | None |  |  |  | 86400 | None |
| `help_section` | Help | Section Break | None |  |  |  | None | None |
| `help_html` | None | HTML | None |  |  |  | None | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/server_script/server_script.js`
```javascript
// Copyright (c) 2019, Frappe Technologies and contributors
// For license information, please see license.txt

frappe.ui.form.on("Server Script", {
	setup: function (frm) {
		frm.trigger("setup_help");
	},
	refresh: function (frm) {
		if (frm.doc.script_type != "Scheduler Event") {
			frm.dashboard.hide();
		}

		if (!frm.is_new()) {
			frm.add_custom_button(__("Compare Versions"), () => {
				new frappe.ui.DiffView("Server Script", "script", frm.doc.name);
			});
		}

		setTimeout(() => {
			frappe
				.call("frappe.core.doctype.server_script.server_script.get_autocompletion_items")
				.then((r) => r.message)
				.then((items) => {
					frm.set_df_property("script", "autocompletions", items);
				});
		}, 100);

		frm.trigger("check_safe_exec");
	},

	check_safe_exec(frm) {
		frappe.xcall("frappe.core.doctype.server_script.server_script.enabled").then((enabled) => {
			if (enabled === false) {
				let docs_link =
					"https://frappeframework.com/docs/user/en/desk/scripting/server-script";
				let docs = `<a href=${docs_link}>${__("Official Documentation")}</a>`;

				frm.dashboard.clear_comment();
				let msg = __("Server Scripts feature is not available on this site.") + " ";
				msg += __("To enable server scripts, read the {0}.", [docs]);
				frm.dashboard.add_comment(msg, "yellow", true);
			}
		});
	},

	setup_help(frm) {
		frm.get_field("help_html").html(`
<h4>DocType Event</h4>
<p>Add logic for standard doctype events like Before Insert, After Submit, etc.</p>
<pre>
	<code>
# set property
if "test" in doc.description:
	doc.status = 'Closed'


# validate
if "validate" in doc.description:
	raise frappe.ValidationError

# auto create another document
if doc.allocated_to:
	frappe.get_doc(dict(
		doctype = 'ToDo'
		owner = doc.allocated_to,
		description = doc.subject
	)).insert()
</code>
</pre>

<h5>Payment processing</h5>
<p>Payment processing events have a special state. See the <a href="https://github.com/frappe/payments/blob/develop/payments/controllers/payment_controller.py">PaymentController in Frappe Payments</a> for details.</p>
<pre>
	<code>
# retreive payment session state
ps = doc.flags.payment_session

if ps.is_success:
	if ps.changed: # could be an idempotent run
		doc.set_as_paid()
	# custom process return values
	doc.flags.payment_session.result = {
		"message": "Thank you for your payment",
		"action": {"href": "https://shop.example.com", "label": "Return to shop"},
	}
if ps.is_pre_authorized:
	if ps.changed: # could be an idempotent run
		...
if ps.is_processing:
	if ps.changed: # could be an idempotent run
		...
if ps.is_declined:
	if ps.changed: # could be an idempotent run
		...
</code>
</pre>
<p>The <i>On Payment Failed</i> (<code>on_payment_failed</code>) event only transports the error message which the controller implementation had extracted from the transaction.</p>
<pre>
	<code>
msg = doc.flags.payment_failure_message
doc.my_failure_message_field = msg
</code>
</pre>

<hr>

<h4>API Call</h4>
<p>Respond to <code>/api/method/&lt;method-name&gt;</code> calls, just like whitelisted methods</p>
<pre><code>
# respond to API

if frappe.form_dict.message == "ping":
	frappe.response['message'] = "pong"
else:
	frappe.response['message'] = "ok"
</code></pre>

<hr>

<h4>Permission Query</h4>
<p>Add conditions to the where clause of list queries.</p>
<pre><code>
# generate dynamic conditions and set it in the conditions variable
tenant_id = frappe.db.get_value(...)
conditions = f'tenant_id = {tenant_id}'

# resulting select query
select name from \`tabPerson\`
where tenant_id = 2
order by creation desc
</code></pre>
`);
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
