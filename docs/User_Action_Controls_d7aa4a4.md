<!-- loiod7aa4a4e98b24181b7f013bea33a8df9 -->

| loio |
| -----|
| d7aa4a4e98b24181b7f013bea33a8df9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d7aa4a4e98b24181b7f013bea33a8df9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d7aa4a4e98b24181b7f013bea33a8df9)</div>

## User Action Controls

OpenUI5 action controls are used for triggering interactions with the application. Therefore it is important that screen readers read the correct set of properties for them in order to insure their proper usage.

***

Screen Reader Behavior in Input Controls<a name="loiod7aa4a4e98b24181b7f013bea33a8df9__table_mv5_wrs_xw"/>

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
			<td>Button</td>
			<td>

 -   Button text
 -   Custom types

 -   Tooltip \(if the button is only an icon\)
			</td>
		</tr>
		<tr>
			<td>Link</td>
			<td>

 -   Link text
 -   Link label

 -   Tooltip
			</td>
		</tr>
		<tr>
			<td>Breadcrumbs</td>
			<td>

 -   In Virtual Cursor mode - upon entry announce the label *Breadcrumb Trail*
 -   For each breadcrumb - text, label and tooltip

 -   For separators - announce textual descriptions if icons are used
			</td>
		</tr>
		<tr>
			<td>Menu Button</td>
			<td>

 -   Button text
 -   Statement that button opens a menu

 -   Custom types

 -   Tooltip \(if the button is only an icon\)
			</td>
		</tr>
		<tr>
			<td>Split Button</td>
			<td>

 -   Button text
 -   Statement that button opens a menu

 -   Custom split button types

 -   Tooltip \(if the button is only an icon\)
			</td>
		</tr>
		<tr>
			<td>Toggle Button</td>
			<td>

 -   Button text
 -   Toggle state

 -   Custom button types

 -   Tooltip \(if the button is only an icon\)
			</td>
		</tr>
	</tbody>
</table>

