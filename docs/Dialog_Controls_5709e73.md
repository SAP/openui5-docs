<!-- loio5709e73d51f2401a9a5a89d8f5479132 -->

| loio |
| -----|
| 5709e73d51f2401a9a5a89d8f5479132 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5709e73d51f2401a9a5a89d8f5479132) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5709e73d51f2401a9a5a89d8f5479132)</div>

## Dialog Controls

OpenUI5 dialog controls can serve different purposes within the application and are therefore handled differently by the screen reader.

***

### General Behavior

Dialog controls are used to interact with the user in two main ways. Popups, message boxes, and busy dialogs interrupt the user and require some additional interaction. Message toast and message strip are used to just display some status information without interrupting the user. Interrupting dialogs have a more complex structure, but all generally follow the same structure - a title, content area and some actions. The title should be the first thing read by the screen reader. It should explain the general purpose of the dialog \(i.e. Data confirmation, Interruption\). If the dialog contains initially focused elements, like action buttons, those should be read after the title announcement. The contents of the dialog should be read in their respective order.

***

### Titles and Labels

The behavior of controls based on Dialog/Popup \(`role="dialog"`\) changes depending on their `aria-labelledby` attribute.

If the the control has an `aria-labelledby` attribute, the screen reader will announce the following elements:

-   The provided label

-   The role of the dialog

-   The currently focused element


If the the control does NOT have an `aria-labelledby` attribute, the screen reader will announce the following elements:

-   All elements in the dialog \(regardless if interactive or not\)

-   The role of the dialog

-   The currently focused element


The `title` property of a Popover/Dialog is used to display the title of the dialog. If the dialog has no visible title, but one is needed, it can be provided as a reference to another control in `aria-labelledby`. All other text that needs to be read before the title, can be added there as well.

> Note:
> A dialog without a title will be read completely when it appears. Users with screen readers will not be able to differentiate it from the rest of the application.
> 
> 

> Note:
> Dialog with `ariaLabelledBy` 
> 
> ```
> 	var oDialog = new sap.m.Dialog({
> 				title: "Dialog Title",
> 				ariaLabelledBy: "textId",
> 				content: [
> 					new sap.m.Text({id: "textId", text: "A sample text that will be annoucned by JAWS after the title, when the dialog is opened."})
> 				]
> 			});
> 			
> 			var btn = new sap.m.Button({
> 				text:'Hello World',
> 				press: function(){
> 					oDialog.open();
> 				}
> 			});
> 			btn.placeAt('content');
> ```
> 
> 

More detailed behavior is described in the table below.

***

### Detailed Behavior

In the following table you can see how the different dialog controls are read by the screen reader.

Screen Reader Behavior in Dialog Controls<a name="loio5709e73d51f2401a9a5a89d8f5479132__table_mv5_wrs_xw"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> OpenUI5 Control</th>
			<th>What is read by default</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Dialog / Select Dialog</td>
			<td>

 -   Dialog title
 -   Initially focused element
			</td>
		</tr>
		<tr>
			<td>Busy Dialog</td>
			<td>

 -   Dialog header
 -   Dialog message

 -   Progress bar
			</td>
		</tr>
		<tr>
			<td>Message Box</td>
			<td>

 -   Dialog title
 -   Dialog message
			</td>
		</tr>
		<tr>
			<td>Message Toast</td>
			<td>

 -   Message text when the toast appears
			</td>
		</tr>
		<tr>
			<td>Message Popover / Popover</td>
			<td>

 -   No specific element needs to be read or focused.
			</td>
		</tr>
		<tr>
			<td>Message Strip</td>
			<td>

 -   The complete content including text, icons and links
 -   Message type

 -   Associated headings \(if any\)


 > Note:
 > The *Close* button should not be read initially.
			</td>
		</tr>
	</tbody>
</table>

