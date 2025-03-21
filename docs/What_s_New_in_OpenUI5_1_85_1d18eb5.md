<!-- loio1d18eb5973ac477ba87f16057adb2571 -->

| loio |
| -----|
| 1d18eb5973ac477ba87f16057adb2571 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/1d18eb5973ac477ba87f16057adb2571) | [demo kit latest release](https://sdk.openui5.org/topic/1d18eb5973ac477ba87f16057adb2571)</div>

## What's New in OpenUI5 1.85

With this release OpenUI5 is upgraded from version 1.84 to 1.85.

***

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

1.85 

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

-   We now provide the `sap.ui.model.odata.v4.ODataModel#getMessages` method for use by `sap.ui.model.Context#getMessages`. Both methods can be used to highlight table rows with messages. For more information, see [Highlighting Table Rows with Messages](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md#loiofbe1cb5613cf4a40a841750bf813238e__section_highlighting_table_rows).

-   The `sap.ui.model.odata.v4.ODataListBinding#refresh` method is now supported for kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.
-   When using `groupLevels` with the `$$aggregation` list binding parameter, we now support grand totals.
-   `TargetProperties` of type `edm.String` are supported in accordance with recent changes to the `SideEffectsType` and can be directly provided to the `sap.ui.model.odata.v4.Context#requestSideEffects` method.
-   You can now set the value of an instance annotation for a newly created or already existing entity. The set value is sent to the back end in a `POST` or `PATCH` request, respectively.

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Special Messaging Support for Visually Impaired Users** 

</td>
<td valign="top">

**Special Messaging Support for Visually Impaired Users**

The `sap.ui.core.InvisibleMessage` class is no longer experimental. This class is used to programmatically expose dynamic content changes that can be announced by the screen reader. For more information, see [Invisible Messaging](Invisible_Messaging_b9a7d6f.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.core.InvisibleMessage) and the [Sample](https://sdk.openui5.org/entity/sap.ui.core.InvisibleMessage).

<sub>Changed•Feature•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.GridContainer`** 

</td>
<td valign="top">

**`sap.f.GridContainer`**

We have improved the two-dimensional keyboard navigation. Now navigation using the [Arrow Keys\] follows the configurable two-dimensional grid. This model provides stable navigation paths when there are items of different sizes. When the user presses an [Arrow Key\] in a direction outward of the `GridContainer`, a `borderReached` event is fired. The implementation of the `borderReached` event allows the application developer to control where the focus goes and \(depending on the surrounding layout\) to pass the focus to a specific place in a neighboring `GridContainer` using the `GridContainer#focusItemByDirection` method. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainersNavigation).

<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Bar`** 

</td>
<td valign="top">

**`sap.m.Bar`**

We have added a new `titleAlignment` property. It enables developers to create custom headers for controls that use headers based on `sap.m.Bar` and to achieve proper title alignment. To keep the default `Bar` behavior \(when it is not used as a header\), we have added a new value `None` \(default\) to the `sap.m.TitleAlignment` enumeration. If the `titleAlignment` value is set to `Start` or `Center`, the horizontal alignment of the `contentMiddle` aggregation of `sap.m.Bar` accepts the same setting. If the `titleAlignment` is set to `Auto`, the `contentMiddle` aggregation is set according to the default theme setting. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Bar).

<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ColorPalette`, `sap.m.ColorPalettePopover`, and `sap.ui.unified.ColorPickerPopover`** 

</td>
<td valign="top">

**`sap.m.ColorPalette`, `sap.m.ColorPalettePopover`, and `sap.ui.unified.ColorPickerPopover`**

A `liveChange` event is now available in these controls, which are using the `sap.ui.unified.ColorPicker` internally. This event is used to propagate real-time color changes from inside the `ColorPicker` before closing the popover that contains this `ColorPicker`. For more information, see the [ColorPickerPopover](https://sdk.openui5.org/entity/sap.ui.unified.ColorPicker/sample/sap.ui.unified.sample.ColorPickerPopover) and the [ColorPalettePopover](https://sdk.openui5.org/entity/sap.m.ColorPalette/sample/sap.m.sample.ColorPalettePopover) samples.

<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

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

The `specialDates` aggregation, which allows you to define special dates for the control, is now visible in the Month view for all supported SAP themes. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Table`** 

</td>
<td valign="top">

**`sap.m.Table`**

> ### Caution:  
> This feature is no longer in place as of 1.85.1. as the default behavior . For more information , see the What’s New in 1.86 and the [API Reference](https://sdk.openui5.org/api/sap.m.Table) for `fixedLayout`. 

If the sum of the width of all columns in a table is less than the available space for the whole table, we now render a placeholder column to occupy the remaining unused space. This feature is enabled by default.

![](images/loio1da07e72426044b6a23a58549b95e2b5_Source1.png)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table).

<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
<tr>
<td valign="top">

1.85 

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

-   You can now configure the `min-height` of the content within Analytical and Component cards. To achieve this, add the <code>“minHeight”: “&lt;<i>CSS value</i>&gt;”</code> property to the `content` section of the manifest. For more information, see the [Analytical Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/analytical) and [Component Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/component) sections in the Card Explorer.

-   We have added a new `actionDefinitions` \(experimental\) aggregation. It defines the action buttons that appear in the card-header menu. The `actionDefinitions` is of type `sap.ui.integation.ActionDefinition`, which allows developers to add, remove, or modify the actions at any time. This aggregation replaces the \(deprecated\) `actions` property of `sap.ui.integration.Extension`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card/Aggregations) in the Demo Kit and the [Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/customActions) and [Component Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/customActions) samples in the Card Explorer.


<sub>Changed•Control•Info Only•1.85</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-12-03

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.133](What_s_New_in_OpenUI5_1_133_86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

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

