| loio |
| -----|
| 81c68e4654994da5935add669e48f20c |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/81c68e4654994da5935add669e48f20c.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/81c68e4654994da5935add669e48f20c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/81c68e4654994da5935add669e48f20c)</div>
<!-- loio81c68e4654994da5935add669e48f20c -->

## Keyboard Handling for Triggering Actions on Item Level

The following keys and key combinations are used for triggering events of clickable elements.

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
			<td>*SPACE*</td>
			<td>If items are **not selectable** and focus is on an item, trigger the item event.

 > Note:
 > If you press and hold the key, you can cancel the trigger action by pressing *Shift*.

 If items are selectable, select/deselect the item.</td>
		</tr>
		<tr>
			<td>*ENTER*</td>
			<td>If focus is on an item, trigger the item event immediately after the key press.</td>
		</tr>
	</tbody>
</table>
***

Use the following keys to trigger additional actions \(if supported\):

|Key combination|Behavior|
|---------------|--------|
|*DELETE*|If deletion of items supported: If focus is on an item, delete the item. Move focus to the next item. If the deleted item is the last item, move focus to the previous item. If the deleted item is the last remaining item, move focus to the next control in the tab order.|
|*F2*|If *Detail* of items is supported: If focus is on an item, trigger the click event for the *Detail* button.|

