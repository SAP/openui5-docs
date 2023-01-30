<!-- loio3264bd2bb9af4998935c7933d0344d1a -->

| loio |
| -----|
| 3264bd2bb9af4998935c7933d0344d1a |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/3264bd2bb9af4998935c7933d0344d1a) | [demo kit latest release](https://sdk.openui5.org/topic/3264bd2bb9af4998935c7933d0344d1a)</div>

## What's New in OpenUI5 1.109

With this release OpenUI5 is upgraded from version 1.108 to 1.109.

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

 1.109 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.fl.variants.VariantManagement`** 



</td>
<td valign="top">

**`sap.ui.fl.variants.VariantManagement`**

-   We have improved the usability of the UI for views: There is no longer a CSS-based, fixed maximum width for the control. The control is now fully responsive, for example, to show longer view titles. You can still limit the maximum width of the control by using the `maxWidth` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.fl.variants.VariantManagement%23methods/setMaxWidth).

-   You can now configure the style of view titles by using the `titleStyle` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.fl.variants.VariantManagement%23methods/setTitleStyle).


<sub>Changed•Control•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Table`** 



</td>
<td valign="top">

**`sap.m.Table`**

If a user selects all rows in a table using the *Select All* checkbox, **only** the rows that are already loaded will be selected in tables where growing is enabled. We have added a message that informs the user about this. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/getMultiSelectMode).

<sub>Changed•Control•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Deprecations** 



</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



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

-   We now provide the experimental `sap.ui.model.odata.v4.Context#resetChanges` method. As of now, it is still under development and must not be used for productive applications.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/resetChanges).
-   We now provide the new `sap.ui.model.odata.v4.ODataListBinding#getAggregation` method.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/getAggregation).
-   You can now request side effects to update single rows or the entire list with the experimental hierarchy feature introduced with OpenUI5 1.105, provided they do not affect the hierarchy itself \(node IDs, parent/child relations, or sibling order\).For more information, see the API Reference for [`#requestSideEffects`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/requestSideEffects) and the `hierarchyQualifier` parameter in [`#setAggregation`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation).
-   You can now prevent the posting of a new entity to the back end that would follow the `createActivate` event of an `sap.ui.model.odata.v4.ODataListBinding` by using the `sap.ui.base.Event#preventDefault` method.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.base.Event/methods/preventDefault).
-   We have improved our documentation of how to delete a context used as the binding context of an object page or Details section. For more information, see [Deleting an Entity](Deleting_an_Entity_2613ebc.md).

<sub>Changed•Feature•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



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

The new version of the OpenUI5 OData V2 model introduces the following features:

-   When you use an `sap.ui.model.type.Unit`, `sap.ui.model.odata.type.Unit`, or the unit instance of `sap.ui.core.format.NumberFormat`, entered unit-of-measure codes are now parsed case-insensitively where possible.
-   The `B` pattern symbol, representing the flexible day period, is now supported by `sap.ui.core.format.DateFormat`.

<sub>Changed•Feature•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.IllustratedMessage`** 



</td>
<td valign="top">

**`sap.m.IllustratedMessage`**

We have updated the illustrations in the default set. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessageType).

<sub>Changed•Control•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



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

-   You can now configure the visibility of the main and side indicators of the numeric header using the new `visible` boolean property. you can set this property in the manifest or it can be resolved dynamically using a condition expression. For more information, see the [Numeric Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/numeric) section in the Card Explorer.

-   We have aligned the behavior of icons when the icon source is resolved to an empty object or an empty string. Now, in such cases, all Integration cards show a default icon.

-   We have changed the default value of the \(experimental\) `dataMode` property to `Auto`. In this mode, the card makes data requests only when it’s in the viewport. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card). 

-   You can use the new \(experimental\) `design` property to set the card background and border to `Transparent`. The default value of the new property is `Solid`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card).

-   We have introduced a new `minItems` property, which represents the minimum number of expected items. This property is used during the calculation of the minimum height of the card to minimize resizing while data is loading. The new property is available for List, Table, and Timeline cards. For more information, see the [Card Features - Sizing](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/sizing) section in the Card Explorer.


<sub>Changed•Control•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
<tr>
<td valign="top">

 1.109 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.LightBox`** 



</td>
<td valign="top">

**`sap.m.LightBox`**

We are now using the `IllustratedMessage` control to show errors when an image could not be loaded, or when it takes too much time to load it.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.LightBox/sample/sap.m.sample.LightBox).

<sub>Changed•Control•Info Only•1.109</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2022-12-01



</td>
</tr>
</table>

