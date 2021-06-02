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

Navigation between controls is done using the [Tab\] key. [Tab\] moves the focus from one control to the next one inside the application. The tab order is defined by the placement of the control within the DOM tree, therefore apps have a large influence on it.

> ### Note:  
> Controls are in the tab order, if they are interactive, enabled and visible. This includes read-only controls. Disabled or hidden controls are taken out of the tab order. Non-interactive controls \(for example, layout container\) can never be reached with [Tab\].


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

[Tab\]



</td>
<td>

Forward Navigation:

On enter, move focus to the control.

On leave, move focus to the next control in the application.



</td>
</tr>
<tr>
<td>

 [Shift\] + [Tab\] 



</td>
<td>

Backward Navigation:

On enter, move focus to the control.

On leave, move focus to the previous control in the tab order.



</td>
</tr>
</table>

***

### Group Navigation

Controls which are adjacent within the application can be grouped. Within a group, [F6\] or  [Ctrl\] + [Alt/Option\] + [Down\]  skip all controls of the group and move the focus to the first control in the application within the **next** group.  [Shift\] + [F6\]  or  [Ctrl\] + [Alt/Option\] + [Up\] move the focus to the first control of the **previous** group.


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

[F6\] 

or

 [Ctrl\] + [Alt/Option\] + [Down\] 



</td>
<td>

Fast Navigation \(forward\):

Move focus to the next control in the tab order after the group



</td>
</tr>
<tr>
<td>

 [Shift\] + [F6\]  

or

 [Ctrl\] + [Alt/Option\] + [Up\] 



</td>
<td>

Fast Navigation \(back\):

Move focus to the previous control in the tab order before the group



</td>
</tr>
</table>

