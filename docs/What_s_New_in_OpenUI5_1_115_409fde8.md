<!-- loio409fde8b73364f5bb49905a669a57503 -->

| loio |
| -----|
| 409fde8b73364f5bb49905a669a57503 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/409fde8b73364f5bb49905a669a57503) | [demo kit latest release](https://sdk.openui5.org/topic/409fde8b73364f5bb49905a669a57503)</div>

## What's New in OpenUI5 1.115

With this release OpenUI5 is upgraded from version 1.114 to 1.115.

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

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **`sap.m.p13n.Engine`** 



</td>
<td valign="top">

**`sap.m.p13n.Engine`**

We have added more samples for the `Engine` and deprecated the following entities: `TablePersoController` and `TablePersoDialog`. For more information, see [Personalization](Personalization_75c08fd.md), the  [API Reference](https://sdk.openui5.org/api/sap.m.p13n.Engine), and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineGridTable) for `sap.ui.table.Table`, the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.Engine) for `sap.m.Table`, and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineGridList) for `sap.f.GridList`.

<sub>Changed•Feature•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 ** `sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`** 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

We have deprecated the `editable` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Table).

<sub>Deprecated•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Introduction of `sap.ui.mdc` library \(experimental\)** 



</td>
<td valign="top">

**Introduction of `sap.ui.mdc` library \(experimental\)**

We have introduced the `sap.ui.mdc` library experimentally. This library contains smart composite controls that are metadata-driven and allow applications to use them with any OpenUI5 model and any data protocol. For more information, see [sap.ui.mdc \(experimental\)](sap_ui_mdc_experimental_1dd2aa9.md) and the  [API Reference](https://sdk.openui5.org/api/sap.ui.mdc).

<sub>New•Feature•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



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

-   You can now close the current changeset in `Auto` groups by calling `sap.ui.model.odata.v4.ODataModel#submitBatch`. For any additional change requests that are created afterwards and make it into the same `$batch` request, a new changeset is created.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/submitBatch).

-   We now support the "Deep Create" scenario for navigation properties of cardinality "many", that is, collection-valued navigation properties.

    For more information, see [Creating an Entity](Creating_an_Entity_c9723f8.md).


<sub>Changed•Feature•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **OpenUI5 OData Types** 



</td>
<td valign="top">

**OpenUI5 OData Types**

The new version of OpenUI5 provides the `parseEmptyValueToZero` format option for the following numeric OData types:

-   `sap.ui.model.odata.type.Byte`
-   `sap.ui.model.odata.type.Decimal`
-   `sap.ui.model.odata.type.Double`
-   `sap.ui.model.odata.type.Int`
-   `sap.ui.model.odata.type.Int16`
-   `sap.ui.model.odata.type.Int32`
-   `sap.ui.model.odata.type.Int64`
-   `sap.ui.model.odata.type.SByte`
-   `sap.ui.model.odata.type.Single`

Empty input, that is, `null` or `""`, is parsed to 0 if `parseEmptyValueToZero` is set to `true` and if the `nullable` constraint is `false`.

For more information, see, for example, the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.type.Int16) for `sap.ui.model.odata.type.Int16`.

<sub>Changed•Feature•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



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

-   Using the new \(experimental\) `modelSizeLimit` property, you can set the maximum number of entries that are used for all list bindings inside the card. This feature is important for cards that use forms and filters. The default `modelSizeLimit` value is 1000. For more information, see the [Integration Card Configuration](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/modelSizeLimit) in the Card Explorer.

-   We have \(experimentally\) introduced a new input field in the Object Card that enables the users to pick a date.

    For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/form) in the Card Explorer.

-   We have introduced a new `showColon` property for labels in the Object Card. When set to `false` it hides the colons. The default value is `true`, in which case all colons are automatically shown. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/form) in the Card Explorer.


<sub>Changed•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **sap.m.Button** 



</td>
<td valign="top">

**sap.m.Button**

We have added a new `accessibleRole` property that can receive a value from an enumeration called `sap.m.ButtonAccessibleRole` and the application developer can select one of two values – `Default` or `Link`.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ButtonAccessibleRole). 

<sub>Changed•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **sap.m.DynamicDateRange** 



</td>
<td valign="top">

**sap.m.DynamicDateRange**

We removed the experimental tag of the control. This changes the API to make the control more stable and easier to use.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DynamicDateRange). 

<sub>Changed•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **sap.m.Wizard** 



</td>
<td valign="top">

**sap.m.Wizard**

We have provided an API that will allow the application to change the H level based on your needs so that the correct heading level structure is presented on the page. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Wizard). 

<sub>Changed•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
<tr>
<td valign="top">

 1.115 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **sap.f.SidePanel** 



</td>
<td valign="top">

**sap.f.SidePanel**

We have added the ability to place the `sap.f.SidePanel` control on the left side of the screen. Previously it was fixed only to the right side.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.SidePanel). 

<sub>Changed•Control•Info Only•1.115</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-06-15



</td>
</tr>
</table>

