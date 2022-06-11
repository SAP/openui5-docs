<!-- loio4e89fee547a24385826cddcfdf4df238 -->

| loio |
| -----|
| 4e89fee547a24385826cddcfdf4df238 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/4e89fee547a24385826cddcfdf4df238) | [demo kit latest release](https://sdk.openui5.org/topic/4e89fee547a24385826cddcfdf4df238)</div>

## What's New in OpenUI5 1.70

With this release OpenUI5 is upgraded from version 1.69 to 1.70.

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td valign="top">

<code><b>sap.f.GridListItem</b></code>

We have introduced a new control `GridListItem` to be used in the default `items` aggregation of `sap.f.GridList`. It consists of a header toolbar and content.

 ![](images/loiod3ef93c51b5f4f1aa04445fae8755995_HiRes.png) 

Note that even though the `content` aggregation can be used for any control, complex responsive layout controls, such as `Table` and `Form`, should not be used.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridListItem) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridList/sample/sap.f.sample.GridListModes).



</td>
</tr>
</table>

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `sap.ui.model.odata.v4.ODataListBinding.requestContexts` method is available for requesting and accessing a collection in controller code through list bindings.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
</table>

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

<code><b>sap.f.GridContainer</b></code>

We have polished the code, added right-to-left \(RTL\) support, and implemented a polyfill for Microsoft Internet Explorer 11 and Microsoft Edge browsers.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.ColorPalette</b></code>

With the new `displayMode` enum property of `sap.m.ColorPalettePopover`, you can now control which variant of `sap.m.ColorPicker` is visualized when the *More colors...* button is pressed.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ColorPalettePopover) and the [Sample](https://sdk.openui5.org/entity/sap.m.ColorPalette/sample/sap.m.sample.ColorPalettePopover).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.DatePicker</b></code>

We have introduced a more intuitive way for users to confirm date selection. Setting the new `showFooter` property enables a footer with *OK* and *Cancel* buttons for the user to confirm or cancel the date selection. When `showFooter` is set to `true`, the picker no longer closes when a day is selected and there's no need to reopen the picker to select the month or year.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker) and the [Sample](https://sdk.openui5.org/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.SelectDialog</b></code>

-   We have introduced a new `clearButtonPressed` parameter for the `search` event of the control. The parameter is set to `true` when the *Clear* button of the search field is pressed.

-   We have introduced the `resizable` and `draggable` properties for the control. If the `resizable` property is set to `true`, `SelectDialog` has a resize handler in its bottom-right corner. If the `draggable` property is set to `true`, the control can be dragged by its header. Both properties are available in desktop mode only.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialog) and the [Samples](https://sdk.openui5.org/entity/sap.m.SelectDialog).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.SinglePlanningCalendar</b></code>

We have introduced support for indicating working hours in the `sap.m.SinglePlanningCalendar` control. Additionally, app developers can now show or hide the rest of the hours in the day. The `startHour` and `endHour` properties define the starting and ending hours of the working day, and these are indicated visually on the screen. The `fullDay` property contains a boolean flag, which determines whether nonworking hours are aslo displayed.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.TableSelectDialog</b></code>

We have extended the `search` event of the control with a new `clearButtonPressed` parameter. The value of this parameter is set to `true` when the event is fired by pressing the *Clear* button and to `false`, when the *Search* button is pressed.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TableSelectDialog) and the [Samples](https://sdk.openui5.org/entity/sap.m.TableSelectDialog).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.table.AnalyticalTable`**

When you group columns in an analytical table, you can now select *Expand All* in the context menu to expand all nodes. Also, you can now expand individual nodes via the context menu by selecting *Expand Level*. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.AnalyticalTable/methods/expandAll).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.ui.unified.Calendar</b></code>

We have improved the navigation in the multiple months view for `sap.ui.unified.Calendar`. When you navigate to the next/previous months, the displayed calendar view is now with one month increments/decrements, instead of two. Note that this behaviour comes out of the box without setting any properties.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.Calendar) and the [Sample](https://sdk.openui5.org/entity/sap.ui.unified.Calendar/sample/sap.ui.unified.sample.CalendarMultipleMonth).



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_5a18410.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_5deb78f.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_5e35c25.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_7aacb4e.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_f21858f.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_b39a11b.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

