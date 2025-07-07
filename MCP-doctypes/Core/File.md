# Master Control Plan: `File`

## 1. Doctype Schema & Metadata

### Core Properties
- **Module:** `Core`
- **Custom:** `0`
- **Is Table:** `0`
- **Is Submittable:** `0`
- **Autoname:** `None`
- **Description:** None

### Permissions
| Role | Read | Write | Create | Delete | Submit | Cancel | Amend | Report | Import | Export | Print | Email | Share | Set User Perms |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| System Manager | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| All | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Employee Self Service | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |


### Fields (Standard)
| Fieldname | Label | Type | Options | Required | Hidden | Read Only | Default | Description |
|---|---|---|---|---|---|---|---|---|
| `file_name` | File Name | Data | None |  |  | ✅ | None | None |
| `is_private` | Is Private | Check | None |  |  |  | 0 | None |
| `column_break_7jmm` | None | Column Break | None |  |  |  | None | None |
| `file_type` | File Type | Data | None |  |  | ✅ | None | None |
| `preview` | Preview | Section Break | None |  |  |  | None | None |
| `preview_html` | Preview HTML | HTML | None |  |  |  | None | None |
| `section_break_5` | None | Section Break | None |  |  |  | None | None |
| `is_home_folder` | Is Home Folder | Check | None |  | ✅ |  | 0 | None |
| `is_attachments_folder` | Is Attachments Folder | Check | None |  | ✅ |  | 0 | None |
| `file_size` | File Size | Int | File Size |  |  | ✅ | None | None |
| `column_break_5` | None | Column Break | None |  |  |  | None | None |
| `file_url` | File URL | Code | None |  |  | ✅ | None | None |
| `thumbnail_url` | Thumbnail URL | Small Text | None |  |  | ✅ | None | None |
| `folder` | Folder | Link | File |  | ✅ | ✅ | None | None |
| `is_folder` | Is Folder | Check | None |  |  | ✅ | 0 | None |
| `section_break_8` | None | Section Break | None |  |  |  | None | None |
| `attached_to_doctype` | Attached To DocType | Link | DocType |  |  | ✅ | None | None |
| `column_break_10` | None | Column Break | None |  |  |  | None | None |
| `attached_to_name` | Attached To Name | Data | None |  |  | ✅ | None | None |
| `attached_to_field` | Attached To Field | Data | None |  |  | ✅ | None | None |
| `old_parent` | old_parent | Data | None |  | ✅ |  | None | None |
| `content_hash` | Content Hash | Data | None |  |  | ✅ | None | None |
| `uploaded_to_dropbox` | Uploaded To Dropbox | Check | None |  |  | ✅ | 0 | None |
| `uploaded_to_google_drive` | Uploaded To Google Drive | Check | None |  |  | ✅ | 0 | None |


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
**Path:** `/workspace/cohenix-bench/apps/frappe/frappe/core/doctype/file/file.js`
```javascript
frappe.ui.form.on("File", {
	refresh: function (frm) {
		if (frm.doc.file_url) {
			frm.add_custom_button(__("View File"), () => {
				if (!frappe.utils.is_url(frm.doc.file_url)) {
					window.open(window.location.origin + frm.doc.file_url);
				} else {
					window.open(frm.doc.file_url);
				}
			});
		}

		if (!frm.doc.is_folder) {
			// add download button
			frm.add_custom_button(__("Download"), () => frm.trigger("download"), "fa fa-download");
		}

		if (!frm.doc.is_private) {
			frm.dashboard.set_headline(
				__("This file is public. It can be accessed without authentication."),
				"orange"
			);
		}

		frm.toggle_display("preview", false);

		// preview different file types
		frm.trigger("preview_file");

		let is_raster_image = /\.(gif|jpg|jpeg|tiff|png)$/i.test(frm.doc.file_url);
		let is_optimizable = !frm.doc.is_folder && is_raster_image && frm.doc.file_size > 0;

		// add optimize button
		is_optimizable && frm.add_custom_button(__("Optimize"), () => frm.trigger("optimize"));

		// add unzip button
		if (frm.doc.file_name && frm.doc.file_name.split(".").splice(-1)[0] === "zip") {
			frm.add_custom_button(__("Unzip"), () => frm.trigger("unzip"));
		}
	},

	preview_file: function (frm) {
		let $preview = "";
		let file_extension = frm.doc.file_type.toLowerCase();

		if (frappe.utils.is_image_file(frm.doc.file_url)) {
			$preview = $(`<div class="img_preview">
				<img
					class="img-responsive"
					src="${frappe.utils.escape_html(frm.doc.file_url)}"
					onerror="${frm.toggle_display("preview", false)}"
				/>
			</div>`);
		} else if (frappe.utils.is_video_file(frm.doc.file_url)) {
			$preview = $(`<div class="img_preview">
				<video width="480" height="320" controls>
					<source src="${frappe.utils.escape_html(frm.doc.file_url)}">
					${__("Your browser does not support the video element.")}
				</video>
			</div>`);
		} else if (file_extension === "pdf") {
			$preview = $(`<div class="img_preview">
				<object style="background:#323639;" width="100%">
					<embed
						style="background:#323639;"
						width="100%"
						height="1190"
						src="${frappe.utils.escape_html(frm.doc.file_url)}" type="application/pdf"
					>
				</object>
			</div>`);
		} else if (file_extension === "mp3") {
			$preview = $(`<div class="img_preview">
				<audio width="480" height="60" controls>
					<source src="${frappe.utils.escape_html(frm.doc.file_url)}" type="audio/mpeg">
					${__("Your browser does not support the audio element.")}
				</audio >
			</div>`);
		}

		if ($preview) {
			frm.toggle_display("preview", true);
			frm.get_field("preview_html").$wrapper.html($preview);
		}
	},

	download: function (frm) {
		let file_url = frm.doc.file_url;
		if (frm.doc.file_name) {
			file_url = file_url.replace(/#/g, "%23");
		}

		// create temporary link element to simulate a download click
		var link = document.createElement("a");
		link.href = file_url;
		link.download = frm.doc.file_name;
		link.style.display = "none";

		document.body.appendChild(link);
		link.click();
		document.body.removeChild(link);
	},

	optimize: function (frm) {
		frappe.show_alert(__("Optimizing image..."));
		frm.call("optimize_file").then(() => {
			frappe.show_alert(__("Image optimized"));
		});
	},

	unzip: function (frm) {
		frappe.call({
			method: "frappe.core.api.file.unzip_file",
			args: {
				name: frm.doc.name,
			},
			callback: function () {
				frappe.set_route("List", "File");
			},
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
