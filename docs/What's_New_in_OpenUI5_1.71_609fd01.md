<!-- loio609fd015eaf64bd2a4a5c0331590eb4c -->

| loio |
| -----|
| 609fd015eaf64bd2a4a5c0331590eb4c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/609fd015eaf64bd2a4a5c0331590eb4c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/609fd015eaf64bd2a4a5c0331590eb4c)</div>

## What's New in OpenUI5 1.71

With this release OpenUI5 is upgraded from version 1.70 to 1.71.

***

<a name="loio609fd015eaf64bd2a4a5c0331590eb4c__section_qwl_pb5_zcb"/>

### Improved Features

| **Card Explorer** -   An entire new *Integrate* section has been added to the Card Explorer with more information about card consumption in the host environment - in apps, dashboards, or on any HTML page. This section gives you more information on how to use integration cards in apps and about the integration card API.

-   The Card Explorer now preserves the page last visited and thus offers an improved usability and better navigation.

 For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html). |
|**Pre-Announcement: Deprecation of the SAPUI5 Tools for Eclipse**Version 1.71 is the last SAPUI5 version for which we will update the [SAPUI5 Tools for Eclipse](https://tools.hana.ondemand.com/#sapui5).

> CAUTION:  
> After the release of SAPUI5 1.71, the SAPUI5 Tools for Eclipse will no longer be maintained.

We recommend that you use SAP Web IDE as the development environment for SAPUI5. For more information, see [App Development Using SAP Web IDE](App_Development_Using_SAP_Web_IDE_13ced94.md).

|
| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   Custom HTTP headers can be set statically in the manifest or dynamically using `sap.ui.model.odata.v4.ODataModel.changeHttpHeaders`.

-   Annotations for individual overloads of bound actions in the OData 4.01 format are understood as well.

-   `sap.ui.model.odata.v4.Context.requestSideEffects` can now also be called on a context belonging to a context binding that does not request data on its own. The call of `requestSideEffects` is propagated upwards in the binding hierarchy until a context binding or list binding that sends its own data requests is found. During the propagation, list bindings that do not send own data requests must not be passed.

-   Metadata parsing now uses a last-one-wins strategy for duplicated names consistently, also if operations are part of the duplicates.

-   With the model setting `autoExpandSelect:true`, property bindings that become active after their parent context or list binding has sent the first data request will be able to store their data so it can be reused by a later property binding with the same relative path and the same binding context.


 > Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and SAP Fiori elements applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).|
| **Support Assistant** The file extension assertion `getReportAsFileInFormat` for OPA tests; which enables Support Assistant checks`RuleEngineOpaExtension`, has changed. Now, the value of the `fileName` parameter should have the extension `.support-assistant.json`, or it will automatically be changed to `.support-assistant.json`. This new feature will improve file recognition in automated test scenarios. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.support.RuleEngineOpaAssertions/methods/sap.ui.core.support.RuleEngineOpaAssertions.getReportAsFileInFormat). |

***

<a name="loio609fd015eaf64bd2a4a5c0331590eb4c__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **`sap.f.dnd.GridDropInfo`** We have introduced a new `dropIndicatorSize` property. It allows the app developer to specify the size of the drop indicator for items which are not part of the grid, for example, if a flat list item is dragged over an `sap.f.GridContainer`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.dnd.GridDropInfo) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDropFromList). </th>
		<tr>
			<td> **`sap.f.FlexibleColumnLayout`** We introduced a visual improvement of the column separator to enhance its visibility. It is applied to the SAP Quartz Light theme and both SAP Belize themes \(along with the high-contrast themes\), and there are no differences between the cozy mode and the compact mode.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithTwoColumnStart). </td>
			<td> **`sap.f.GridContainer`** This control is no longer experimental, but some properties, methods, and aggregations are still in experimental state.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer). </td>
			<td> **`sap.m.Dialog, sap.m.IconTabBar`, and `sap.m.Input`** Visual improvements based on the latest SAP Fiori Design Guidelines were implemented for the SAP Quartz Light theme.

 -   `sap.m.Dialog` - button stretching on mobile phones has been removed.
 -   `sap.m.Input` - `Success` semantic state border is now 1 px for both the SAP Quartz Light and SAP Belize themes.
 -   `sap.m.IconTabBar` - top, right, and left shadows are hidden. The bottom shadow is visible over the content, and the bottom border has been removed.
			</td>
		</tr>
		<tr>
			<td> **`sap.m.Label`** Visual changes have been introduced. If the `required` property is set to `true`, the asterisk is now smaller and darker. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Label/sample/sap.m.sample.Label). </td>
			<td> **`sap.m.Link`** A new key user adaptation/SAPUI5 flexibility feature now enables the `target` property to be changed in the UI Adaptation mode if the `href` property is set. For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Link). </td>
			<td> **`sap.m.PlanningCalendar`** We have changed the look of the `sap.m.PlanningCalendar`. The header part is now aligned with the one of `sap.m.SinglePlanningCalendar` to have a similar experience when interacting with the two controls. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarModifyAppointments). </td>
			<td> **`sap.m.SelectDialog`** We have updated the behavior of the `sap.m.SelectDialog` when the single selection mode has the `rememberSelections` property set to `true`. Now the user can close the `SelectDialog` by pressing the already selected item from a single selection dialog. This means that the users no longer need to press *Cancel*, if they have opened the `SelectDialog` for a second time to check what was previously selected. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SelectDialog) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SelectDialog). </td>
			<td> **`sap.m.SinglePlanningCalendar`** A new `viewChange` event has been introduced, which is fired when the user changes the view of the control. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar). </td>
			<td> **`sap.m.TableSelectDialog`** The new `resizable` and `draggable` properties have been introduced which affect the desktop mode. They allow the `TableSelectDialog` to be dragged and resized. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TableSelectDialog) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.TableSelectDialog/sample/sap.m.sample.TableSelectDialog). </td>
			<td> **`sap.m.ViewSettingsDialog`** We have improved the user experience of the search. When there are no items matching the search criteria, the *Select All* checkbox is disabled. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ViewSettingsDialog). </td>
			<td> **`sap.ui.integration.widgets.Card`**

 -   Static resource handling improvements have been introduced. Relative URLs for static resources \(i18n files, icons, and images\) inside the manifest can now be resolved based on the provided path in the `baseURL` property. This property helps to resolve the card bundle resource locations, in cases when the card manifest is provided as an object.
 -   We have introduced a new `withCredentials` boolean property for the `sap.ui.integration.widgets.Card`’s manifest. It is part of the `request` property. It indicates whether cross-site requests should be made using credentials or not.


 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.integration.widgets.Card). </td>
		</tr>
		<tr>
			<td>**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**The new `enableNotification` property of `MultiSelectionPlugin` can be used to display a message when the limit of rows that has been selected at the same time is reached.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).</td>
	</tbody>
</table>

