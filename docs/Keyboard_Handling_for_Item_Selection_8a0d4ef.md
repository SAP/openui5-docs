<!-- loio8a0d4efa29d44ef39219c18d832012da -->

| loio |
| -----|
| 8a0d4efa29d44ef39219c18d832012da |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8a0d4efa29d44ef39219c18d832012da) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8a0d4efa29d44ef39219c18d832012da)</div>

## Keyboard Handling for Item Selection

The following keys and key combinations are used for selecting one or multiple items from a list.

***

### Single Selection


<table>
<tr>
<th>

Key combination



</th>
<th>

Behavior



</th>
</tr>
<tr>
<td>

[Spacebar\]



</td>
<td>

If focus is on an item, select the item and deselect all others.



</td>
</tr>
</table>

***

### Multi Selection


<table>
<tr>
<th>

Key combination



</th>
<th>

Behavior



</th>
</tr>
<tr>
<td>

[Spacebar\]



</td>
<td>

If focus is on an item, select the item and deselect all others.



</td>
</tr>
<tr>
<td>

 [Ctrl\] + [Spacebar\] 



</td>
<td>

If focus is on an item, select the item in addition to an existing selection..



</td>
</tr>
<tr>
<td>

 [Shift\] + [Spacebar\] 



</td>
<td>

If focus is on an item, select all items from the previous selected item to the now focused item \(included\).

Previous selection: all kinds of selection except [Shift\][Spacebar\] selections



</td>
</tr>
<tr>
<td>

 [Shift\] + [Up arrow\] 



</td>
<td>

If focus is on an item, change selection state \(selected/ not selected\) to the item above.



</td>
</tr>
<tr>
<td>

 [Shift\] + [Down arrow\] 



</td>
<td>

If focus is on an item, change selection state \(selected/ not selected\) to the item below.



</td>
</tr>
<tr>
<td>

 [Ctrl\] + [A\] 



</td>
<td>

Selects all items which the user can reach in the current view by scrolling or paging.

If all items are selected, deselects all items.

This is the default behavior of a list.



</td>
</tr>
<tr>
<td>

 [Ctrl\] + [Shift\] + [A\] 



</td>
<td>

Deselects all items which the user can reach in the current view by scrolling or paging.

To select items , you can no longer use [Ctrl\][A\]. You have to use [Spacebar\] for single selection or  [Shift\] + [Up arrow\]  or [Down arrow\] for multiple selection.

This is the behavior if `multiSelectMode` is set to `ClearAll` for a list.



</td>
</tr>
</table>

