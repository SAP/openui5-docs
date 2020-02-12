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

Main Keyboard Combinations<a name="loio6b741a6133284bd78e897cef8b75f6d9__table_u1x_1dg_yq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Key Combination</th>
			<th>What it does</th>
			<th>Specific Behavior</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>*Tab* / * Shift Tab *</td>
			<td>Focuses UI elements in order \(forward / backward\)</td>
			<td>You can cycle through all interactive, enabled and visible UI elements that are part of a given dialog or other container. When the last UI element is focused, pressing the key again will move the focus to first element.</td>
		</tr>
		<tr>
			<td>*Space* </td>
			<td>Triggers an action \(reversible\)</td>
			<td>Pressing and releasing the key triggers the action that is associated with a UI element \(for example, open a link or toggle a button\).

 > Note:
 > If you press and hold the key, you can cancel the trigger action by pressing *Shift*.
			</td>
		</tr>
		<tr>
			<td>*Enter*</td>
			<td>Triggers an action \(immediate\)</td>
			<td>Triggers the action that is associated with a UI element \(for example, open a link or toggle a button\). The action is triggered immediately after the key is pressed.</td>
		</tr>
		<tr>
			<td>*Arrow Keys* </td>
			<td>Navigates between elements</td>
			<td>You can move the focus between elements within a complex UI element \(for example a table or a list\). Depending on the structure, this navigation is either one-directional \(left/right or up/down\) or two-directional \(left, right, up, down\).</td>
		</tr>
		<tr>
			<td>*Home* / *End*</td>
			<td>Navigates between elements</td>
			<td>You can move the selection to the first/last element within a set of elements.

 > Note:
 > When using UI elements like sliders and rating indicators, pressing these keys will set the selected value to the maximum/minimum respectively.
			</td>
		</tr>
		<tr>
			<td>*Page Up* / *Page Down*</td>
			<td>Skips elements during navigation</td>
			<td>You can move the selection forward/backward by several elements at a time. If the remaining number of elements is less than the step size, selection will move to the last/first element.</td>
		</tr>
		<tr>
			<td>*Escape*</td>
			<td>Closes element / Reverts changes</td>
			<td>Depending on your situation, you can do the following:

 -   Close an additionally opened element \(for example, a pop-up\).
 -   Revert the execution to a previous step - one step at a time.

 -   If you have made changes to the content of an element \(for example, a text field\), pressing this key will revert those changes.
			</td>
		</tr>
		<tr>
			<td> *F4* / * Alt Down * / * Alt Up *</td>
			<td>Opens / closes a drop-down menu</td>
			<td>You can open the options and elements available in a drop-down menu, if the UI element in question provides this type of information.</td>
		</tr>
		<tr>
			<td>*F6* / * Shift F6 *</td>
			<td>Skips focus of UI elements \(forward / backward\)</td>
			<td>UI elements within an application can be grouped together \(for example, all elements in the header of an application\). You can skip focusing the elements within a group by using these keys.</td>
		</tr>
	</tbody>
</table>

Additional Keyboard Combinations for Specific UI elements<a name="loio6b741a6133284bd78e897cef8b75f6d9__table_zld_4rl_yq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Key Combination</th>
			<th>What it does</th>
			<th>Specific Behavior</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>*Page Up* / *Page Down*</td>
			<td>Date modification \(Days\)</td>
			<td>When in input: Pressing these keys decreases/increases the date value by one day. When in Calendar UI: Pressing these keys decreases/increases the date value by one month.</td>
		</tr>
		<tr>
			<td>* Shift Page Up * / * Shift Page Down *</td>
			<td>Date modification \(Months\)</td>
			<td>When in input: Pressing these keys decreases/increases the date value by one month. When in Calendar UI: Pressing these keys decreases/increases the date value by one year.</td>
		</tr>
		<tr>
			<td>* Ctrl Shift Page Up * / * Ctrl Shift Page Down *</td>
			<td>Date modification \(Years\)</td>
			<td>When in input: Pressing these keys decreases/increases the date value by one year. When in Calendar UI: Pressing these keys decreases/increases the date value by 10 years.</td>
		</tr>
		<tr>
			<td>* Ctrl Arrow Keys *</td>
			<td>When used with grouped radio buttons - Moves selection</td>
			<td>Pressing these keys moves the focus to the next corresponding radio button in the group. The currently selected radio button does not change.</td>
		</tr>
		<tr>
			<td>* Ctrl Arrow Keys *</td>
			<td>When editing tiles in a container - Changes tile position</td>
			<td>Pressing these keys changes the position of the focused tile in the tile container. The remaining tiles are re-ordered accordingly.</td>
		</tr>
		<tr>
			<td>*F2*</td>
			<td>Toggles edit mode</td>
			<td>You can toggle editing of an editable UI element like an input field or text area.</td>
		</tr>
		<tr>
			<td>*F7*</td>
			<td>Exits edit mode</td>
			<td> When you are editing an input field in a table or a list, pressing this key will stop the editing and move the focus to the parent UI element.
 > Note:
 > Pressing *F7* again will move focus back to the editable element.
			</td>
		</tr>
	</tbody>
</table>

