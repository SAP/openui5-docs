<!-- loioa9553fe29f174452ae86de7b6da4b5f6 -->

| loio |
| -----|
| a9553fe29f174452ae86de7b6da4b5f6 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/a9553fe29f174452ae86de7b6da4b5f6) | [demo kit latest release](https://sdk.openui5.org/topic/a9553fe29f174452ae86de7b6da4b5f6)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.113

With this release OpenUI5 is upgraded from version 1.112 to 1.113.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

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

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.p13n*`** 

</td>
<td valign="top">

**`sap.m.p13n*`**

We have further improved the usability and accessibility of the *View Settings* dialog: You can now move items up and down using keyboard shortcuts. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.comp.smarttable.SmartTable/sample/sap.ui.comp.sample.smarttable).

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

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

<sub>Deprecated•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Code Coverage Powered by `Istanbul`** 

</td>
<td valign="top">

**Code Coverage Powered by `Istanbul`**

OpenUI5 already provides a deep integration of `QUnit` and code coverage measurement. We now introduce `Istanbul` as a modern JavaScript code instrumenter, which is intended to eventually replace the former, now legacy solution based on `Blanket.js`.

To start taking advantage of the more future-proof and feature-rich `Istanbul` solution, see the updated [code coverage documentation](Code_Coverage_Measurement_7ef3242.md).

<sub>Changed•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Date and Time Formatting** 

</td>
<td valign="top">

**OpenUI5 Date and Time Formatting**

The new version of OpenUI5 introduces the following formatting features:

-   You can now centrally configure calendar week numbering via the new `calendarWeekNumbering` configuration parameter. Note that the `calendarWeekNumbering` format option introduced with OpenUI5 1.108 for `sap.ui.core.format.DateFormat` overrules the central configuration.

    For more information, see [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

-   We provide the new `intervalDelimiter` format option for `sap.ui.core.format.DateFormat`. If an `intervalDelimiter` is set, the locale-specific rules for displaying a range as defined in the Common Locale Data Repository are overruled; the two parts of the range are formatted individually, and the given delimiter is used.


<sub>Changed•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

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

-   You can now delete nested transient records that were created using the experimental Deep Create feature provided with OpenUI5 1.112. Any initial data handed over to `sap.ui.model.odata.v4.ODataListBinding#create` can now contain nested entities.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/create).

-   In read-only scenarios, you can now combine the experimental hierarchy feature introduced with OpenUI5 1.105 with the `sap.ui.model.odata.v4.Context#setKeepAlive` and `sap.ui.model.odata.v4.ODataModel#getKeepAliveContext` data synchronization methods described in [Data Reuse](Data_Reuse_648e360.md).

    For more information, see the API Reference for [`setKeepAlive`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/setKeepAlive) and [`getKeepAliveContext`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/getKeepAliveContext).

-   The `sap.ui.model.odata.v4.Context#resetChanges` API introduced as an experimental feature with OpenUI5 1.109 is now generally available.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/resetChanges).


<sub>Changed•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

You can now prevent the activation of a new inactive entity by using `sap.ui.base.Event#preventDefault` in the handler of the `createActivate` event of an `sap.ui.model.odata.v2.ODataListBinding`. Note that user input into inactive rows is regarded as a pending change by `sap.ui.model.odata.v2.ODataModel#hasPendingChanges`; it can be reset using `sap.ui.model.odata.v2.ODataModel#resetChanges`.

For more information, see the API Reference for [`hasPendingChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel/methods/hasPendingChanges), [`resetChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel/methods/resetChanges), and [`Event.preventDefault`](https://sdk.openui5.org/api/sap.ui.base.Event/methods/preventDefault).

<sub>Changed•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.112

</td>
<td valign="top">

Deleted 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q1/2023\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q1/2023\)**

> ### Note:  
> The following information concerns important upcoming changes for end users. These changes may require end users to adjust and/or test cases to be adapted, but they won't stop or disrupt software or processes.

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q1/2023.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.90
-   1.93
-   1.97
-   1.98

Action: Upgrade to a version that’s still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.52 to 1.38.53
    -   1.71.40-1.71.43
    -   1.84.20 to 1.84.22
    -   1.96.3 to 1.96.6

    Action: Upgrade to the latest available patch for the respective OpenUI5 version.


For more information, see [UI5 Releases Ending Service in 2023](https://blogs.sap.com/2022/12/05/ui5-releases-ending-service-in-2023/) and [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub>Deleted•Announcement•Required•1.112</sub>

</td>
<td valign="top">

Required 

</td>
<td valign="top">

2023-03-31

</td>
</tr>
<tr>
<td valign="top">

1.113 

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

-   Using the new `customStateIcon` property, you can now set custom state-icons for the items in Table, List, and Object cards. Before this change, states like `Error`, `Warning`, `Success`, or `Information`, only had default icons. For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/table) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/table/visibleColumns) in the Card Explorer.

-   Integration cards now support the `IllustratedMessage` control to provide more informative and consistent error messages. When the application is in debug mode \(when the URL parameter `sap-ui-debug=true` is set\), the *Show More* button opens a dialog with relevant additional \(more technical\) information.

-   We have enhanced the Table card with several new properties:

    -   You can use the new `highlight` property to show the state of each table row. Additionally, the `highlightText` property conveys the semantic of this state for better accessibility.
    -   The `additionalText` property gives you the option to display additional text in the table identifier column.

    For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/table) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/table/highlight) in the Card Explorer. 


<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.test.Opa5`** 

</td>
<td valign="top">

**`sap.ui.test.Opa5`**

We have introduced a new `fetchWaiter`, which checks for currently ongoing fetch requests.

<sub>Changed•Feature•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SuggestionsPopover`** 

</td>
<td valign="top">

**`sap.m.SuggestionsPopover`**

We have restricted the width of input suggestions to a maximum of 40 rem for optimal user experience. Limiting the width of suggestions allows users to easily scan and select options. However, if the input field is wider than 40 rem, the width of the suggestions matches the input’s width.

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

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

We have introduced a new `Survey` illustration type and four new illustrations to the default illustration set: `sapIllus-Dialog-NoColumnsSet`, `sapIllus-Dot-NoColumnsSet`, `sapIllus-Scene-NoColumnsSet`, and `sapIllus-Spot-NoColumnsSet`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage). 

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`** 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`**

We have implemented two new methods in the control's API, a trigger to open the native file upload picker and a getter to return the file input type element from the control DOM representation.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader). 

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.SidePanel`** 

</td>
<td valign="top">

**`sap.f.SidePanel`**

We have implemented an **enabled** property to the Side Panel item, which disables the controls and UI elements inside it.

For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.SidePanel/sample/sap.f.sample.SidePanel). 

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
<tr>
<td valign="top">

1.113 

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

We have implemented a new mode to select one or more dates in **SinglePlanningCalendar**. Тhe single day option is enabled by default, the multi-date selection option is possible by using a key combination \([Ctrl\] + [Meta key\]  and select the dates\) or by activating the new **MultiDateSelectionMode** property.

For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarDateSelection). 

<sub>Changed•Control•Info Only•1.113</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-04-20

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

