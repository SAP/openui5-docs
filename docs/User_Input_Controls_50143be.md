<!-- loio50143be270b7433c8a45915d8ae57e69 -->

| loio |
| -----|
| 50143be270b7433c8a45915d8ae57e69 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/50143be270b7433c8a45915d8ae57e69) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/50143be270b7433c8a45915d8ae57e69)</div>

## User Input Controls

OpenUI5 input controls are used to get and store user data. The most common use of these controls is as part of a form.

***

Screen Reader Behavior in Input Controls<a name="loio50143be270b7433c8a45915d8ae57e69__table_mv5_wrs_xw"/>

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
			<td>Check Box</td>
			<td>

 -   Checkbox label
 -   Checkbox state

 -   Checkbox value

 -   Tooltip
			</td>
		</tr>
		<tr>
			<td>Combo Box</td>
			<td>-   Combobox label
 -   Combobox placeholder text \(if any\)

 -   Combobox state

 -   Combobox value

 -   Tooltip


Other interactions that need to be announced:-   Expanding\\collapsing the combobox

 -   Value changes that happen without expanding

 -   When navigating the dropdown items: item text, item state, position in the list, total number of items
			</td>
		</tr>
		<tr>
			<td>Date Picker</td>
			<td>

 -   Picker text
 -   Picker placeholder text \(if any\)

 -   Picker state

 -   Picker value

 -   Tooltip
			</td>
		</tr>
		<tr>
			<td>Facet Filter</td>
			<td>Light Variant \(only one button\):

 -   Label for the filter
 -   Default statement: "no filter selected"


Simple Variant \(several buttons\):-   Labels for the filters
			</td>
		</tr>
		<tr>
			<td>Input</td>
			<td>

 -   Input state
 -   Input value

 -   Input label

 -   Tooltip

 -   Associated descriptions

 -   Associated messages

 -   Additional properties like `valueHelp`
			</td>
		</tr>
		<tr>
			<td>Mask Input</td>
			<td>Basic behavior is like `Input`. Additionally the screen reader should read:

 -   Masked input characters/symbols
 -   Symbols that have already been entered
			</td>
		</tr>
	</tbody>
</table>

