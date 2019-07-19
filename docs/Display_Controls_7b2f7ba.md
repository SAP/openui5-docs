<!-- loio7b2f7bac3a024cc884c28b09fb7a32ec -->

| loio |
| -----|
| 7b2f7bac3a024cc884c28b09fb7a32ec |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7b2f7bac3a024cc884c28b09fb7a32ec) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7b2f7bac3a024cc884c28b09fb7a32ec)</div>

## Display Controls

OpenUI5 display controls are used to indicate the progress of some action or to show visual elements like images and text.

Screen Reader Behavior in Display Controls<a name="loio7b2f7bac3a024cc884c28b09fb7a32ec__table_mv5_wrs_xw"/>

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
			<td>Busy Indicator</td>
			<td>

 -   Duration - indeterminate
			</td>
		</tr>
		<tr>
			<td>Image</td>
			<td>

 -   Textual description of the image content

 > Note:
 > Decorative images need not be read out.

 > Note:
 > Interactive icons, that are used as buttons, should be read as such \( `role=”button”`\).
			</td>
		</tr>
		<tr>
			<td>Label</td>
			<td>

 -   Label text
			</td>
		</tr>
		<tr>
			<td>Numeric Content</td>
			<td>

 -   Description of the numeric value
			</td>
		</tr>
		<tr>
			<td>Object Identifier</td>
			<td>In Virtual Cursor mode:-   Content
			</td>
		</tr>
		<tr>
			<td>Object Number</td>
			<td>In Virtual Cursor mode:-   Content
 -   Status
			</td>
		</tr>
		<tr>
			<td>Object Status</td>
			<td>In Virtual Cursor mode:-   Content
 -   Status

 -   Textual description of the icons used
			</td>
		</tr>
		<tr>
			<td>Progress Indicator</td>
			<td>

 -   Progress state
 -   Current value

 -   Minimal value

 -   Maximal value

 -   Value changes
			</td>
		</tr>
		<tr>
			<td>Text</td>
			<td>In Virtual Cursor mode:-   Text content
			</td>
		</tr>
	</tbody>
</table>

