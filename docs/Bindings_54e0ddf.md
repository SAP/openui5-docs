<!-- loio54e0ddf695af4a6c978472cecb01c64d -->

| loio |
| -----|
| 54e0ddf695af4a6c978472cecb01c64d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/54e0ddf695af4a6c978472cecb01c64d) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/54e0ddf695af4a6c978472cecb01c64d)</div>

## Bindings

Bindings connect OpenUI5 view elements to model data, allowing changes in the model to be reflected in the view element and vice versa.

The OData V4 model supports the following types of binding:

-   **List bindings**, which represent a collection \(of OData entities, complex or primitive types\) such as `/SalesOrderList` \(see the [sap.ui.model.odata.v4.ODataListBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding) API documentation in the Demo Kit\)

-   **Context bindings**, which represent a single entity such as `/SalesOrderList('0500000000')` or a structural property with complex type \(see the [sap.ui.model.odata.v4.ODataContextBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding) API documentation in the Demo Kit\)

-   **Property bindings**, which represent a single, primitive type property in an entity or complex type such as `/ProductList('HT-1000')/Name` \(see the [sap.ui.model.odata.v4.ODataPropertyBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataPropertyBinding) API documentation in the Demo Kit\)


**Related information**  


[sap.ui.model.odata.v4.ODataListBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding)

[sap.ui.model.odata.v4.ODataContextBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding)

[sap.ui.model.odata.v4.ODataPropertyBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataPropertyBinding)

[Sample: Sales Orders](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.odata.v4.SalesOrders/code/Main.controller.js)

[Binding Events](Binding_Events_1a010d3.md)

[Batch Control](Batch_Control_74142a3.md)

[Filtering](Filtering_5338bd1.md)

[Sorting](Sorting_d2ce3f5.md)

[OData Version 4.0 Part 2: URL Conventions, 4 Resource Path](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html)

[OData Version 4.0 Part 2: URL Conventions, 5 Query Options](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html)

[OData Version 4.0 Part 2: URL Conventions, 5.2 Custom Query Options](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part2-url-conventions/odata-v4.0-errata03-os-part2-url-conventions-complete.html)

[OData Version 4.0 SimpleIdentifier](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part3-csdl/odata-v4.0-errata03-os-part3-csdl-complete.html#_SimpleIdentifier)

