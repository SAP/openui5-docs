<!-- loioc512d71312e54b77809ba62b813239a1 -->

# What's New in OpenUI5 1.134

With this release OpenUI5 is upgraded from version 1.133 to 1.134.

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

1.134 

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

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://ui5.sap.com/#/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Table`** 

</td>
<td valign="top">

**`sap.ui.mdc.Table`**

Up to now, the `p13n` data and the variants did not save the information about whether details are displayed or hidden in a table \(*Show More per Row*/*Show Less per Row* buttons\). The state of this data is now persisted for responsive tables when the user presses the *Show More per Row* or the *Show Less per Row* button, when a new column is added or a variant is changed, or via `sap.ui.mdc.p13n.StateUtil`. Depending on what happens in the scenario, the state gets updated or stays the same, for example, for a new column that is hidden in the popin, `showDetails` is set to `true` and a change is created or, if it isn't hidden, the state stays the same.

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`** 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

We've improved accessibility by removing default labels for untitled subsections and sections in the `ObjectPageLayout` control. This change ensures a cleaner and more intuitive navigation experience, as labeling now occurs at the section level or is derived from the anchor bar, improving usability for screen-reader users.

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Select`** 

</td>
<td valign="top">

**`sap.m.Select`**

The `sap.m.Select` control now supports both [Space\] and [Enter\] keys to open its dropdown menu. This update enhances keyboard navigation, making it easier and more efficient for users to interact with breadcrumb elements. For more information, see [Accessibility for End Users](https://help.sap.com/viewer/bc5a64aac808463baa95b4230f221716/1.134/en-US).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessageView`** 

</td>
<td valign="top">

**`sap.m.MessageView`**

The `MessageView` control has been enhanced to improve message display by enabling text wrapping and truncating long messages and subtitles after 140 characters. This feature allows users to access full message details by navigating to a detailed view, enhancing user experience and interface clarity. For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.MessageView/sample/sap.m.sample.MessageViewInsideResponsivePopover).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`** 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`** 

-   Year range selections are now presented in two columns instead of three. This change enhances accessibility and prevents numbers from being cut off when a text spacing tool is used.
-   Months, years, and year ranges now show as selected in their respective pickers if there is a selected date within the month, year, or year range. For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.ui.unified.Calendar/sample/sap.ui.unified.sample.CalendarMultipleDaySelection).

<sub>Changed • Control • Info Only • 1.134 </sub> 

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Button`** 

</td>
<td valign="top">

**`sap.m.Button`**

We have added a visible focus outline to `sap.m.Button` when the control receives focus on a mobile device from an external keyboard. For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.Button/sample/sap.m.sample.Button).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DynamicDateRange`** 

</td>
<td valign="top">

**`sap.m.DynamicDateRange`**

We have simplified the display of date ranges of type *Last X Minutes / Hours / Days / Weeks / Months / Quarters / Years* and *Next X Minutes / Hours / Days / Weeks / Months / Quarters / Years* that are accessible from the control's *Choose date range* dropdown list. We have removed from the display of the date ranges in the *Select* dropdown *Unit of Time* in cases when it has become redundant because only one unit of time \(for example *Last X Minutes*\) has been specified by the application developer. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.DynamicDateRange).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ColorPalette`** 

</td>
<td valign="top">

**`sap.m.ColorPalette`**

If a color is selected in the `ColorPalette` or a color is selected in the `selectedColor` property, and subsequently the *More Colors* button is pressed to open the `ColorPicker`, the `ColorPicker` now inherits the selected color and displays it. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.ColorPalette).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

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

Based on user testing feedback, we have implemented several improvements:

-   The clock dial in 24-hour format is now reprogrammed as a single circular interface.
-   Hovering over a number or a dot in the clock dial now highlights and visualizes the number for the respective hour.
-   Dots in the clock dial are now selectable.
-   To enhance visual interaction, we have improved animations for transitions between different clock dial visualization states \(hours, minutes, seconds\).

For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.TimePicker/sample/sap.m.sample.TimePicker). 

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`** 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`**

The new Overlay Mode allows `SideNavigation` to reside in `sap.m.ResponsivePopover` and function as a standard `SideNavigation`. To activate Overlay Mode, set the `verticalScrolling` property of the `ResponsivePopover` to `false`. In addition, we have created a new `design` property in `SideNavigation`. The `design` property handles the control’s container styling and we strongly recommend setting it to `Plain` in Overlay Mode. For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.tnt.SideNavigation/sample/sap.tnt.sample.SideNavigationOverlayMode). 

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.FlexBox, sap.m.HBox, sap.m.VBox`** 

</td>
<td valign="top">

**`sap.m.FlexBox, sap.m.HBox, sap.m.VBox`**

The new `gap` property offers a simple and consistent approach to defining space between flex items \(rows and columns\), ensuring visual separation and enhancing the layout structure. Additionally, the `rowGap` and `columnGap` longhand properties can be used for more precision and take precedence over `gap` if both `gap` and either `rowGap` or `columnGap` are specified. For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.FlexBox/sample/sap.m.sample.FlexBoxGap).

<sub>Changed•Control•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
<tr>
<td valign="top">

1.134 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V4 Model and OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V4 Model and OData V2 Model**

We have provided the `sap.ui.model.odata.v4.ODataModel#setRetryAfterHandler` and `sap.ui.model.odata.v2.ODataModel#setRetryAfterHandler` APIs. For more information, see *Handling of Temporarily Unavailable Back Ends* for the [OData V4](../04_Essentials/handling-of-temporarily-unavailable-back-ends-b3422ec.md) and [OData V2](../04_Essentials/odata-v2-model-6c47b2b.md#loio262f75165c3d43b1817f6469aaad453c) model, and the API Reference for [`v4.ODataModel#setRetryAfterHandler`](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/setRetryAfterHandler) and [`v2.ODataModel#setRetryAfterHandler`](https://ui5.sap.com/#/api/sap.ui.model.odata.v2.ODataModel%23methods/setRetryAfterHandler).

<sub>Changed•Feature•Info Only•1.134</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-03-20

</td>
</tr>
</table>

