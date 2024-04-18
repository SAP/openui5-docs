<!-- loio9d00ac7f35734554ac9d11de5f3d4dbe -->

| loio |
| -----|
| 9d00ac7f35734554ac9d11de5f3d4dbe |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/9d00ac7f35734554ac9d11de5f3d4dbe) | [demo kit latest release](https://sdk.openui5.org/topic/9d00ac7f35734554ac9d11de5f3d4dbe)</div>

## What's New in OpenUI5 1.123

With this release OpenUI5 is upgraded from version 1.122 to 1.123.

****


<table>
<tr>
<th valign="top">

Version

</th>
<th valign="top">

Type

</th>
<th valign="top">

Category

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Deprecations** 

</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MenuItem` and `sap.ui.unified.MenuItem`** 

</td>
<td valign="top">

**`sap.m.MenuItem`, `sap.ui.unified.MenuItem`**

We have added a new `shortcutText` property to the menu items of both controls. It allows developers to provide users with a quick reference about the available keyboard shortcuts. The shortcut text is displayed after the regular menu item text. Additionally, when the `shortcutText` property is set, the `aria-keyshortcuts` attribute is automatically rendered in the menu item's DOM element. This attribute holds the same value as the `shortcutText` property, thereby improving accessibility for users who rely on assistive technologies. For more information, see the API References of [sap.m.MenuItem](https://sdk.openui5.org/api/sap.m.MenuItem) and [sap.ui.unified.MenuItem](https://sdk.openui5.org/api/sap.ui.unified.MenuItem) controls.

<sub>Changed•Control•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

-   We have introduced a way to place custom content inside calendar appointments in the same way as it was already possible in the `sap.m.PlanningCalendar`. Using the `customContent` aggregation you can now add suitable controls in the `sap.ui.unified.CalendarAppointment` and these controls will be rendered instead of the original `title`, `text`, `description`, and `icon` properties of the appointment. The custom content will be displayed in all views of the `SinglePlanningCalendar`. As an application developer, you must ensure that all the accessibility requirements are met, and that the height of the content conforms with the height provided by the appointment For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.CalendarAppointment).
-   We have introduced two new events triggered from the Month view:

    -   `weekNumberPress` - fired when a calendar week number is pressed. It carries information about the number of the selected week.
    -   `selectedDatesChange` - fired when a new day, or a sequence of days, is selected. If the event is prevented, the change will not occur.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).


<sub>Changed•Control•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TimePicker`** 

</td>
<td valign="top">

**`sap.m.TimePicker`**

-   We have improved the control when used with flexible time formats. We have changed the default behavior of the mask and now, if the `maskMode` property is set to `On`, the mask is only applied to time formats with a fixed length, but it’s disabled when the time format doesn't have a fixed length. Additionally, we have added a new `maskMode` option, `Enforce`, with which the mask will always be enforced, regardless of whether the length of the time format is fixed or variable.
-   The flexible time periods that are specified with date patterns with the `B` symbol in the display format can now be used in the control’s value help. Date patterns specified with the `B` symbol are using values like `midnight`, `noon`, `in the morning`, `in the afternoon`, and others. These values are now adapted to AM/PM when a 12-hour format is used.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TimePicker).

<sub>Changed•Control•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V4 Model** 

</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We have introduced the `sap.ui.model.odata.v4.ODataContextBinding#invoke` method, replacing the now deprecated `#execute` method.

-   If you use the experimental feature of recursive hierarchy maintenance and call the `sap.ui.model.odata.v4.Context#requestSideEffects` API with an empty navigation property path on the header context of a list binding, the expansion state of nodes is now kept, and created nodes are still shown preceding their siblings.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/requestSideEffects).

-   If you use the experimental feature of selecting all records by calling `sap.ui.model.odata.v4.Context#setSelected` on the header context of a list binding, all loaded contexts are now selected accordingly.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/setSelected).


<sub>Changed•Feature•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.InputBase`,`sap.m.ComboBox`** 

</td>
<td valign="top">

**`sap.m.InputBase`, `sap.m.ComboBox`**

We have enhanced the behavior to display the value state message when clicking the input if it was moved out of the viewport or hidden for any other reason.

<sub>Changed•Control•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

1.123 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input`, `sap.m.ComboBox` ** 

</td>
<td valign="top">

**`sap.m.Input`, `sap.m.ComboBox`**

We have improved the behavior of type-ahead and selection of dynamically added items when users edit or delete input or suggestions. When users delete characters and the remaining text exactly matches an item, that item is now selected.

<sub>Changed•Control•Info Only•1.123</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-04-18

</td>
</tr>
</table>

