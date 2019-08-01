<!-- loiof5b050131a934a2ea6ea4c88aa09fce0 -->

| loio |
| -----|
| f5b050131a934a2ea6ea4c88aa09fce0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f5b050131a934a2ea6ea4c88aa09fce0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f5b050131a934a2ea6ea4c88aa09fce0)</div>

## Container Controls

OpenUI5 container controls do not directly interact with the application user. Still they play an important role in the application navigation and structure.

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
			<td>Bar/Toolbar</td>
			<td>

 -   Upon entry in Virtual Cursor mode - ARIA role
 -   In Virtual Cursor mode - Type of the contained labels \(header, subheader, footer\)
			</td>
		</tr>
		<tr>
			<td>Icon Tab Bar</td>
			<td>

 -   Element role \(tapstrip or tabpanel\)
 -   Sub-element role \(tab\)

 -   Textual descriptions for icon tabs

 -   Actual position of the selected tab in the set

 -   Total size of the tab set

 -   Current state of the selected tab
			</td>
		</tr>
		<tr>
			<td>Message Page</td>
			<td>

 -   In Virtual Cursor mode - all text on the page
			</td>
		</tr>
		<tr>
			<td>Page</td>
			<td>

 -   Landmark roles for the substructure elements \(header, content, footer\)
			</td>
		</tr>
		<tr>
			<td>Panel</td>
			<td>

 -   Button text
 -   Toggle state

 -   Custom button types

 -   Tooltip \(if the button is only an icon\)
			</td>
		</tr>
		<tr>
			<td>Object Header</td>
			<td>

 -   The Object Header title
 -   In Virtual Cursor mode - all content of the region


 > Note:
 > The whole region should be available as a landmark
			</td>
		</tr>
	</tbody>
</table>

