<!-- loio182879fc8cd84672a11826f63450f258 -->

| loio |
| -----|
| 182879fc8cd84672a11826f63450f258 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/182879fc8cd84672a11826f63450f258) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/182879fc8cd84672a11826f63450f258)</div>

## Keyboard Handling for Value Help and Auto-Complete

The following keys and key combinations are used for triggering and using the value help and auto-complete features.

***

### Auto-complete

Auto-complete is available for one dimensional editing only.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Key combination</th>
			<th>Behavior</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Any printable character</td>
			<td> Adds the corresponding character. If text is selected, it gets overwritten.
 Triggers autocomplete, if available.
			</td>
		</tr>
		<tr>
			<td>*Right arrow* or *Down arrow*</td>
			<td> Move caret on position to the right.
 If text is selected, move caret to the end of the selection and remove selection.

 If caret is at the rightmost position, do nothing.

 If autocomplete is currently available, take over changes. Move caret to the right of the changed text.
			</td>
		</tr>
		<tr>
			<td>*Enter*</td>
			<td>If autocomplete is currently available, take over changes. Move caret to the right of the changed text.</td>
		</tr>
		<tr>
			<td>*Tab*</td>
			<td>Move focus to next element. Take over autocomplete, if available.</td>
		</tr>
	</tbody>
</table>

***

### Value Help

Use the following keys and key combinations to trigger value help:

|Key combination|Behavior|
|---------------|--------|
|* Alt Down arrow * or * Alt Up arrow * or *F4* |Open the value help dialog.|

