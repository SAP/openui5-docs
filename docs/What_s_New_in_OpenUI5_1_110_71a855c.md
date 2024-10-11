<!-- loio71a855cfc8ad43b2b19f03bcce65bef4 -->

| loio |
| -----|
| 71a855cfc8ad43b2b19f03bcce65bef4 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/71a855cfc8ad43b2b19f03bcce65bef4) | [demo kit latest release](https://sdk.openui5.org/topic/71a855cfc8ad43b2b19f03bcce65bef4)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.110

With this release OpenUI5 is upgraded from version 1.109 to 1.110.

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

1.110 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.p13n.Engine`** 

</td>
<td valign="top">

**`sap.m.p13n.Engine`**

We have provided a new entity that allows custom control developers and application developers to make use of available personalization settings for their controls, for example, for sorting, grouping, and managing variants, and handling personalization states. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.p13n.Engine) and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.Engine).

<sub>New•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Copy-to-Clipboard Feature for Tables** 

</td>
<td valign="top">

**Copy-to-Clipboard Feature for Tables**

Users can copy selected table content to the clipboard and use it anywhere inside or outside an app. To achieve this, we have introduced the new `sap.m.plugins.CopyProvider` plugin. To extract the cell data from the table, we have created the `extractData` property. This new feature is available for grid and responsive tables. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CopyProvider).

<sub>New•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

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

<sub>Deprecated•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.table.ColumnMenu`** 

</td>
<td valign="top">

**`sap.m.table.ColumnMenu`**

We have introduced a new control that allows users to do the following in grid and responsive tables:

-   Quick sorting

-   Quick filtering

-   Quick grouping

-   Quick selection of columns

-   Quick totaling


These features are available in a menu that users can choose in the column headers of the tables. Applications can define their own application-specific quick actions. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.columnmenu)  and the [Sample](https://sdk.openui5.org/entity/sap.ui.comp.smarttable.SmartTable/sample/sap.ui.comp.sample.smarttable). 

<sub>New•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Header Bar in Key User Adaptation** 

</td>
<td valign="top">

**Header Bar in Key User Adaptation**

The header bar in key user adaptation has been redesigned.

-   The *Save & Exit* button has been replaced by two separate buttons for *Save* \(:floppy_disk:\) and *Exit* \(:x:\).

-   For each action, an icon is now displayed.

-   Actions that are available in some environments only, like *Translate*, *Manage App Variants*, and *Save As*, have been moved to a *More Actions* menu that key users access by clicking on a new hamburger icon \(<span class="SAP-icons-V5"></span>\).

    When the *More Actions* menu has no entries, like in the demo apps in the SAPUI5 demo kit, the hamburger icon is hidden.


The following screenshot shows an example:

![](images/loio00fdcc7e160c4395a3b98824accc64a4_LowRes.png)

<sub>Changed•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

****`sap.m.PlanningCalendar, sap.m.SinglePlanningCalendar`**, and **`sap.ui.core.format.DateFormat`**** 

</td>
<td valign="top">

****`sap.m.PlanningCalendar, sap.m.SinglePlanningCalendar`**, and **`sap.ui.core.format.DateFormat`****

We have adapted our Date and Time controls to support the calendar week based on the `sap.ui.core.format.DateFormat` options.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.format.DateFormat). 

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ObjectStatus`** 

</td>
<td valign="top">

**`sap.m.ObjectStatus`**

We have implemented a new property to give application developers the ability to override the default state announcement. Now the `group` role isn't placed on inactive control instances and a proper `roledescription` is set for active control instances.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectStatus). 

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.core.ScrollEnablement`** 

</td>
<td valign="top">

**`sap.ui.core.ScrollEnablement`**

We have added a new option to the `scrollToElement` API method of the `sap.ui.core.ScrollEnablement` class. If the new `bSkipElementsInScrollport` parameter is set to `true`, scrolling will happen only if necessary. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.delegate.ScrollEnablemen/methods/scrollToElement).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IllustratedMessage`** 

</td>
<td valign="top">

**`sap.m.IllustratedMessage`**

The `IllustratedMessage`'s sample of the default set of illustrations is now split into three different samples depending on their visual style: classic, illustrative, and simple.

For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.IllustratedMessage).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ComboBox`** 

</td>
<td valign="top">

**`sap.m.ComboBox`**

We have updated the behavior of the `loadItems` API. Now, when the picker is open and no items are loaded - the *No data* label is loaded in the list. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxLazyLoading).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit: Improved main theme selection** 

