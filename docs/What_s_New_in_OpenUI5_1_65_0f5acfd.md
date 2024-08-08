<!-- loio0f5acfddbcfd49258e07ad44770bfaa7 -->

| loio |
| -----|
| 0f5acfddbcfd49258e07ad44770bfaa7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0f5acfddbcfd49258e07ad44770bfaa7) | [demo kit latest release](https://sdk.openui5.org/topic/0f5acfddbcfd49258e07ad44770bfaa7)</div>

## What's New in OpenUI5 1.65

With this release OpenUI5 is upgraded from version 1.64 to 1.65.

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

1.65 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**New Theme Available** 

</td>
<td valign="top">

**New Theme Available**

A new theme with *SAP Quartz Light* as the default appearance \(theme ID `sap_fiori_3`\) has been introduced. The theme is provided as an additional theme in OpenUI5.

For more information, see [Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md).

<sub>New•Feature•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.GridContainer (Experimental)`** 

</td>
<td valign="top">

**`sap.f.GridContainer (Experimental)`**

The new `GridContainer` control allows you to align tiles, cards, and other controls in configuration, such as an overview page. It relies on a regular grid mesh constructed of rows with the same height and columns with the same width. Each item can be configured to span a different number of rows and columns inside that mesh. `GridContainer` automatically calculates how many rows an item needs, based on the height of the item.

![](images/loio2916482f87df4b91afabd81d6070fc78_HiRes.png)

For more information, see [sap.f.GridContainer](sap_f_GridContainer_cca5ee5.md), the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer), and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainer).

<sub>New•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

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

-   You can now create more than one transient entity in a list binding without refreshing the list binding, see `sap.ui.model.odata.v4.ODataListBinding` in the API Reference.

-   `$count` reflects the number of records shown in the table. Duplicates are avoided by filtering out created and persisted records using system query option `$filter`.

-   You can use `@$ui5.context.isTransient` in expression bindings to find out whether context is transient, see It is now ensured that created and persisted records are shown only once in the list, and that `sap.ui.model.odata.v4.Context.isTransient` in the API Reference.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Test Automation** 

</td>
<td valign="top">

**Test Automation**

The setup for Karma-based test automation has been improved significantly: The corresponding plugin has been completely reworked and renamed to `karma-ui5`.

For more information, see [Installing Karma for Automated Testing](Test_Automation_ae44824.md#loioa182676ed3714bd5b4f011eb29076f6c) and [karma-ui5 on Github](https://github.com/SAP/karma-ui5).

<sub>Changed•Feature•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.Avatar`** 

</td>
<td valign="top">

**`sap.f.Avatar`**

With the new `fallbackIcon` property, you can define a fallback icon to be displayed if the image `src` is incorrect and no `initials` are set. If `fallbackIcon` is not set, a default fallback icon is displayed depending on the value of the `displayShape` property.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.Avatar) and the [Sample](https://sdk.openui5.org/entity/sap.f.Avatar/sample/sap.f.sample.Avatar).

<sub>Changed•ControlControl•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`**

-   We have implemented a new sticky subheader in the `DynamicPage` control. It is positioned below the `DynamicPageHeader` and is always visible \(sticks to the `DynamicPageTitle` when the header is collapsed\). You can implement the subheader with the new `stickySubheader` association, which accepts controls that implement the `sap.f.IDynamicPageStickyContent` interface.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPage) and the [Sample](https://sdk.openui5.org/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageWithStickySubheader).

-   We have improved the visual design of the content set in the `snappedContent` and `expandedContent` aggregations of `sap.f.DynamicPageTitle`. The width of the content set in these aggregations and the `heading` aggregation are no longer dependent.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.DynamicPage/sample/sap.f.sample.DynamicPageFreeStyle).


<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.ShellBar`** 

</td>
<td valign="top">

**`sap.f.ShellBar`**

The control is no longer experimental. To comply with the latest UX guidelines, its child controls have a predefined semantic order and are displayed in their cozy content density mode with dark visual design.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ShellBar) and the [Sample](https://sdk.openui5.org/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBar).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

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

We have improved the `sap.m.Select` control to display the text set in the `valueStateText` property on multiple lines when the dropdown list is opened. The implementation ensures that the value state text is displayed even though it is longer than the width of the `sap.m.Select` container.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Select) and the [Sample](https://sdk.openui5.org/entity/sap.m.Select/sample/sap.m.sample.SelectValueState).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

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

-   You can now change the start and end date of appointments by selecting and dragging their top or bottom end and dropping it on the desired time interval. Use the new `enableAppointmentsResize` property to enable the feature.

-   You can now create appointments by clicking and dragging. Select a start \(or end\) time interval in an empty cell, start dragging up \(or down\) over the time intervals to determine the desired time interval. Use the new `enableAppointmentsCreate` property to enable the feature.

-   We have improved the visual design of appointments that are shorter than 30 minutes. The color bar at the left border of appointments now has variable height to represent the time interval accurately. For appointments that are 30 minutes or longer, it fills 100% of the height.

-   You can now focus on individual cells in the `SinglePlanningCalendar` and navigate between them using the keyboard. When pressing the [Space\] or [Enter\] key on a focused cell, the new `cellPress` event is fired, which can be used for creating an appointment.

-   We have improved the visual design of the control by adding a shadow effect below the sticky header so that it is easier for the user to recognize the line between the fixed header and the scrollable content.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Samples](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ToolbarSeparator`** 

</td>
<td valign="top">

**`sap.m.ToolbarSeparator`**

We have enabled the control to move to the overflow area of `sap.m.OverflowToolbar` where it changes its layout from vertical to horizontal. If the control happens to be the first or the last item of the overflow area, it is not displayed.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.OverflowToolbar/sample/sap.m.sample.OverflowToolbarSimple).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.core.hyphenation.Hyphenation`** 

</td>
<td valign="top">

**`sap.ui.core.hyphenation.Hyphenation`**

We have changed the `leftmin` and `rightmin` properties for all languages, with the default value of 3 characters. `leftmin` defines the minimum of characters to remain on the previous line, and `rightmin` defines the minimum of characters to move to the new line.For more information, see [Hyphenation for Text Controls](Hyphenation_for_Text_Controls_6322164.md) and the [API Reference](https://sdk.openui5.org/api/sap.ui.core.hyphenation.Hyphenation). 

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

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

-   We have introduced a new `Table` card type, that displays a set of items in a table format. Table cards use the responsive UI5 control `sap.m.Table`.

-   We have introduced a new experimental card type - `Component` card. It is used to display multiple controls. The `Component` card is used as a custom approach for use cases that do not fit in other card types and structures. The content area of the unstructured content card can be moved to the top.

    > ### Note:  
    > In contrast to the other integration card types, the structure and behavior of the `Component` card are custom-definable and follow the established OpenUI5 Component model. For more information, see [Components](Components_958ead5.md).


For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://sdk.openui5.org//#/api/sap.ui.integration.widgets.Card), and the [Samples](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.ObjectPageHeader`** 

</td>
<td valign="top">

**`sap.uxap.ObjectPageHeader`**

-   We have improved the visual appearance of the image placed in `ObjectPageHeader` to be identical with the styling of the `sap.f.Avatar` control.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageDynamicHeader).

-   When the user presses an action from the overflow area, a dialog should open and the action sheet should close. To notify the app developer that the action is in the overflow area, we now pass an additional `bInOverflow` parameter along with the `press` event of the control set in the `actions` aggregation of the `sap.uxap.ObjectPageHeader`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageHeader).

