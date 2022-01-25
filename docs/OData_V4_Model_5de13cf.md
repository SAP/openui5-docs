<!-- loio5de13cf4dd1f4a3480f7e2eaaee3f5b8 -->

| loio |
| -----|
| 5de13cf4dd1f4a3480f7e2eaaee3f5b8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5de13cf4dd1f4a3480f7e2eaaee3f5b8) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5de13cf4dd1f4a3480f7e2eaaee3f5b8)</div>

## OData V4 Model

The `sap.ui.model.odata.v4.ODataModel` is the model implementation for consuming an OData V4 service.

> ### Note:  
> Smart controls \(`sap.ui.comp` library\) do not support the OpenUI5 OData V4 model. Also controls such as `TreeTable` and `AnalyticalTable` are not supported together with the OpenUI5 OData V4 model.
> 
> The interface for applications has been changed for an easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

The OData V4 model supports the following:

-   Read access

-   Updating properties of OData entities \(in entity sets and contained entities\) via two-way-binding

-   Deleting entities

-   Operation \(function and action\) execution

-   Grouping data requests in a batch request

-   Server-side sorting and filtering


> ### Note:  
> The OData V4 model documentation contains several code samples. These refer to the [Sales Orders](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.odata.v4.SalesOrders/preview) sample in the Demo Kit.

-   **[Model Instantiation and Data Access](Model_Instantiation_and_Data_Access_9613f1f.md "One OData V4 model instance can only cover one OData service. This section describes the
		creation of a model instance in more detail.")**  
One OData V4 model instance can only cover one OData service. This section describes the creation of a model instance in more detail.
-   **[Bindings](Bindings_54e0ddf.md "Bindings connect OpenUI5
		view elements to model data, allowing changes in the model to be reflected in the view
		element and vice versa.")**  
Bindings connect OpenUI5 view elements to model data, allowing changes in the model to be reflected in the view element and vice versa.
-   **[Binding Events](Binding_Events_1a010d3.md "The OData V4 model supports certain events intended for applications, and others that
		are to be used for controls, as outlined in this section.")**  
The OData V4 model supports certain events intended for applications, and others that are to be used for controls, as outlined in this section.
-   **[Filtering](Filtering_5338bd1.md "The OData V4 Model supports server side filtering on lists.")**  
The OData V4 Model supports server side filtering on lists.
-   **[Sorting](Sorting_d2ce3f5.md "The OData V4 model supports server side sorting on lists.")**  
The OData V4 model supports server side sorting on lists.
-   **[Value Lists](Value_Lists_ab267a6.md "The OData V4 model supports the access to value list metadata and data.")**  
The OData V4 model supports the access to value list metadata and data.
-   **[OData Operations](OData_Operations_b54f789.md "The OData V4 model supports OData operations (ActionImport,
			FunctionImport, bound Actions and bound
			Functions). Unbound parameters are limited to primitive
		values.")**  
The OData V4 model supports OData operations \(`ActionImport`, `FunctionImport`, bound `Actions` and bound `Functions`\). Unbound parameters are limited to primitive values.
-   **[Batch Control](Batch_Control_74142a3.md "OData V4 allows you to group multiple operations into a single HTTP request payload,
		as described in the official OData V4 specification Part 1, Batch Requests (see the link
		under Related Information for more details).")**  
OData V4 allows you to group multiple operations into a single HTTP request payload, as described in the official OData V4 specification Part 1, Batch Requests \(see the link under Related Information for more details\).
-   **[Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md "Each OData V4 model offers access via getMetaModel to a
		corresponding metadata model sap.ui.model.odata.v4.ODataMetaModel, which is
		read-only and offers access to OData V4 metadata in a streamlined JSON format (see links
		under Related Information for more details). Only one-time bindings are supported by this
		model because the metadata is immutable.")**  
Each OData V4 model offers access via `getMetaModel` to a corresponding metadata model `sap.ui.model.odata.v4.ODataMetaModel`, which is read-only and offers access to OData V4 metadata in a streamlined JSON format \(see links under Related Information for more details\). Only one-time bindings are supported by this model because the metadata is immutable.
-   **[Performance Aspects](Performance_Aspects_5a0d286.md "The OData V4 model offers the features described below which influence
		performance.")**  
The OData V4 model offers the features described below which influence performance.
-   **[Unsupported Superclass Methods and Events](Unsupported_Superclass_Methods_and_Events_1232241.md "Certain methods derived from OpenUI5 model and binding
		superclasses are not supported in OData V4 model classes or have limited
		support.")**  
Certain methods derived from OpenUI5 model and binding superclasses are not supported in OData V4 model classes or have limited support.
-   **[Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md "This section outlines the main differences between the OData V2 and OData V4
		models.")**  
This section outlines the main differences between the OData V2 and OData V4 models.
-   **[Creating an Entity](Creating_an_Entity_c9723f8.md "The sap.ui.model.odata.v4.ODataListBinding#create method creates a
		new entity. Users can interact with a newly created entity even before it has been sent to
		the server.")**  
The `sap.ui.model.odata.v4.ODataListBinding#create` method creates a new entity. Users can interact with a newly created entity even before it has been sent to the server.
-   **[Draft Handling with the OData V4 Model](Draft_Handling_with_the_OData_V4_Model_40986e6.md "A draft is an interim version of a business entity that has not yet been explicitly saved. Drafts are saved automatically in the
		background whenever users add or change information within a business entity.")**  
A draft is an interim version of a business entity that has not yet been explicitly saved. Drafts are saved automatically in the background whenever users add or change information within a business entity.
-   **[Deleting an Entity](Deleting_an_Entity_2613ebc.md "The Context.delete method deletes an entity on the server and
		updates the user interface accordingly.")**  
The `Context.delete` method deletes an entity on the server and updates the user interface accordingly.
-   **[Consuming OData V2 Services with the OData V4 Model](Consuming_OData_V2_Services_with_the_OData_V4_Model_365bdbd.md "The OpenUI5 framework can
		consume OData V2 Services in a non-intrusive way as if working directly with OData
		V4.")**  
The OpenUI5 framework can consume OData V2 Services in a non-intrusive way as if working directly with OData V4.
-   **[Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md "The OData V4 Model supports features of the OData Extension for Data Aggregation V4.0
		specification.")**  
The OData V4 Model supports features of the OData Extension for Data Aggregation V4.0 specification.
-   **[Server Messages in the OData V4 Model](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md "The OData V4 model supports server messages sent via an OData V4 service.")**  
The OData V4 model supports server messages sent via an OData V4 service.
-   **[Currency and Unit Customizing in OData V4](Currency_and_Unit_Customizing_in_OData_V4_4d1b9d4.md "For amounts or measures, you may sometimes need different currencies or units than defined in the CLDR. The data types
      sap.ui.model.odata.type.Currency and sap.ui.model.odata.type.Unit enable you to use code lists with
    customizing for currency codes and units. ")**  
For amounts or measures, you may sometimes need different currencies or units than defined in the CLDR. The data types `sap.ui.model.odata.type.Currency` and `sap.ui.model.odata.type.Unit` enable you to use code lists with customizing for currency codes and units.

**Related Information**  


[Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md "This section outlines the main differences between the OData V2 and OData V4 models.")

[sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html)

[Sample: Sales Orders](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.sample.odata.v4.SalesOrders/preview)

