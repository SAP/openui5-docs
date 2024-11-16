<!-- loio85609d48f6954cf1a13724c1aaa78c63 -->

| loio |
| -----|
| 85609d48f6954cf1a13724c1aaa78c63 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/85609d48f6954cf1a13724c1aaa78c63) | [demo kit latest release](https://sdk.openui5.org/topic/85609d48f6954cf1a13724c1aaa78c63)</div>

## What's New in OpenUI5 1.130

With this release OpenUI5 is upgraded from version 1.129 to 1.130.

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

1.130 

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

<sub>Deprecated•Feature•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**sap.m.List** 

</td>
<td valign="top">

**sap.m.List**

Up to now, labels in lists might have been truncated. We have now enabled wrapping for input list items, which is already a feature for standard list items. We have also introduced the `contentSize` property to adjust the behavior for input controls of different sizes. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.InputListItem%23methods/getContentSize).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**sap.m.plugins.CellSelector** 

</td>
<td valign="top">

**sap.m.plugins.CellSelector**

We have now made the `selectionChange` event public. The event indicates that the user changed the selection of cells. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector%23events).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**sap.ui.mdc.Table** 

</td>
<td valign="top">

**sap.ui.mdc.Table**

We have enabled the interactive row mode for tables of type `GridTableType`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.enums.TableRowCountMode%23overview).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MultiComboBox`** 

</td>
<td valign="top">

**`sap.m.MultiComboBox`**

We have corrected the accessibility validation to hide the checkbox from the accessibility tree and make it non-interactive. This ensures compliance with the latest accessibility standards.

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Types** 

</td>
<td valign="top">

**OpenUI5 Types**

The parse error messages of the following types now contain an example showing the expected format:

-   `sap.ui.model.type.Date`
-   `sap.ui.model.type.Time`
-   `sap.ui.model.type.DateTime`
-   `sap.ui.model.type.DateInterval`
-   `sap.ui.model.type.TimeInterval`
-   `sap.ui.model.type.DateTimeInterval`

<sub>Changed•Feature•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Formatter** 

</td>
<td valign="top">

**OpenUI5 Formatter**

When using the currency instance of `sap.ui.core.format.NumberFormat#getCurrencyInstance` without providing custom currencies, the number of decimals defined in the Unicode Common Locale Data Repository for the given currency is used when formatting the amount unless the `decimals` format option is provided.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.format.NumberFormat%23methods/sap.ui.core.format.NumberFormat.getCurrencyInstance).

<sub>Changed•Feature•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

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

-   The support for `OneWay` property bindings for properties of complex type, introduced as an experimental feature with OpenUI5 1.126, is now available; you can use it in productive applications.

    For more information, see [Property Binding With an Object Value](Initialization_and_Read_Requests_fccfb2e.md#loiofccfb2eb41414f0792c165e69a878717__section_PBOV).

-   The selection feature introduced with OpenUI5 1.111 is now available and can be used productively.

    For more information, see [Selection](Selection_ec55312.md)and the API Reference for [`v4.Context#setSelected`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/setSelected) and [`#isSelected`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/isSelected).

-   The `createInPlace` property, introduced as an experimental feature with OpenUI5 1.126 for the `$$aggregation` binding parameter and the `sap.ui.model.odata.v4.ODataListBinding#setAggregation` API, is now available and can be used productively.

    For more information, see [Recursive Hierarchy](Data_Aggregation_and_Recursive_Hierarchy_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH)and the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/setAggregation).

-   The `sap.ui.model.odata.v4.Context#expand` method now returns a `Promise`.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/expand).

-   We have provided the new `sap.ui.model.odata.v4.Context#getFilter` method. It returns an `sap.ui.model.Filter` corresponding to the context.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/getFilter).


<sub>Changed•Feature•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit: Improved search in collapsed nodes** 

</td>
<td valign="top">

**Demo Kit: Improved search in collapsed nodes**

Previously, when using a browser search \([Ctrl\] + [F\] \) or the Demo Kit’s global search, results in collapsed nodes, such as code samples or sections, wouldn’t be highlighted. These nodes would remain collapsed. We’ve improved this experience, and now when users perform a search that includes collapsed nodes, the nodes expand, and the search term is highlighted.

<sub>Changed•Feature•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

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

We’ve added a new `beforeOpen` event. This event indicates that the control is opening and triggers before the `sap.m.SelectList` opens.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Select).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Avatar`** 

</td>
<td valign="top">

**`sap.m.Avatar`**

We have improved the control behavior. The magnifier icon is no longer displayed for avatars when an icon URI is set as the source image.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Avatar).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Carousel`** 

</td>
<td valign="top">

**`sap.m.Carousel`**

To improve the accessibility of the control, we have set the navigation arrows to be always visible on touch devices. The behavior on desktop devices doesn't change - the navigation arrows are always shown, except when the arrows are placed over the content \(`sap.m.CarouselArrowsPlacement.Content`\) when they are shown only on hover. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithDisplayOptions).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

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

We have enhanced the options for date ranges of type *Last X Minutes / Hours / Days / Weeks / Months / Quarters / Years* and *Next X Minutes / Hours / Days / Weeks / Months / Quarters / Years*. Until now, the control has returned intervals that exclude the current period. For example, if today is 17 October 2024, then `Last 2 Days` would return the interval `15 October 2024 – 16 October 2024`. We have now added additional options and the users also have the choice to include the current period. Therefore, in the same example, the control would return `16 October 2024 – 17 October 2024`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.DynamicDateRange/sample/sap.m.sample.DynamicDateRange).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TableSelectDialog`** 

</td>
<td valign="top">

**`sap.m.TableSelectDialog`**

We have improved the UX of the control when the dialog is in single-selection mode and the `rememberSelections` property is set. When a user selects an item and reopens the dialog, the selection is preserved. Now, if the user selects the same item again, the dialog closes automatically. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TableSelectDialog).

<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
<tr>
<td valign="top">

1.130 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

****

`sap.ui.integration.widgets.Card`

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   Application developers can now specify the first day of the week in a Calendar card by setting the option `calendarWeekNumbering` in the card manifest to one of the available options: `Default`, `ISO_8601`, `MiddleEastern`, or `WesternTraditional`. For more information, see the [API Reference](https://sdk.openui5.orgapi/module:sap/base/i18n/date/CalendarWeekNumbering) and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/calendar).

-   We have added a new `use12HourFormat` Boolean property to the Calendar card, which enables developers to display the card either in 24-hour \(default\) or 12-hour format.

-   We have improved the UX in the pagination for List, Table, and Timeline cards. Previously, users could flip back and forth through the items of the card in place. Now, they can scroll through the items. Scrolling happens in a separate card, which opens in a dialog after selecting the *Show More* button. For more information, see the [Pagination](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/pagination) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/pagination/server).

-   The Component card now supports file upload functionality. To achieve this, we have enhanced the card’s `request` method to support parameters of type `FormData`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card/methods/request) and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/uploadFile).

-   We have introduced a new `fitType` property for icons in the Default Header and in the Object card. You can use it to define how the image fits in the icon space. The new property accepts values from the `sap.m.AvatarImageFitType` enum, with the default value `Cover`. For more information, see the [Default Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/default) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/iconFitType).


<sub>Changed•Control•Info Only•1.130</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-10-31

</td>
</tr>
</table>