</td>
<td valign="top">

**Demo Kit: Improved main theme selection**

We have added the latest high contrast themes to the main theme selector in the Demo Kit.![](images/loiob76a17bb50f04301b6b21dd28ee048c5_Source1.png)

<sub>Changed•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   List and Object cards can now display \(default\) icons for object attributes of states `Error`, `Warning`, `Success` or `Information`. The icons are shown if the new `showStateIcon` property is set to `true`. For more information, see the [Attributes](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/attributes) and the [Form Inputs](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/form) examples in the Card Explorer.

-   We have improved the loading of the libraries that are specified in the `dependencies` attribute of the `sap.ui5` namespace. This option allows you to use other libraries in the card. For more information, see the [Card Manifest](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/cardManifest) section and the [Shared Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/sharedExtension) example in the Card Explorer.

-   As a card developer, you can now dynamically hide the filters in the card using the new `visible` property. For more information, see the [Multiple Filters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/searchFilter/multipleFilters) example in the Card Explorer.


<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SelectDialog`** 

</td>
<td valign="top">

**`sap.m.SelectDialog`**

You can now control the placeholder text in the inner search field using the new `searchPlaceholder` property. If not set, the word `Search` in the current local language or in English will be used as a placeholder.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialog) and the [Sample](https://sdk.openui5.org/entity/sap.m.SelectDialog/sample/sap.m.sample.SelectDialog).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Dialog`** 

</td>
<td valign="top">

**`sap.m.Dialog`**

We have added a new `footer` aggregation of type `sap.m.Toolbar` to the control. You can now use this horizontal container to display controls that fit different custom scenarios, for example, a button that shows a message popover.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Dialog) and the [Sample](https://sdk.openui5.org/entity/sap.m.Dialog/sample/sap.m.sample.DialogWithMessagePopover).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

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

Using the new `backgroundDesign` property, you can now set the carousel’s background color as `Translucent` \(Default\), `Solid`, or `Transparent`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Carousel) and the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithDisplayOptions).

<sub>Changed•Control•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

****OpenUI5 Formatters**** 

</td>
<td valign="top">

****OpenUI5 Formatters****

The new version of OpenUI5 introduces the following formatting features:

-   You can now use the `sap-timezone` URL parameter for testing an application in a different time zone by specifying an IANA time zone, such as "America/New\_York". We do not recommend using this parameter in a productive environment. For more information, see [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md) .
-   We have restricted the use of fallback patterns without delimiters in `DateFormat`. Successful parsing now requires that the length matches, as only then year, month, and day values can reliably be attributed.
-   We have updated the OpenUI5 locale data to Version 41 of the Unicode Common Locale Data Repository \(CLDR\). With this upgrade, unit keys have changed incompatibly in the CLDR. A legacy unit mapping ensures that previous unit keys are still supported when formatting. Parsing of user input will provide the current unit keys. For more information, see [Legacy Unit Mapping](Unit_Formatting_8e618a8.md#loio8e618a8d93cb4f92adc911b96047eb8d__section_LUM).

<sub>Changed•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
<tr>
<td valign="top">

1.110 

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

-   Requesting `$count` and using `sap.ui.model.odata.v4.ODataListBinding#getDownloadUrl` now work with the experimental hierarchy feature introduced with OpenUI5 1.105. For more information, see the API Reference for [`getDownloadUrl`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/getDownloadUrl) and the `hierarchyQualifier` in [`setAggregation`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation), and[Binding Collection Inline Count](Binding_Collection_Inline_Count_77d2310.md).
-   The `synchronizationMode` model parameter is now optional and deprecated.
-   User input into inactive rows is now regarded as a pending change by `sap.ui.model.odata.v4.Context#hasPendingChanges`; it can be reset using `sap.ui.model.odata.v4.Context#resetChanges`. You can prevent the activation of inactive rows after user input since OpenUI5 1.109 using `sap.ui.base.Event#preventDefault` in the handler of the `createActivate` event.For more information, see the API Reference for [`hasPendingChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/hasPendingChanges), [`resetChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/resetChanges), and [`preventDefault`](https://sdk.openui5.org/api/sap.ui.base.Event/methods/preventDefault).
-   The `sap.ui.model.odata.v4.ODataModel` now supports the `propertyChange` event.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/events/propertyChange).

<sub>Changed•Feature•Info Only•1.110</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-01-26

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

