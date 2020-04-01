<!-- loiob9b0a3f223c14b9d99e0d86e649cafec -->

| loio |
| -----|
| b9b0a3f223c14b9d99e0d86e649cafec |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b9b0a3f223c14b9d99e0d86e649cafec) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b9b0a3f223c14b9d99e0d86e649cafec)</div>

## What's New in OpenUI5 1.76

With this release OpenUI5 is upgraded from version 1.75 to 1.76.

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_yxw_pxt_zcb"/>

### New Features

|**`Team Calendar`**We have enabled custom colors to be used with the `specialDates` aggregation in `sap.m.PlanningCalendar`, `sap.m.SinglePlanningCalendar`, and `sap.ui.unified.Calendar` controls. This enhancement harmonizes with the `legend` aggregation where custom colors were already available. It is implemented with the new `color` property of type `sap.ui.core.CSSColor` in the `sap.ui.unified.DateTypeRange` control. Find it in the [Demo Apps](https://openui5.hana.ondemand.com/#demoapps).|

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_qwl_pb5_zcb"/>

### Improved Features

|**`Card Explorer`**-   The Component card sample in the Explore section has been enhanced. To facilitate developers, we have added the option to download the bundle of all the files in the sample.
-   All the properties in the Learn section are now listed with their Since attribute. This will inform developers since which version each feature is available.

For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **One Page Acceptance Tests \(OPA5\)** We've introduced `Drag` and `Drop` actions to OPA5 to help with the most common cases. For more information, see [Simulating User Interactions on Controls](Simulating_User_Interactions_on_Controls_8615a0b.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.test.actions) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.test.Opa5/sample/sap.ui.core.sample.OpaAction).</th>
 -   The `updateAggregatedMessages` parameter of `sap.ui.model.odata.v2.ODataModel#read` is now public.
 -   Existing server messages can be retrieved from the model using the `sap.ui.model.Context#getMessages` method.
			</td>
		</tr>
		<tr>
			<td> **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features:

 -   You can now access the binding parameter of an operation, as described in [OData Operations](OData_Operations_b54f789.md). -   A property path provided to `sap.ui.model.odata.v4.Context#requestSideEffects` can be given the suffix "`*`" to enforce re-reading of all properties of the related entity.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context%23methods/requestSideEffects).


 > Note:
 > Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.</td>
		</tr>

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_rqn_wd5_zcb"/>

### Improved Controls

		<tr>
			<td> **`sap.f.FlexibleColumnLayout`**

 -   With the new `autoFocus` property, we’ve introduced the possibility to enable/disable the autofocus functionality of the `FlexibleColumnLayout` control.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.FlexibleColumnLayout) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithOneColumnStart).
 -   We’ve introduced the `columnResize` event, which is fired when the resizing of each column of the control is complete.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.FlexibleColumnLayout%23events/columnResize).
			</td>
		</tr>
		<tr>
			<td>**`sap.m.FacetFilter`**Optimization regarding the initial database service query has been introduced. There are cases when the `items` aggregation for the `FacetFilterList` could take a long time fetching data from the database service. Now we have added а `search` event, that fires when the `FacetFilterList` is opened. This enables developers to register a handler function to prevent the default filtering behavior by calling the `sap.ui.base.Event.prototype.preventDefault` function. As a result, no list items are loaded initially. In this case, the developers have to define the filtering behavior at the application level inside the `search` event handler function. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.FacetFilter) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.FacetFilter).</td>
			<td> **`sap.m.List, sap.m.Table, sap.m.Tree`** New indication colors are now available \(provided by the `sap.ui.core.IndicationColor` enumeration\) that can be used for highlighting table rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.IndicationColor). </td>
			<td>**`sap.m.plugins.DataStateIndicator`**We made some improvements to this plugin class and the messages shown for the data state:-   A new refresh function of the messages for each data state is available that re-evaluates the filter and then refreshes the message strip based on that information.
 -   The `filter` property that is defined by the application can now also take the related control into account, along with the message, using the respective parameters.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.plugins.DataStateIndicator).</td>
		</tr>
		<tr>
			<td> **`sap.m.Table`** An automatic pop-in mode has been enabled for the responsive table. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table%23methods/getAutoPopinMode) for the related method, the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Column%23controlProperties) for the related properties, and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableAutoPopin). </td>
			<td>**`sap.ui.integration.widgets.Card`**-   We have added a `type` property for the configuration parameters inside a card. This property defines the data type of the parameter. Currently the `type` property is used only in UI adaptation at design time. For more information, see the [Manifest Parameters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/manifestParameters) section in the Card Explorer. -   We have added support for the destinations to be resolved by the host environment. In the manifest, the card developer indicates the name of the destination and the request, which depends on this destination. On the host environment side, the host application developer creates a method that resolves the given destination name to a URL. For more information, see [Destinations](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/destinations) in the Card Explorer.
 -   We have introduced optional application-level Host Actions that interact with the host environment. These specific actions are displayed by the card and processed back in the host environment. For example, sharing or removing a card. For more information, see [Host Actions](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/hostActions) in the Card Explorer.
 -   A new `JsonDateTime` parser is now used to properly parse dates. Some `DateTime` values may appear in JSON files as `DateTime Wire` format strings like `/Date(700000+0500)/`. The parser automatically splits the date string into parts, taking into account the time zone offset if present, and returns a valid date object. For more information, see [DateTime Wire Format](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/stand-alone-json-serialization?redirectedfrom=MSDN#datetime-wire-format).
			</td>
		</tr>
		<tr>
			<td> **`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**

 -   New indication colors are now available \(provided by the `sap.ui.core.IndicationColor` enumeration\) that can be used for highlighting table rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.IndicationColor).
 -   The resizing of columns has been changed to improve the usability on tablet devices.
			</td>
		</tr>
		<tr>
			<td>**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**`sap.ui.table.plugins.MultiSelectionPlugin` for these tables has been enhanced and now provides the following functions:-   The selection of indices outside of data boundaries is now no longer possible, because the binding length is taken into account.
 -   A validation takes place to prevent errors from occurring due to the selection of unsuitable parameters.

 -   Methods that change the selection now return a `Promise` that is resolved after a selection has been made.

 -   A `customPayload` parameter has been added to the `selectionChange` event to allow event listeners to make use of custom event data.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).</td>
		</tr>
		<tr>
			<td>**`sap.ui.unified.calendar.Month`**We have enabled custom colors to be used with the `specialDates` aggregation in `sap.m.PlanningCalendar`, `sap.m.SinglePlanningCalendar`, and `sap.ui.unified.Calendar` controls. This enhancement harmonizes with the `legend` aggregation where custom colors were already available. It is implemented with the new `color` property of type `sap.ui.core.CSSColor` in the `sap.ui.unified.DateTypeRange` control. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.DateTypeRange) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar).</td>
	</tbody>
</table>

