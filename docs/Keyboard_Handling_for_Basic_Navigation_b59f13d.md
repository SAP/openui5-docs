<!-- loiob59f13d3586c4196b28e92683e9dff19 -->

| loio |
| -----|
| b59f13d3586c4196b28e92683e9dff19 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b59f13d3586c4196b28e92683e9dff19) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b59f13d3586c4196b28e92683e9dff19)</div>

## Keyboard Handling for Basic Navigation

The following keys and key combinations are used for navigation between controls within an application.

***

### Standard Navigation

Navigation between controls is done using the *Tab* key. *Tab* moves the focus from one control to the next one inside the application. The tab order is defined by the placement of the control within the DOM tree, therefore apps have a large influence on it.

> Note:  
> Controls are in the tab order, if they are interactive, enabled and visible. This includes read-only controls. Disabled or hidden controls are taken out of the tab order. Non-interactive controls \(for example, layout container\) can never be reached with *Tab*.

|Key combination

|Behavior

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----------------</th>
			<th>----------</th>
		</tr>
	</thead>
	<tbody>

			<td>Forward Navigation:
On enter, move focus to the control.

On leave, move focus to the next control in the application.
			</td>
		</tr>
		<tr>
			<td>* Shift Tab *
			</td>
			<td>Backward Navigation:
On enter, move focus to the control.

On leave, move focus to the previous control in the tab order.
			</td>
		</tr>
	</tbody>
</table>

***

### Group Navigation

Controls which are adjacent within the application can be grouped. Within a group, *F6* skips all controls of the group and moves the focus to the first control in the application within the **next** group. * Shift F6 * moves the focus to the first control of the **previous** group.

|Key combination

|Behavior

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----------------</th>
			<th>----------</th>
		</tr>
	</thead>
	<tbody>

			<td>Forward Navigation:
Move focus to the next control in the tab order after the group
			</td>
		</tr>
		<tr>
			<td>* Shift F6 *
			</td>
			<td>Backward Navigation:
Move focus to the previous control in the tab order before the group
			</td>
		</tr>
	</tbody>
</table>

