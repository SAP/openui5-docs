<!-- loio4e89fee547a24385826cddcfdf4df238 -->

| loio |
| -----|
| 4e89fee547a24385826cddcfdf4df238 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/4e89fee547a24385826cddcfdf4df238) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/4e89fee547a24385826cddcfdf4df238)</div>

## What's New in OpenUI5 1.70

With this release OpenUI5 is upgraded from version 1.69 to 1.70.

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_bkm_s15_zcb"/>

### New Controls

|`**sap.f.GridListItem**`We have introduced a new control `GridListItem` to be used in the default `items` aggregation of `sap.f.GridList`. It consists of a header toolbar and content. ![](loiod3ef93c51b5f4f1aa04445fae8755995_HiRes.png) 

Note that even though the `content` aggregation can be used for any control, complex responsive layout controls, such as `Table` and `Form`, should not be used.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridListItem) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList/sample/sap.f.sample.GridListModes).|

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   The `sap.ui.model.odata.v4.ODataListBinding.requestContexts` method is available for requesting and accessing a collection in controller code through list bindings.


 > Note:
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).
> 
> 

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).|

***

<a name="loio4e89fee547a24385826cddcfdf4df238__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>`**sap.f.GridContainer**`We have polished the code, added right-to-left \(RTL\) support, and implemented a polyfill for Microsoft Internet Explorer 11 and Microsoft Edge browsers.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).</th>
		<tr>
			<td>`**sap.m.DatePicker**`We have introduced a more intuitive way for users to confirm date selection. Setting the new `showFooter` property enables a footer with *OK* and *Cancel* buttons for the user to confirm or cancel the date selection. When `showFooter` is set to `true`, the picker no longer closes when a day is selected and there's no need to reopen the picker to select the month or year.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DatePicker) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).</td>
			<td> `**sap.m.SelectDialog**`

 -   We have introduced a new `clearButtonPressed` parameter for the `search` event of the control. The parameter is set to `true` when the *Clear* button of the search field is pressed.
 -   We have introduced the `resizable` and `draggable` properties for the control. If the `resizable` property is set to `true`, `SelectDialog` has a resize handler in its bottom-right corner. If the `draggable` property is set to `true`, the control can be dragged by its header. Both properties are available in desktop mode only.


 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SelectDialog) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SelectDialog).</td>
		</tr>
		<tr>
			<td>`**sap.m.SinglePlanningCalendar**`We have introduced support for indicating working hours in the `sap.m.SinglePlanningCalendar` control. Additionally, app developers can now show or hide the rest of the hours in the day. The `startHour` and `endHour` properties define the starting and ending hours of the working day, and these are indicated visually on the screen. The `fullDay` property contains a boolean flag, which determines whether nonworking hours are aslo displayed.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).</td>
			<td>`**sap.m.TableSelectDialog**`We have extended the `search` event of the control with a new `clearButtonPressed` parameter. The value of this parameter is set to `true` when the event is fired by pressing the *Clear* button and to `false`, when the *Search* button is pressed.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TableSelectDialog) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.TableSelectDialog).</td>
			<td> **`sap.ui.table.AnalyticalTable`** When you group columns in an analytical table, you can now select *Expand All* in the context menu to expand all nodes. Also, you can now expand individual nodes via the context menu by selecting *Expand Level*. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.AnalyticalTable/methods/expandAll). </td>
			<td>`**sap.ui.unified.Calendar**`We have improved the navigation in the multiple months view for `sap.ui.unified.Calendar`. When you navigate to the next/previous months, the displayed calendar view is now with one month increments/decrements, instead of two. Note that this behaviour comes out of the box without setting any properties.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.Calendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.unified.Calendar/sample/sap.ui.unified.sample.CalendarMultipleMonth).</td>
	</tbody>
</table>

