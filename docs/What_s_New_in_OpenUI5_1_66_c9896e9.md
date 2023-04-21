<!-- loioc9896e9fefee401fbdb3fbef8e06f733 -->

| loio |
| -----|
| c9896e9fefee401fbdb3fbef8e06f733 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c9896e9fefee401fbdb3fbef8e06f733) | [demo kit latest release](https://sdk.openui5.org/topic/c9896e9fefee401fbdb3fbef8e06f733)</div>

## What's New in OpenUI5 1.66

With this release OpenUI5 is upgraded from version 1.65 to 1.66.

** **


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

 1.66 



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

-   New events `createSent` and `createCompleted` on `v4.ODataListBinding`: These events are sent when a POST request for creating an entity is sent to the backend, and when it is completed. Note that the created promise of the new context is only resolved when the POST was successful.

-   `bAtEnd` parameter for the `v4.ODataListBinding.create` method: If this parameter is set, the new entity is added at the end of the list. Note that you must determine the length of the list using `$count`.

-   Format option `emptyString` defaults to 0 for `odata.type.Currency` and `odata.type.Unit`.

-   `v4.Context.requestSideEffects` can also be called on a context of a list binding representing a single entity and the header context of a list binding. For the latter, side effects are loaded for the whole binding.

-   Processing the ETag from the response header.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.66</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Support for New Era in the Japanese Calendar** 



</td>
<td valign="top">

**Support for New Era in the Japanese Calendar**

Starting May 1, 2019, OpenUI5 supports a new era in the Japanese calendar, due to the imperial transition.

<sub>Changed•Feature•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.f.GridContainer` \(Experimental\)** 



</td>
<td valign="top">

**`sap.f.GridContainer` \(Experimental\)**

We have introduced three new properties:

-   `containerQuery` allows you to derive the layout breakpoints either based on the container surrounding the `sap.f.GridContainer` or the device screen size.

-   `allowDenseFill` is an experimental property that allows you to try out a denser arrangement of the grid items. Smaller items will take up all the available space, ignoring their order.

-    `inlineBlockLayout` is an experimental property. It allows you to arrange the items in rows with the height equal to the highest item in the row.


For more information, see [sap.f.GridContainer](sap_f_GridContainer_cca5ee5.md) and the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.ComboBox / sap.m.MultiComboBox`** 



</td>
<td valign="top">

**`sap.m.ComboBox / sap.m.MultiComboBox`**

The options list used in these controls is now instantiated lazily. The list is created primarily based on user interaction. As a result of the change, the initialization time of the controls has decreased significantly. For more information, see the samples \([`sap.m.ComboBox`](https://sdk.openui5.org/entity/sap.m.ComboBox), [`sap.m.MultiComboBox`](https://sdk.openui5.org/entity/sap.m.MultiComboBox)\). 

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.DateRangeSelection`** 



</td>
<td valign="top">

**`sap.m.DateRangeSelection`**

You can now change the date range value using keyboard combinations without opening the calendar. When the cursor is on the start date \(before the delimiter\), we change the start date and when it is on the end date \(after the delimiter\), we change the end date.

-   [PgUp\]/[PgDn\] - increments/decrements the date

-    [Shift\] + [PgUp\] / [Shift\] + [PgDn\]  - increments/decrements the month

-    [Ctrl\] + [Shift\] + [PgUp\] / [Ctrl\] + [Shift\] + [PgDn\]  - increments/decrements the year


For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelection).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Input`** 



</td>
<td valign="top">

**`sap.m.Input`**

We have adjusted the value state text for the `sap.m.Input` control. The value state text is now shown in the suggestion popover container when the `sap.m.Input` control has suggestions.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Input) and the [Samples](https://sdk.openui5.org/entity/sap.m.Input).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



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

You can now switch the background and text colors using the new `inverted` property.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectStatus).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



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

To be better aligned with the other input controls, we have implemented a new `editable` property for the `sap.m.Select` control. If `editable` is set to `false`, the interaction with the control is disabled but remains focusable, and its background color and borders are changed to indicate that it's read-only.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Select) and the [Sample](https://sdk.openui5.org/entity/sap.m.Select/sample/sap.m.sample.Select).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



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

-   You can now include custom views to display different numbers of columns in the grid area of the control, for example, you can show only the first 10 days of each month. To create custom views, extend the `sap.m.SinglePlanningCalendarView` basic view class.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithCustomViews).

-   We have implemented a new `specialDates` aggregation, that allows you to define special dates for the control. They are visualized as a color bar in the header below the respective dates. In addition, you can add the assigned special dates to the associated `sap.m.PlanningCalendarLegend`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).

-   The control can now display longer titles and texts of appointments on multiple lines depending on the length of the appointment.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithCustomViews).

-   We added an arrow indicator to improve the visual design of appointments which are not marked as *All-day* but do continue outside of the visible area.


<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
<tr>
<td valign="top">

 1.66 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 User Documentation 



</td>
<td valign="top">

 **OData V2 Messaging Documentation** 



</td>
<td valign="top">

**OData V2 Messaging Documentation**

The OData V2 Messaging documentation has been enhanced and improved. See [Error, Warning, and Info Messages](Error_Warning_and_Info_Messages_62b1481.md).

<sub>Changed•Control•Info Only•1.66</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-05-22



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

