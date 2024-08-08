<!-- loio029d3b4a39c84384be6398c444f7e06a -->

| loio |
| -----|
| 029d3b4a39c84384be6398c444f7e06a |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/029d3b4a39c84384be6398c444f7e06a) | [demo kit latest release](https://sdk.openui5.org/topic/029d3b4a39c84384be6398c444f7e06a)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.117

With this release OpenUI5 is upgraded from version 1.116 to 1.117.

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

1.117 

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

We have deprecated the following entities for `sap.ui.table*`:

-   `sap.ui.table.ColumnMenu` and `sap.ui.table.AnalyticalColumnMenu`

-   `menu` aggregation of `Column`

-   `columnMenuOpen` event of `Column`
-   `columnVisibilityMenuSorter` property of `AnalyticalTable`

-   `showColumnVisibilityMenu` property of `Table`

-   `columnVisibility` event of `Table`

Instead of the deprecated `ColumnMenu`, you can use the `sap.m.table.columnmenu.Menu` control.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.columnmenu.Menu) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Menus).

<sub>Deprecated•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`** 

</td>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

To define the semantic level of a header, we have introduced the `headerLevel` property.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/getHeaderLevel).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)**

Refreshing table data via binding might be required if it has been changed in the back end. For example, a user might have selected *Go* in the filter bar without actually changing any filter settings. To evaluate whether the binding needs to be refreshed, even if `bindingInfo` has not changed, the `TableDelegate` uses the new `updateBinding` parameter `mSettings.forceRefresh`.

For more information, see the [API Reference](https://sdk.openui5.org/api/module:sap/ui/mdc/TableDelegate%23methods/sap/ui/mdc/TableDelegate.updateBinding).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

****Sample for `sap.ui.mdc` library**** 

</td>
<td valign="top">

****Sample for `sap.ui.mdc` library****

You can now test the table and filter bar features of the \(experimental\) `sap.ui.mdc` library in a sample. To find the sample for this library in the Demo Kit, go to *Samples* and select MDC Overview. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc/sample/sap.ui.mdc.demokit.sample.TableFilterBarJson).

<sub>New•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form.SimpleForm`** 

</td>
<td valign="top">

**`sap.ui.layout.form.SimpleForm`**

`ResponsiveGridLayout` is now the default layout for `SimpleForm` controls \(instead of `ResponsiveLayout`, which has already been deprecated\).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Modern ECMAScript Support in OpenUI5** 

</td>
<td valign="top">

**Modern ECMAScript Support in OpenUI5**

Since OpenUI5 1.116, the framework leverages features of modern ECMAScript up to and including [ECMAScript 2022 Language Specification](https://262.ecma-international.org/13.0/). There are certain restrictions you have to consider when using modern ECMAScript with your UI5 project.

For more information, see [ECMAScript Support](ECMAScript_Support_0cb44d7.md). Please also make sure to [upgrade your tools for modern ECMAScript in UI5](https://blogs.sap.com/2023/05/24/upgrade-your-tools-for-modern-ecmascript-in-ui5/).

<sub>Changed•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Theme-Dependent Custom Icon Fonts** 

</td>
<td valign="top">

**Theme-Dependent Custom Icon Fonts**

You can now configure variants of a custom icon font for different UI5 themes; previously, a custom icon font was applied to all themes. With an enhanced version of the metadata JSON file associated with an icon font, you can provide theme-dependent path configuration. For instance, this allows you to easily differentiate between custom icons for modern themes, such as SAP Horizon, and custom icons for older themes.

For more information and an example, see [Icon and Icon Pool](Icon_and_Icon_Pool_21ea0ea.md).

<sub>Changed•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

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

-   We now provide `withCredentials` as an experimental model parameter.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel).

-   **Experimental:** You can now create a nested single entity behind a single-valued navigation property in the transient entity.

    For more information, see *Nested Single Entity* in [Deep Create](Creating_an_Entity_c9723f8.md#loioc9723f8265f644af91c0ed941e114d46__section_DCR).

-   Support for read-only hierarchies is now available.

    For more information, see [Recursive Hierarchy](Data_Aggregation_and_Recursive_Hierarchy_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH).


<sub>Changed•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

New 

</td>
<td valign="top">

User Documentation 

</td>
<td valign="top">

**TypeScript Tutorial** 

</td>
<td valign="top">

**TypeScript Tutorial**

You are familiar with OpenUI5 app development, but do you want to learn how to do it in TypeScript? Now there is a video that guides you through the official UI5 TypeScript Tutorial, adds hints about how to avoid pitfalls, and provides some background information. To find it, see [UI5 TypeScript Tutorial video](https://youtu.be/CRKNIiXZN6U).

<sub>New•User Documentation•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`** 

</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`**

We have introduced a new `isOpen` method that indicates whether the menu is currently open. The `bOpen` flag in `sap.ui.unified.Menu`, which was used for similar purposes, will be phased out. If you use this flag in your applications, we recommend that you replace it with the new method. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Menu/methods/isOpen).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

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

Users can now select a whole week from the Month view if they click on the week number. A second click removes the selection. This feature is enabled when the `dateSelectionMode` property is set to `MultiSelect`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarDateSelection).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SelectDialog` and `sap.m.TableSelectDialog`** 

</td>
<td valign="top">

**`sap.m.SelectDialog` and `sap.m.TableSelectDialog`**

To improve the accessibility of these controls, we have introduced a new `initialFocus` property. It defines whether the initial focus will be received by the `SearchField` or by the `Content` list. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialogBase) and the [Sample](https://sdk.openui5.org/entity/sap.m.TableSelectDialog/sample/sap.m.sample.TableSelectDialogGrowing).

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OPA Framework** 

</td>
<td valign="top">

**OPA Framework**

We have enhanced the OPA framework to now perform comprehensive checks for component parents, ensuring controls nested within multiple layers are correctly treated when evaluating busy states.

<sub>Changed•Feature•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

</td>
</tr>
<tr>
<td valign="top">

1.117 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Panel`** 

</td>
<td valign="top">

**`sap.m.Panel`**

We have introduced the `stickyHeader` property. When set to `true`, the header of the panel will be visible while scrolling content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Panel/sample/sap.m.sample.PanelSticky). 

<sub>Changed•Control•Info Only•1.117</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-08-10

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

