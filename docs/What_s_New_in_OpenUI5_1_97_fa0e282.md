<!-- loiofa0e2828d1444c268a8b6722e5df0b98 -->

| loio |
| -----|
| fa0e2828d1444c268a8b6722e5df0b98 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/fa0e2828d1444c268a8b6722e5df0b98) | [demo kit latest release](https://sdk.openui5.org/topic/fa0e2828d1444c268a8b6722e5df0b98)</div>

## What's New in OpenUI5 1.97

With this release OpenUI5 is upgraded from version 1.96 to 1.97.

***

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

 1.97 



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

-   If the parent context of an operation binding is a row context of a list binding, and the result of the operation fulfills the criteria for a return value context, you can now replace that row context with the result of the operation. For more information, see the `sap.ui.model.odata.v4.ODataContextBinding#execute` method, and in particular the `bReplaceWithRVC` parameter.

-   We have introduced the `sap.ui.model.odata.v4.Context#replaceWith` method. You can use it to replace a row context of a list binding by a kept-alive context that is not part of the collection. Such a context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

-   You can now apply the `sort`, `filter`, `changeParameters`, and `suspend` methods to an `sap.ui.model.odata.v4.ODataListBinding` despite changes in kept-alive contexts or bindings relative to kept-alive contexts of the list. Accordingly, `sap.ui.model.odata.v4.ODataListBinding#hasPendingChanges` has been extended with a `bIgnoreKeptAlive` parameter.

-   The `sap.ui.model.odata.v4.ODataListBinding#filter` and `sap.ui.model.odata.v4.ODataListBinding#sort` methods do not reset the binding if the filters or sorters are unchanged.


<sub>Changed•Feature•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



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

With the new `decorative` property, you can now set the `Avatar` control to be used only for decorative purposes and to be ignored by accessibility tools.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessagePage).

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.ComboBox`, `sap.m.MultiComboBox`** 



</td>
<td valign="top">

**`sap.m.ComboBox`, `sap.m.MultiComboBox`**

We have introduced the `showClearIcon` property. If set to `true`, when there is text input it shows an additional icon that allows users to clear their input. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxClearIcon) for `sap.m.ComboBox` and the [Sample](https://sdk.openui5.org/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBoxClearIcon) for `sap.m.MultiComboBox`.

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.DatePicker, sap.m.DateRangeSelection, sap.m.DateTimePicker, and sap.m.TimePicker`** 



</td>
<td valign="top">

**`sap.m.DatePicker, sap.m.DateRangeSelection, sap.m.DateTimePicker, and sap.m.TimePicker`**

These controls can now be opened by another control. To enable this feature, we have introduced a new `hideInput` property that hides the input field of the corresponding control. In this case, the only way to open the picker popover is by calling the `openBy` method. This new feature minimizes the visual footprint of the controls, which is useful when more controls are placed together. For more information, see the [DatePicker](https://sdk.openui5.org/entity/sap.m.DatePicker/sample/sap.m.sample.DatePickerHidden), [DateRangeSelection](https://sdk.openui5.org/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelectionHidden), [DateTimePicker](https://sdk.openui5.org/entity/sap.m.DateTimePicker/sample/sap.m.sample.DateTimePickerHidden), and [TimePicker](https://sdk.openui5.org/entity/sap.m.TimePicker/sample/sap.m.sample.TimePickerHidden) samples.

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.DateTimePicker`** 



</td>
<td valign="top">

**`sap.m.DateTimePicker`**

The control now implements the new dial-based design for the time picker.For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.DateTimePicker).

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.DynamicDateRange` \(Experimental\)** 



</td>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

We have added a new standard option named `DATETOYEAR` - a period from today to the end of the year. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DynamicDateRange).

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.MessagePage`** 



</td>
<td valign="top">

**`sap.m.MessagePage`**

With the new `titleLevel` property, we have enabled app developers to set a custom aria-level of the `MessagePage` title.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessagePage).

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



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

We have introduced a new `multipleAppointmentsSelection` property that allows mobile users to select multiple appointments. If set to `true`, every mouse click or tap on an appointment will lead to selection. The selection of multiple appointments using the [CTRL\] key is possible regardless of the value of this property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarOneLine).

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



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

Timeline cards now support actions defined on an item level. These actions can be handled by the application in the same way as actions of the List card items.For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/timeline) in the Card Explorer.

<sub>Changed•Control•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
<tr>
<td valign="top">

 1.97 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Demo Kit News Section with Notifications** 



</td>
<td valign="top">

**Demo Kit News Section with Notifications**

We implemented a *News* section with notifications where you can get highlights on important news about OpenUI5. When we upload new information, you’ll see a notification bell with a counter in the main toolbar.

![](images/loiofe57420a441440c3bad48ca4a02eaf0f_HiRes.png)

<sub>New•Feature•Info Only•1.97</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2021-12-02



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

