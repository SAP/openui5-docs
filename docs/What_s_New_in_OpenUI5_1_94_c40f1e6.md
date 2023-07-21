<!-- loioc40f1e63ca404cb1833c15ea90ff203a -->

| loio |
| -----|
| c40f1e63ca404cb1833c15ea90ff203a |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c40f1e63ca404cb1833c15ea90ff203a) | [demo kit latest release](https://sdk.openui5.org/topic/c40f1e63ca404cb1833c15ea90ff203a)</div>

## What's New in OpenUI5 1.94

With this release OpenUI5 is upgraded from version 1.93 to 1.94.

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

1.94 



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

We now provide the `sap.ui.model.odata.v2.Context#isTransient` method, which returns information about whether an entity created on the client is not yet saved in the back-end system.

<sub>Changed•Feature•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



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

-   Bound transition messages can now also be received in the `sap-messages` header. This can be useful if the payload, and hence any messages within the payload, is not available, for example in a success response of an action or function without corresponding return type. In this case, the server can send a bound transition message in the `sap-messages` header that the OData V4 model can forward to the message model.

-   XML templating can now process the `@com.sap.vocabularies.UI.v1.DoNotCheckScaleOfMeasureQuantity` annotation. This annotation prevents the validation of the number of decimals.

-   A new `@$ui5.node.groupLevelCount` instance annotation for data aggregation scenarios. It represents the number of direct children of a group node. For more information, see [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).


<sub>Changed•Feature•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Whitespaces Visualization** 



</td>
<td valign="top">

**Whitespaces Visualization**

We have created a new sample pattern that showcases how whitespaces can be enabled on the application level, for freestyle applications. For more information, see [Whitespaces Concept](Whitespaces_Concept_37deb0b.md) and the [Sample](https://sdk.openui5.org/entity/sap.m.WhitespacePattern). 

<sub>Changed•Feature•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.IconTabBar`** 



</td>
<td valign="top">

**`sap.m.IconTabBar`**

We have updated the colors of value-state status icons. Now, they have better color-contrast ratios for improved accessibility. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBar).

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Input`, `sap.m.MultiInput`** 



</td>
<td valign="top">

**`sap.m.Input`, `sap.m.MultiInput`**

We have introduced the `showClearIcon` property. If set to true, when there is text input it shows an additional icon that allows users to clear their input. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Input). 

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.List`** 



</td>
<td valign="top">

**`sap.m.List`**

You can now adapt the default wrapping behavior for titles and descriptions in lists and define the number of characters after which wrapping is done by using the new `wrapCharLimit` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StandardListItem%23methods/getWrapCharLimit) and the [Sample](https://sdk.openui5.org/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemWrapping).

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.MenuButton`** 



</td>
<td valign="top">

**`sap.m.MenuButton`**

We have introduced a new `beforeMenuOpen` event, fired when the arrow button of the `sap.m.MenuButton` in split mode is pressed, and before the dropdown menu opens. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MenuButton) and the [Sample](https://sdk.openui5.org/entity/sap.m.MenuButton/sample/sap.m.sample.MenuButton).

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



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

The new `firstDayOfWeek` property enables developers to set the first day of week that is displayed in the week-based views of the `PlanningCalendar` - `Week` view, and `OneMonth` view \(on small devices\). Valid values are 0 to 6 starting on Sunday. If there is no valid value set, the default from the user locale is used. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarWithLegend).

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
<tr>
<td valign="top">

1.94 



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

We have updated the Microsoft Adaptive Cards SDK from version 1.2.3 to version 2.9.0, which will give us the possibility to adopt and consume the latest features and functionalities in future releases.

<sub>Changed•Control•Info Only•1.94</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2021-09-09



</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

