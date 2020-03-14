<!-- loio25e532617b7f4b9bad842757324151ed -->

| loio |
| -----|
| 25e532617b7f4b9bad842757324151ed |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/25e532617b7f4b9bad842757324151ed) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/25e532617b7f4b9bad842757324151ed)</div>

## What's New in OpenUI5 1.72

With this release OpenUI5 is upgraded from version 1.71 to 1.72.

***

<a name="loio25e532617b7f4b9bad842757324151ed__section_yxw_pxt_zcb"/>

### New Features

| **New Theme Available \(Experimental\)** A new theme *SAP Quartz Dark* \(theme ID: `sap_fiori_3_dark`\) has been introduced. The theme is provided as an additional theme in OpenUI5. > Note:
> This theme will have the status 'experimental' until testing is complete.
> 
> 

 |
|**Responsive Paddings Enablement**We have introduced the `sap.ui.core.util.ResponsivePaddingsEnablement` utility for applying responsive paddings over separate parts of the controls, when using the SAP Quartz themes. The breakpoints and layout paddings can now be determined by the container's width, and not by the screen size. We have introduced responsive paddings to the `sap.m.Page`,`sap.m.Popover`, and `sap.m.Wizard` controls.For more information, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md).|

***

<a name="loio25e532617b7f4b9bad842757324151ed__section_bkm_s15_zcb"/>

### New Controls

|**`sap.f.ProductSwitch` \(Experimental\)**The new layout control is a single-level navigation menu that offers access to the entry pages of products. Its items can be configured with an image/icon, title, subtitle, and navigation target.![](loio0a4532ffdad544a783a2670901a43e85_HiRes.png)For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ProductSwitch) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.ProductSwitch).|

***

<a name="loio25e532617b7f4b9bad842757324151ed__section_qwl_pb5_zcb"/>

### Improved Features

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **Navigation in Nested Components** The navigation in nested components has been enhanced with additional information that can now be passed in optional parameters of the `navTo` method of `sap.ui.core.routing.Router`. This additional information enables the routers in nested components to show the targets which are configured to one specific route. For more information, see [`sap.ui.core.routing.Router.navTo`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.routing.Router/methods/navTo) in the API Reference and [Navigate with Nested Components](Navigate_with_Nested_Components_8e9d6e4.md).</th>

 -   The `resetChanges` method on bindings returns a promise which is resolved without a defined result as soon as all changes in the binding itself and all dependent bindings are canceled.


 > Note:
 > Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).</td>
		</tr>
		<tr>
			<td> **Title Alignment Changes for SAP Quartz Themes** A new title alignment has been introduced for the SAP Quartz themes. The title of the affected control is aligned to the start position \(left or right depending on the text directionality\). Affected Controls:
 -   `sap.m.BusyDialog`
 -   `sap.m.Dialog`
 -   `sap.m.MessageBox`
 -   `sap.m.Page`
 -   `sap.m.Popover`
 -   `sap.m.ResponsivePopover`
 -   `sap.m.SelectDialog`
 -   `sap.m.TableSelectDialog`
 -   `sap.m.ViewSettingsDialog`
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio25e532617b7f4b9bad842757324151ed__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **`sap.f.Avatar`** We have added more options in the `sap.f.AvatarColor` enum for the background color of the `sap.f.Avatar`: `Transparent`, `TileIcon`, and `Placeholder`. To set them, use the `backgroundColor` property.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.Avatar/sample/sap.f.sample.Avatar). </th>
		<tr>
			<td>`**sap.m.ActionSheet**`We have extended the `afterClose` event, to provide context information that indicates the trigger of closing the control - whether it closes with a selection, or it is dismissed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ActionSheet). </td>
			<td>**`sap.m.ComboBox`**, **`sap.m.MultiComboBox`**, **`sap.m.Input`**, **`sap.m.MultiInput`**We have improved the controls to display the text set in the `valueStateText` property on multiple lines. This ensures that the value state text is displayed even when it is longer than the width of the control's container. For more information, see the [`sap.m.ComboBox` Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxValueState). </td>
			<td> **`sap.m.DateRangeSelection`** We have introduced an optional footer with *OK* and *Cancel* buttons, to provide an alternative way for users to confirm the date range selection. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DateRangeSelection). </td>
			<td> **`sap.m.List`, `sap.m.Table`, `sap.m.Tree`**

 -   A new parameter for the direction of the `swipe` event is now available for both left-to-right \(LTR\) and right-to-left \(RTL\) scenarios. This parameter can be used in an app for approvals, for example, where a manager wants to accept or reject leave requests using the swipe function on a mobile device or touch screen. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SwipeDirection) for `SwipeDirection`, the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase/events/swipe) for `swipe`, and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.List/sample/sap.m.sample.ListSwipe).
 -   A new `navigated` property is now available: After a user has displayed the details of an item, a navigation indicator at the end of the corresponding row indicates that the user has already viewed the details. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListItemBase), the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem) for lists, and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table) for tables.
			</td>
		</tr>
		<tr>
			<td> **`sap.m.SinglePlanningCalendar`** The `appointmentSelect` event was also provided for the appointments in the Month view, fired when an appointment is selected. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar). </td>
			<td> **`sap.m.Table`** If applications configure a responsive table that contains only one column in such a way that all columns are moved to the pop-in or hidden on smaller screens, this setting is now ignored to ensure that there is at least one column visible in the tabular layout. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table). </td>
			<td> **`sap.m.ViewSettingsDialog`** The *Reset* button is now fully available for all the tabs in this control.

 -   For built-in tabs \(Sort, Group, and Filter\), the initial state of the Sort and Group settings is stored upon first opening. If changed, this state can be restored later using the *Reset* button and Filter tab selection is removed. If no changes have been made, the *Reset* button remains inactive. -   For custom tabs \(or custom and built-in tabs together\), developers can use the `Reset` event. The *Reset* button is in an active state, no matter if changes are made or not.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ViewSettingsDialog).</td>
		</tr>
		<tr>
			<td>`**sap.m.Wizard**`We have added a new `backgroundDesign` property. It can change the background color of the content and accepts values from `sap.m.PageBackgroundDesign`. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Wizard/sample/sap.m.sample.WizardCurrentStep). </td>
			<td> **`sap.ui.integration.widgets.Card`**

 -   The predefined parameter `LOCALE` is now available, and developers can use it in data-request URL queries. -   New `manifestReady` event has been introduced in an experimental state. It is fired after the manifest is loaded.
 -   The `Refresh` method is now available in experimental state when consuming `sap.ui.integration.widgets.Card` as custom HTML element.

 For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).</td>
		</tr>
		<tr>
			<td> **`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

 -   You can now select rows using key combinations \(select one row: * SHIFT SPACE *, select multiple rows: * SHIFT UP * and * SHIFT DOWN *\). For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Selection).
 -   A new `navigated` property is now available for rows with row actions: After a user has displayed the details of an item, a navigation indicator at the end of the corresponding row indicates that the user has already viewed the details. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.RowSettings) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowAction).
			</td>
		</tr>
		<tr>
			<td> **`sap.ui.unified.FileUploader`** The new `fileEmpty` event was introduced, fired when uploading an empty file. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.sap.ui.unified.FileUploader). </td>
			<td> **`sap.uxap.BlockBase`** You can now subscribe to the new `viewInit` event that is fired when the asynchronously created internal view is available.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.BlockBase). </td>
	</tbody>
</table>

