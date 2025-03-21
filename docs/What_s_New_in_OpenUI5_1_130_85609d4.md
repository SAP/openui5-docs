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

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.133](What_s_New_in_OpenUI5_1_133_86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](What_s_New_in_OpenUI5_1_115_409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](What_s_New_in_OpenUI5_1_114_890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](What_s_New_in_OpenUI5_1_113_a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](What_s_New_in_OpenUI5_1_112_34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](What_s_New_in_OpenUI5_1_111_7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](What_s_New_in_OpenUI5_1_110_71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](What_s_New_in_OpenUI5_1_109_3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](What_s_New_in_OpenUI5_1_108_66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](What_s_New_in_OpenUI5_1_107_d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](What_s_New_in_OpenUI5_1_106_5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](What_s_New_in_OpenUI5_1_105_4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](What_s_New_in_OpenUI5_1_104_69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](What_s_New_in_OpenUI5_1_103_0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](What_s_New_in_OpenUI5_1_102_f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

