<!-- loiof5b050131a934a2ea6ea4c88aa09fce0 -->

| loio |
| -----|
| f5b050131a934a2ea6ea4c88aa09fce0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f5b050131a934a2ea6ea4c88aa09fce0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f5b050131a934a2ea6ea4c88aa09fce0)</div>

## Container Controls

OpenUI5 container controls do not directly interact with the application user. Still they play an important role in the application navigation and structure.


<table>
<tr>
<th valign="top">

 OpenUI5 Control



</th>
<th valign="top">

What is read by default



</th>
</tr>
<tr>
<td valign="top">

Bar/Toolbar



</td>
<td valign="top">

-   Upon entry in Virtual Cursor mode - ARIA role

-   In Virtual Cursor mode - Type of the contained labels \(header, subheader, footer\)




</td>
</tr>
<tr>
<td valign="top">

Icon Tab Bar



</td>
<td valign="top">

-   Element role \(tapstrip or tabpanel\)

-   Sub-element role \(tab\)

-   Textual descriptions for icon tabs

-   Actual position of the selected tab in the set

-   Total size of the tab set

-   Current state of the selected tab




</td>
</tr>
<tr>
<td valign="top">

Message Page



</td>
<td valign="top">

-   In Virtual Cursor mode - all text on the page




</td>
</tr>
<tr>
<td valign="top">

Page



</td>
<td valign="top">

-   Landmark roles for the substructure elements \(header, content, footer\)




</td>
</tr>
<tr>
<td valign="top">

Panel



</td>
<td valign="top">

-   Button text

-   Toggle state

-   Custom button types

-   Tooltip \(if the button is only an icon\)




</td>
</tr>
<tr>
<td valign="top">

Object Header



</td>
<td valign="top">

-   The Object Header title

-   In Virtual Cursor mode - all content of the region


> ### Note:  
> The whole region should be available as a landmark



</td>
</tr>
</table>

