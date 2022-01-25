<!-- loio6b741a6133284bd78e897cef8b75f6d9 -->

| loio |
| -----|
| 6b741a6133284bd78e897cef8b75f6d9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/6b741a6133284bd78e897cef8b75f6d9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/6b741a6133284bd78e897cef8b75f6d9)</div>

## Keyboard Handling for OpenUI5 UI Elements

OpenUI5 UI elements provide keyboard handling in order to improve accessibility and speed up work.

***

### Keyboard Shortcuts for End Users

In this topic we introduce the main keyboard combinations that are used by OpenUI5 UI elements. Furthermore we describe some additional combinations that are used in specific cases.

<a name="loio6b741a6133284bd78e897cef8b75f6d9__table_u1x_1dg_yq"/>Main Keyboard Combinations


<table>
<tr>
<th valign="top">

Key Combination



</th>
<th valign="top">

What it does



</th>
<th valign="top">

Specific Behavior



</th>
</tr>
<tr>
<td valign="top">

[Tab\]

[Shift\] ⁠+⁠ [Tab\]



</td>
<td valign="top">

Focuses UI elements in order \(forward / backward\)



</td>
<td valign="top">

You can cycle through all interactive, enabled and visible UI elements that are part of a given dialog or other container. When the last UI element is focused, pressing the key again will move the focus to first element.



</td>
</tr>
<tr>
<td valign="top">

[Space\] 



</td>
<td valign="top">

Triggers an action \(reversible\)



</td>
<td valign="top">

Pressing and releasing the key triggers the action that is associated with a UI element \(for example, open a link or toggle a button\).

> ### Tip:  
> If you press and hold the key, you can cancel the trigger action by pressing [Shift\].



</td>
</tr>
<tr>
<td valign="top">

[Enter\]



</td>
<td valign="top">

Triggers an action \(immediate\)



</td>
<td valign="top">

Triggers the action that is associated with a UI element \(for example, open a link or toggle a button\). The action is triggered immediately after the key is pressed.



</td>
</tr>
<tr>
<td valign="top">

[Arrow  Keys\] 



</td>
<td valign="top">

Navigates between elements



</td>
<td valign="top">

You can move the focus between elements within a complex UI element \(for example a table or a list\). Depending on the structure, this navigation is either one-directional \(left/right or up/down\) or two-directional \(left, right, up, down\).



</td>
</tr>
<tr>
<td valign="top">

[Home\]

[End\]



</td>
<td valign="top">

Navigates between elements



</td>
<td valign="top">

You can move the selection to the first/last element within a set of elements.

> ### Tip:  
> When using UI elements like sliders and rating indicators, pressing these keys will set the selected value to the maximum/minimum respectively.



</td>
</tr>
<tr>
<td valign="top">

[Page  Up\]

[Page  Down\]



</td>
<td valign="top">

Skips elements during navigation



</td>
<td valign="top">

You can move the selection forward/backward by several elements at a time. If the remaining number of elements is less than the step size, selection will move to the last/first element.



</td>
</tr>
<tr>
<td valign="top">

[Escape\]



</td>
<td valign="top">

Closes element / Reverts changes



</td>
<td valign="top">

Depending on your situation, you can do the following:

-   Close an additionally opened element \(for example, a pop-up\).

-   Revert the execution to a previous step - one step at a time.

-   If you have made changes to the content of an element \(for example, a text field\), pressing this key will revert those changes.




</td>
</tr>
<tr>
<td valign="top">

[F4\] or

 [Alt\] + [Down\]  or

 [Alt\] + [Up\] 



</td>
<td valign="top">

Opens / closes a drop-down menu



</td>
<td valign="top">

You can open the options and elements available in a drop-down menu, if the UI element in question provides this type of information.



</td>
</tr>
<tr>
<td valign="top">

[F6\] or

 [Ctrl\] + [Alt/Option\] + [Down\] 



</td>
<td valign="top">

Forward fast navigation



</td>
<td valign="top">

UI elements within an application can be grouped together \(for example, all elements in the header of an application\). You can forward-skip focusing every element within such a group by using these keys.



</td>
</tr>
<tr>
<td valign="top">

 [Shift\] + [F6\]  or

 [Ctrl\] + [Alt/Option\] + [Up\] 



</td>
<td valign="top">

Backward fast navigation



</td>
<td valign="top">

Skips focus of UI elements backward.



</td>
</tr>
</table>

<a name="loio6b741a6133284bd78e897cef8b75f6d9__table_zld_4rl_yq"/>Additional Keyboard Combinations for Specific UI elements


<table>
<tr>
<th valign="top">

Key Combination



</th>
<th valign="top">

What it does



</th>
<th valign="top">

Specific Behavior



</th>
</tr>
<tr>
<td valign="top">

[Page  Up\]

[Page  Down\]



</td>
<td valign="top">

Date modification \(Days\)



</td>
<td valign="top">

When in input: Pressing these keys decreases/increases the date value by one day.

When in Calendar UI: Pressing these keys decreases/increases the date value by one month.



</td>
</tr>
<tr>
<td valign="top">

 [Shift\] + [Page  Up\] 

 [Shift\] + [Page  Down\] 



</td>
<td valign="top">

Date modification \(Months\)



</td>
<td valign="top">

When in input: Pressing these keys decreases/increases the date value by one month.

When in Calendar UI: Pressing these keys decreases/increases the date value by one year.



</td>
</tr>
<tr>
<td valign="top">

 [Ctrl\] + [Shift\] + [Page  Up\] 

 [Ctrl\] + [Shift\] + [Page  Down\] 



</td>
<td valign="top">

Date modification \(Years\)



</td>
<td valign="top">

When in input: Pressing these keys decreases/increases the date value by one year.

When in Calendar UI: Pressing these keys decreases/increases the date value by 10 years.



</td>
</tr>
<tr>
<td valign="top">

 [Ctrl\] + [Arrow  Keys\] 



</td>
<td valign="top">

When used with grouped radio buttons - Moves selection



</td>
<td valign="top">

Pressing these keys moves the focus to the next corresponding radio button in the group. The currently selected radio button does not change.



</td>
</tr>
<tr>
<td valign="top">

 [Ctrl\] + [Arrow  Keys\] 



</td>
<td valign="top">

When editing tiles in a container - Changes tile position



</td>
<td valign="top">

Pressing these keys changes the position of the focused tile in the tile container. The remaining tiles are re-ordered accordingly.



</td>
</tr>
<tr>
<td valign="top">

[F2\]



</td>
<td valign="top">

Toggles edit mode



</td>
<td valign="top">

You can toggle editing of an editable UI element like an input field or text area.



</td>
</tr>
<tr>
<td valign="top">

[F7\]



</td>
<td valign="top">

Exits edit mode



</td>
<td valign="top">

When you are editing an input field in a table or a list, pressing this key will stop the editing and move the focus to the parent UI element.

> ### Note:  
> Pressing [F7\] again will move focus back to the editable element.



</td>
</tr>
</table>

