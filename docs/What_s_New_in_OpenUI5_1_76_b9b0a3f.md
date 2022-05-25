<!-- loiob9b0a3f223c14b9d99e0d86e649cafec -->

| loio |
| -----|
| b9b0a3f223c14b9d99e0d86e649cafec |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/b9b0a3f223c14b9d99e0d86e649cafec) | [demo kit latest release](https://sdk.openui5.org/topic/b9b0a3f223c14b9d99e0d86e649cafec)</div>

## What's New in OpenUI5 1.76

With this release OpenUI5 is upgraded from version 1.75 to 1.76.

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**`Team Calendar`**

We have added a new demo application - the Team Calendar. It demonstrates the integration between `sap.m.PlanningCalendar` and `sap.m.SinglePlanningCalendar` controls, sharing the same data source. The Team Calendar can be used as a starting point for building a fully functional complex application. Find it in the [Demo Apps](https://sdk.openui5.orgdemoapps).



</td>
</tr>
</table>

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**`Card Explorer`**

-   The Component card sample in the Explore section has been enhanced. To facilitate developers, we have added the option to download the bundle of all the files in the sample.
-   All the properties in the Learn section are now listed with their Since attribute. This will inform developers since which version each feature is available.

For more information, see [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).



</td>
</tr>
<tr>
<td valign="top">

**One Page Acceptance Tests \(OPA5\)**

We've introduced `Drag` and `Drop` actions to OPA5 to help with the most common cases. For more information, see [Simulating User Interactions on Controls](Simulating_User_Interactions_on_Controls_8615a0b.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.test.actions) and the [Sample](https://sdk.openui5.org/entity/sap.ui.test.Opa5/sample/sap.ui.core.sample.OpaAction).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   A new `transitionMessagesOnly` binding parameter is provided for the `sap.ui.model.odata.v2.ODataListBinding` class.
-   The `updateAggregatedMessages` parameter of `sap.ui.model.odata.v2.ODataModel#read` is now public.
-   Existing server messages can be retrieved from the model using the `sap.ui.model.Context#getMessages` method.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now access the binding parameter of an operation, as described in [OData Operations](OData_Operations_b54f789.md).
-   A property path provided to `sap.ui.model.odata.v4.Context#requestSideEffects` can be given the suffix "`*`" to enforce re-reading of all properties of the related entity.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/requestSideEffects).


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loiob9b0a3f223c14b9d99e0d86e649cafec__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

-   With the new `autoFocus` property, we’ve introduced the possibility to enable/disable the autofocus functionality of the `FlexibleColumnLayout` control.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout) and the [Sample](https://sdk.openui5.org/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithOneColumnStart).

-   We’ve introduced the `columnResize` event, which is fired when the resizing of each column of the control is complete.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout%23events/columnResize).




</td>
</tr>
<tr>
<td valign="top">

**`sap.m.FacetFilter`**

Optimization regarding the initial database service query has been introduced. There are cases when the `items` aggregation for the `FacetFilterList` could take a long time fetching data from the database service. Now we have added а `search` event, that fires when the `FacetFilterList` is opened. This enables developers to register a handler function to prevent the default filtering behavior by calling the `sap.ui.base.Event.prototype.preventDefault` function. As a result, no list items are loaded initially. In this case, the developers have to define the filtering behavior at the application level inside the `search` event handler function. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.FacetFilter) and the [Samples](https://sdk.openui5.org/entity/sap.m.FacetFilter).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

New indication colors are now available \(provided by the `sap.ui.core.IndicationColor` enumeration\) that can be used for highlighting table rows. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.IndicationColor).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.plugins.DataStateIndicator`**

We made some improvements to this plugin class and the messages shown for the data state:

-   A new refresh function of the messages for each data state is available that re-evaluates the filter and then refreshes the message strip based on that information.

-   The `filter` property that is defined by the application can now also take the related control into account, along with the message, using the respective parameters.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.DataStateIndicator).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Table`**

An automatic pop-in mode has been enabled for the responsive table. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table%23methods/getAutoPopinMode) for the related method, the [API Reference](https://sdk.openui5.org/api/sap.m.Column%23controlProperties) for the related properties, and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TableAutoPopin).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have added a `type` property for the configuration parameters inside a card. This property defines the data type of the parameter. Currently the `type` property is used only in UI adaptation at design time. For more information, see the [Manifest Parameters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/manifestParameters) section in the Card Explorer.
-   We have added support for the destinations to be resolved by the host environment. In the manifest, the card developer indicates the name of the destination and the request, which depends on this destination. On the host environment side, the host application developer creates a method that resolves the given destination name to a URL. For more information, see [Destinations](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/destinations) in the Card Explorer.
-   We have introduced optional application-level Host Actions that interact with the host environment. These specific actions are displayed by the card and processed back in the host environment. For example, sharing or removing a card. For more information, see [Host Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/hostActions) in the Card Explorer.
-   A new `JsonDateTime` parser is now used to properly parse dates. Some `DateTime` values may appear in JSON files as `DateTime Wire` format strings like `/Date(700000+0500)/`. The parser automatically splits the date string into parts, taking into account the time zone offset if present, and returns a valid date object. For more information, see [DateTime Wire Format](https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/stand-alone-json-serialization?redirectedfrom=MSDN#datetime-wire-format).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**

-   New indication colors are now available \(provided by the `sap.ui.core.IndicationColor` enumeration\) that can be used for highlighting table rows. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.IndicationColor).

-   The resizing of columns has been changed to improve the usability on tablet devices.




</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**

`sap.ui.table.plugins.MultiSelectionPlugin` for these tables has been enhanced and now provides the following functions:

-   The selection of indices outside of data boundaries is now no longer possible, because the binding length is taken into account.

-   A validation takes place to prevent errors from occurring due to the selection of unsuitable parameters.

-   Methods that change the selection now return a `Promise` that is resolved after a selection has been made.

-   A `customPayload` parameter has been added to the `selectionChange` event to allow event listeners to make use of custom event data.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.unified.calendar.Month`**

We have enabled custom colors to be used with the `specialDates` aggregation in `sap.m.PlanningCalendar`, `sap.m.SinglePlanningCalendar`, and `sap.ui.unified.Calendar` controls. This enhancement harmonizes with the `legend` aggregation where custom colors were already available. It is implemented with the new `color` property of type `sap.ui.core.CSSColor` in the `sap.ui.unified.DateTypeRange` control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.DateTypeRange) and the [Samples](https://sdk.openui5.org/entity/sap.m.PlanningCalendar).



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

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

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

