<!-- loio9d87044050f44763a2aeabff0a7a6bb2 -->

| loio |
| -----|
| 9d87044050f44763a2aeabff0a7a6bb2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/9d87044050f44763a2aeabff0a7a6bb2) | [demo kit latest release](https://sdk.openui5.org/topic/9d87044050f44763a2aeabff0a7a6bb2)</div>

## What's New in OpenUI5 1.125

With this release OpenUI5 is upgraded from version 1.124 to 1.125.

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

1.125 

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

In the table in the `View Settings` dialog \(`P13n`\), you can now use the `Select All` option to select all columns at once to make them visible. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc.Table/sample/sap.ui.mdc.demokit.sample.TableJson).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.filterbar.vh.FilterBar`, `sap.ui.mdc.filterbar.vh.CollectiveSearchSelect`** 

</td>
<td valign="top">

**`sap.ui.mdc.filterbar.vh.FilterBar`, `sap.ui.mdc.filterbar.vh.CollectiveSearchSelect`**

To make it easier to find value-help-related entities, we have moved these controls to the `sap.ui.mdc.valuehelp` namespace.

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` ** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` **

To enable automatic resizing of columns, we have introduced the `autoResizeColumn` function. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Column%23methods/getAutoResizable).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.p13n.Engine` ** 

</td>
<td valign="top">

**`sap.m.p13n.Engine`**

We have added a tutorial that allows you to build and try out your own artifacts based on the controls in the <code><code>P13n</code></code> class. For more information, see the [P13nify Everything - Personalization for Any Control](https://github.com/SAP-samples/ui5-p13n-tutorial).



<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.mdc` library** 

</td>
<td valign="top">

**`sap.ui.mdc` library**

We have added a tutorial that allows you to build and try out your own artifacts based on the controls in the `sap.ui.mdc` library. For more information, see the [OpenUI5 MDC Tutorial](https://github.com/SAP-samples/ui5-mdc-json-tutorial).

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

**`sap.ui.mdc.Table`, `sap.ui.mdc.table.DragDropConfig`**

-   We have enhanced the `DropInfo` configuration: You can now use `preventDefault` for the `dragover` event. This way, you can disable dropping on a specific location, for example, between two table rows. To help consumers find out whether to prevent the default of the `dragenter` event when dragging over the edge of two DOM nodes, we have also added the `dropPosition` parameter to the event. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.dnd.DropInfo%23events/dragOver) for the `dragOver` event and the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.DragDropConfig%23events/Summary) for `DragDropConfig`. 

-   We have introduced the `browserEvent` parameter for all drag-and-drop-related events in `DragDropConfig` allowing consumers to access the `DataTransfer` object. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.table.DragDropConfig).


<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Resource Model** 

</td>
<td valign="top">

**OpenUI5 Resource Model**

We have deprecated the `async` parameter of the `sap.ui.model.resource.ResourceModel` API. A warning is now logged if the `async` parameter is not set to `true`.

<sub>Deprecated•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

The maintenance of recursive hierarchies is no longer experimental; you can now use it in productive applications. For more information, see [Recursive Hierarchy](Data_Aggregation_and_Recursive_Hierarchy_7d91431.md#loio7d914317c0b64c23824bf932cc8a4ae1__section_RCH).

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Icon Explorer** 

</td>
<td valign="top">

**Icon Explorer**

We have added the following new icons to the SAP Fiori Tools icon font:

-   business-application-studio
-   clone-from-git
-   business-accelerator

Find the icon that fits your needs using the [Icon Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/iconExplorer/webapp/index.html) tool. 

<sub>Changed•Feature•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

You can now display the carousel’s page indicator over the content. To enable this behavior, we have created a new `sap.m.CarouselPageIndicatorPlacementType` enumeration, that replaces the old `sap.m.PlacementType`. The new enumeration has two additional values that you can use for this purpose - `OverContentTop` and `OverContentBottom`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Carousel) and the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithDisplayOptions).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

Using the new `noData` aggregation, you can now set the control to display an illustrated message when there is no data available. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

-   To enhance the accessibility of the control, we have enabled screen readers to announce information about the number of appointments hidden in the *More* button, along with the corresponding date of these appointments.
-   We have added a new `sourceLink` property to the `moreLinkPress` event. The new property enables developers to identify the exact *More* button that has been pressed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
<tr>
<td valign="top">

1.125 

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

-   You can now set the card to display a custom image loaded from the extension, rather than the default illustrated message. For more information, see the [Custom Image Message](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/customImage) sample in the Card Explorer.
-   The rendered card now has a `data-help-id` attribute set on its root element. This `data-help-id` is useful when you want to connect the card with a help system for the end user, for example SAP Companion. For more information, see the [Help ID](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/helpId) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.125</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-06-13

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

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

