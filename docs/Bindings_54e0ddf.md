<!-- loio54e0ddf695af4a6c978472cecb01c64d -->

| loio |
| -----|
| 54e0ddf695af4a6c978472cecb01c64d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/54e0ddf695af4a6c978472cecb01c64d) | [demo kit latest release](https://sdk.openui5.org/topic/54e0ddf695af4a6c978472cecb01c64d)</div>

## Bindings

Bindings connect OpenUI5 view elements to model data, allowing changes in the model to be reflected in the view element and vice versa.

The OData V4 model supports the following types of binding:

-   **List bindings**, which represent a collection \(of OData entities, complex or primitive types\) such as `/SalesOrderList` \(see the [sap.ui.model.odata.v4.ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding) API documentation in the Demo Kit\)

-   **Context bindings**, which represent a single entity such as `/SalesOrderList('0500000000')` or a structural property with complex type \(see the [sap.ui.model.odata.v4.ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding) API documentation in the Demo Kit\)

-   **Property bindings**, which represent a single, primitive type property in an entity or complex type such as `/ProductList('HT-1000')/Name` \(see the [sap.ui.model.odata.v4.ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding) API documentation in the Demo Kit\)


-   **[Creating Bindings](Creating_Bindings_95cf4b1.md "")**  

-   **[Path Syntax](Path_Syntax_596a570.md "")**  

-   **[Initialization and Read Requests](Initialization_and_Read_Requests_fccfb2e.md "")**  

-   **[Parameters](Parameters_1ab4f62.md "")**  

-   **[Binding Collection Inline Count](Binding_Collection_Inline_Count_77d2310.md "")**  

-   **[Type Determination](Type_Determination_53cdd55.md "")**  

-   **[Binding Modes](Binding_Modes_e37a0c3.md "")**  

-   **[Suspend and Resume](Suspend_and_Resume_b0f5c53.md " A suspended binding does not send data service requests nor does it fire change events. You can resume a suspended list or context
		binding with its resume method.")**  
 A suspended binding does not send data service requests nor does it fire change events. You can resume a suspended list or context binding with its `resume` method.
-   **[Context API](Context_API_22ee78b.md "")**  

-   **[Accessing Data in Controller Code](Accessing_Data_in_Controller_Code_17b30ac.md "In the OData V4 model, bindings are used to access and modify back-end data also if the data is accessed or modified in controller
		code.")**  
In the OData V4 model, bindings are used to access and modify back-end data also if the data is accessed or modified in controller code.
-   **[Automatic determination of $expand and $select](Automatic_determination_of_expand_and_select_10ca58b.md "")**  

-   **[Data Reuse](Data_Reuse_648e360.md "The OData V4 model keeps data with respect to bindings, which allows different views on the same data, but also means that data is not
		automatically shared between bindings. There are mechanisms for sharing data to avoid redundant requests and to keep the same data in
		different controls in sync.")**  
The OData V4 model keeps data with respect to bindings, which allows different views on the same data, but also means that data is not automatically shared between bindings. There are mechanisms for sharing data to avoid redundant requests and to keep the same data in different controls in sync.

**Related Information**  


[sap.ui.model.odata.v4.ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding)

[sap.ui.model.odata.v4.ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding)

[sap.ui.model.odata.v4.ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding)

[Sample: Sales Orders](https://sdk.openui5.org/sample/sap.ui.core.sample.odata.v4.SalesOrders/code/Main.controller.js)

[Binding Events](Binding_Events_1a010d3.md "The OData V4 model supports certain events intended for applications, and others that are to be used for controls, as outlined in this section.")

[Batch Control](Batch_Control_74142a3.md "OData V4 allows you to group multiple operations into a single HTTP request payload, as described in the official OData V4 specification Part 1, Batch Requests (see the link under Related Information for more details).")

[Filtering](Filtering_5338bd1.md "The OData V4 Model supports server side filtering on lists.")

[Sorting](Sorting_d2ce3f5.md "The OData V4 model supports server side sorting on lists.")

[OData Version 4.0 Part 2: URL Conventions, 4 Resource Path](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html)

[OData Version 4.0 Part 2: URL Conventions, 5 Query Options](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part2-url-conventions.html)

[OData Version 4.0 Part 2: URL Conventions, 5.2 Custom Query Options](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part2-url-conventions/odata-v4.0-errata03-os-part2-url-conventions-complete.html)

[OData Version 4.0 SimpleIdentifier](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part3-csdl/odata-v4.0-errata03-os-part3-csdl-complete.html#_SimpleIdentifier)

