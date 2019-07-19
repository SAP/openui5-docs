<!-- loio5de13cf4dd1f4a3480f7e2eaaee3f5b8 -->

| loio |
| -----|
| 5de13cf4dd1f4a3480f7e2eaaee3f5b8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5de13cf4dd1f4a3480f7e2eaaee3f5b8) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5de13cf4dd1f4a3480f7e2eaaee3f5b8)</div>

## OData V4 Model

The `sap.ui.model.odata.v4.ODataModel` is the model implementation for consuming an OData V4 service.

> Note:
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and Fiori elements applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).
> 
> 

The OData V4 model supports the following:

-   Read access

-   Updating properties of OData entities \(in entity sets and contained entities\) via two-way-binding

-   Deleting entities

-   Operation \(function and action\) execution

-   Grouping data requests in a batch request

-   Server-side sorting and filtering


> Note:
> The OData V4 model documentation contains several code samples. These refer to the [Sales Orders](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.odata.v4.SalesOrders/preview) sample in the Demo Kit.
> 
> 

**Related information**  


[Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md)

[sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html)

[Sample: Sales Orders](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.odata.v4.SalesOrders/preview)