<sub>Changed•Control•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

New 

</td>
<td valign="top">

User Documentation 

</td>
<td valign="top">

**New openSAP Course: Evolved Web Apps with SAPUI5** 

</td>
<td valign="top">

**New openSAP Course: Evolved Web Apps with SAPUI5**

We have launched a new openSAP course on how to develop professional web apps with UI5. Key highlights:

-   Evolved best practices and recommendations for app developers
-   New UI5 innovations \(drag and drop, OData V4, XML composites\)
-   Developer productivity tools and features in SAP Web IDE
-   Optimizing apps with the UI5 Tooling
-   Configuring apps for SAP Fiori elements and SAP Fiori launchpad
-   Adapting apps with SAPUI5 flexibility

The key concepts shown in this course apply to both, SAPUI5 and OpenUI5. The course is aimed at intermediate to advanced developers but is also suitable for ambitious UI5 beginners. Participation is free of charge.

For more information and to enroll, see [https://open.sap.com/courses/ui52](https://open.sap.com/courses/ui52).

![](images/loio56cac78b078f4cf3ada1fc92a9430182_LowRes.png)

<sub>New•User Documentation•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
<tr>
<td valign="top">

1.65 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit Search** 

</td>
<td valign="top">

**Demo Kit Search**

We have improved the global search capabilities in the Demo Kit app by migrating to a client-side search based on Elasticlunr.js.

![](images/loio36a8538c55c3402b9c7adef4df7cba2c_HiRes.png)

<sub>Changed•Feature•Info Only•1.65</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-04-25

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

