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
<th valign="top">

Key combination



</th>
<th valign="top">

Behavior



</th>
</tr>
<tr>
<td valign="top">

[Spacebar\]



</td>
<td valign="top">

If focus is on an item, selects the item and deselects all others.



</td>
</tr>
</table>

***

### Multi Selection


<table>
<tr>
<th valign="top">

Key combination



</th>
<th valign="top">

Behavior



</th>
</tr>
<tr>
<td valign="top">

[Spacebar\]



</td>
<td valign="top">

If focus is on an item, selects the item in addition to all previously selected items.



</td>
</tr>
<tr>
<td valign="top">

 [Shift\] + [Up arrow\] 



</td>
<td valign="top">

If focus is on an item, changes selection state \(selected/ not selected\) to the item above.



</td>
</tr>
<tr>
<td valign="top">

 [Shift\] + [Down arrow\] 



</td>
<td valign="top">

If focus is on an item, changes selection state \(selected/ not selected\) to the item below.



</td>
</tr>
<tr>
<td valign="top">

 [Ctrl\] + [A\] 



</td>
<td valign="top">

Selects all items which the user can reach in the current view by scrolling or paging.

If all items are selected, deselects all items.

This is the default behavior of a list.



</td>
</tr>
<tr>
<td valign="top">

 [Ctrl\] + [Shift\] + [A\] 



</td>
<td valign="top">

Deselects all items which the user can reach in the current view by scrolling or paging.

To select items , you can no longer use [Ctrl\][A\]. You have to use [Spacebar\] for single selection or  [Shift\] + [Up arrow\]  or [Down arrow\] for multiple selection.

This is the behavior if `multiSelectMode` is set to `ClearAll` for a list.



</td>
</tr>
</table>

