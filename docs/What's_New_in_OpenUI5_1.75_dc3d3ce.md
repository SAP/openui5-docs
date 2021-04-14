<!-- loiodc3d3ce46105441db5543049fb1c11e7 -->

| loio |
| -----|
| dc3d3ce46105441db5543049fb1c11e7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/dc3d3ce46105441db5543049fb1c11e7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/dc3d3ce46105441db5543049fb1c11e7)</div>

## What's New in OpenUI5 1.75

With this release OpenUI5 is upgraded from version 1.74 to 1.75.

***

<a name="loiodc3d3ce46105441db5543049fb1c11e7__section_yxw_pxt_zcb"/>

### New Features

|**Accessibility Enhancement** 

OpenUI5 is following the SAP ‘s updated design and development guidelines, as well as the testing procedures and accessibility reporting, that are based on WCAG 2.1 level A and AA.

|
|**Browser and Platform Support**

OpenUI5 now supports the latest Chromium-based version of Microsoft Edge. The next long-term maintenance OpenUI5 release that comes after 1.71 will be the last release to support the legacy EdgeHTML-based version of Microsoft Edge. For more information, see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md).

|

***

<a name="loiodc3d3ce46105441db5543049fb1c11e7__section_qwl_pb5_zcb"/>

### Improved Features

|**Card Explorer**

We have introduced a schema validation feature in our samples in the Card Explorer. With this option, developers can see a more detailed report for mistakes inside the card manifest. Things like wrong names of properties, bad property types or bad structures are easily spotted.For more information, explore the samples in the [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/exploreOverview/types).

|
|**Currency Codes**

When displaying ISO currency codes using `sap.ui.core.format.NumberFormat`, `sap.ui.model.type.Currency` or `sap.ui.model.odata.type.Currency`, the currency code is now displayed by default after the amount, ignoring locale, in order to be consistent with SAP design guidelines. The core configuration parameter `trailingCurrencyCode` can be used to switch the behavior globally.

If currency symbols are enabled \(formatting option `currencyCode: false`\), they continue to follow locale-specific placement.

|
|**OpenUI5 OData V2 Messages**

With the new version of the OpenUI5 OData V2 model, the target of server messages is shortened by removing associated pairs of navigation properties. For example, a `/SalesOrderSet('1')/ToLineItems(SalesOrderID='1',ItemPosition='10')/ToHeader/GrossAmount` message target gets reduced to `/SalesOrderSet('1')/GrossAmount` if the `ToLineItems` and `ToHeader` navigation properties have the same relationship in the service metadata. If the second navigation property references a collection, the message target path is reduced only if the referenced entity is the same as without the navigation.

|
|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   When displaying aggregated data with a list binding using either the `$$aggregation` binding parameter or `sap.ui.model.odata.v4.ODataListBinding#setAggregation`, you can filter by properties that are part of the original entity set but not of the result set. Note that these filters need to be provided as `sap.ui.model.Filter` objects.
-   `sap.ui.model.odata.v4.Context#requestSideEffects` now supports updating in parent bindings by specifying navigation properties to the parent entities in the path expressions. The respective navigation properties from the parent binding to the binding of the context and back to the parent need to be marked as partners in the metadata.
-   When using `autoExpandSelect`, paths with navigation properties can now be added to `$select`. The binding will evaluate this and automatically derive `$select` and `$expand`.
-   For `sap.ui.model.odata.v4.ODataPropertyBinding`, a `$$noPatch` binding parameter is provided, so that values can be changed in the model without updating them in the back end.
-   The `resume` method of the `v4.ODataContextBinding` and `v4.ODataListBinding` classes now works synchronously.

> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

|
|**Title Support in Nested Components**

The `title` property can now also be defined on routing targets of type `Component`. When set with a binding syntax, it is resolved in the context of the root view of the component loaded by this target.

The router of a nested component may also have a `title` property defined on its own target\(s\) and eventually fire its own `titleChanged` event once such a target is displayed. A new configuration `propagateTitle` allows the `titleChanged` event to propagate from an individual `Component` target to the router of its parent component. In the routing configuration, this can also be enabled for all `Component` targets, so that it is not necessary to define the `propagateTitle` property on each `Component` target.

For more information, see [Using the title Property in Targets](Using_the_title_Property_in_Targets_1238d70.md) and [Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md). In addition, the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.routing.Router/sample/sap.ui.core.sample.RoutingNestedComponent) application introduced in the previous release to feature routing of nested components has been enhanced. It now shows how the new title definition and title propagation could be used in an application built with nested \(or reuse\) components. 

|

***

<a name="loiodc3d3ce46105441db5543049fb1c11e7__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.m.InitialPagePattern`**

We have introduced the initial page floorplan as a Demo Kit sample. The floorplan allows users to navigate to a single object to view or edit it. The interaction point on the screen is a single input field and it relies on assisted input to direct the user to the object in as few steps as possible \(using features such as value help and live search\). For more information, see the [CardSAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/initial-page-floorplan/)and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.InitialPagePattern/sample/sap.m.sample.InitialPagePattern).

|
|**`sap.m.Link`**

The `text` property can now be changed using UI adaptation at runtime. This enables key users to provide meaningful link text according to the application context.

For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Link).

|
|**`sap.m.MessageBox`**

We have introduced a new `emphasizedAction` property. This allows developers to specify which button in the dialog will receive the type `Emphasized`. If `emphasizedAction` is empty with no actions provided, the default value applies. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MessageBox) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.MessageBox).

|
|**`sap.m.ObjectStatus`**

We have enhanced the `sap.ui.core.IndicationColor` palette. Three new colors were added to the palette as numbers 6, 7, and 8. These colors enable developers to represent statuses that don't require a meaning in the sense of good-bad, but should be visually distinguishable. For example, statuses such as Updated, New, or Active. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectStatus) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectStatus/sample/sap.m.sample.ObjectStatus).

|
|**`sap.ui.integration.widgets.Card`**

-   You can now load the Adaptive Card manifest/descriptor from а URL.

-   The Adaptive Card supports templating, which enables the separation of data from the layout.


For more information, see the [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) in the Card Explorer.

|
|**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**

A more comprehensive message text is now shown if no data is available because all table columns are hidden.

|

***

<a name="loiodc3d3ce46105441db5543049fb1c11e7__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|***Edit on GitHub* link from each OpenUI5 *Documentation* page**

We have added a direct link from each OpenUI5 documentation page to its markdown version in the *openui5-docs* GitHub repo. Now, when you want to send us feedback on a specific topic or even suggest a change with a pull request, we hope to save you time and efforts in finding the respective file.

![](loio8a5845e5be56483da308611359ba45ea_HiRes.gif)

|
|**Search Highlighting in the *Documentation* and *Samples* sections**

The search highlighting functionality is now also available in the *Documentation* tree filter and the *Samples* list.

 ![](loioe79499d4357e4a7eb7de9c5e1a835d55_HiRes.png) 

 ![](loio308ff81070684b318c4da4d1290a7e95_HiRes.png) 

|

