<!-- loioabd4d7c7548d4c29ab8364d3904a6d74 -->

| loio |
| -----|
| abd4d7c7548d4c29ab8364d3904a6d74 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/abd4d7c7548d4c29ab8364d3904a6d74) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/abd4d7c7548d4c29ab8364d3904a6d74)</div>

## Changes Compared to OData V2 Model

This section outlines the main differences between the OData V2 and OData V4 models.

While some of the differences between the OData V4 model and the OData V2 model are due to features that have not yet been implemented, many differences are due to the following:

-   Protocol incompatibility between OData V4 and OData V2

-   API cleanup and simplification

-   Adherence to OData V4 standards regarding the names and terms used in APIs


These differences will therefore remain even after all features have been implemented. The table below gives you an overview of these changes, as well as the reason behind them and \(if applicable\) how the OData V2 model mechanism is supported in the OData V4 model.


<table>
<tr>
<th valign="top">

Change



</th>
<th valign="top">

Reason



</th>
</tr>
<tr>
<td valign="top">

Binding parameter names: The binding parameter name for an OData system query option is identical to the system query option name: `$expand`, `$select`, ... \(V2 uses `expand`, `select`\).



</td>
<td valign="top">

Simplification: The OData V4 model simplifies the binding parameter structure to just one map where all entries in the map are OData query options, with the exception of entries that have a key starting with "$$" \(binding-specific parameters\). In all cases, the names of the binding parameters are exactly the same as in the OData URL sent to the server.



</td>
</tr>
<tr>
<td valign="top">

The model does not support the methods `getData`, `getObject`, `getOriginalProperty`, `getProperty`. For data access, use the context API instead of methods on the model.



</td>
<td valign="top">

OData requires asynchronous data retrieval: Synchronous data access requires that data has already been loaded from the server. This means there is no way of knowing whether this already happened, meaning the result of a synchronous access method is quite often unpredictable.

The OData V4 context API offers ansynchronous and synchronous access to the data of a specific context. It is no longer necessary to construct a path for data access as needed by the methods on the model. For more information, see the section *Context API* in [Bindings](Bindings_54e0ddf.md).



</td>
</tr>
<tr>
<td valign="top">

Minimize APIs required for batch control: Model does not support the methods `getChangeBatchGroups`, `getChangeGroups`, `getDeferredGroups`, `setChangeBatchGroups`, `setChangeGroups`, `setDeferredBatchGroups`, `setDeferredGroups`, `setUseBatch` \(and corresponding model construction parameters\).



</td>
<td valign="top">

Simplification: Batch groups are solely defined via binding parameters with the corresponding parameters on the model as default. Application groups are by default deferred; there is no need to set or get deferred groups. You just need the `submitBatch` method on the model to control execution of the batch. You can use the predefined batch group `"$direct"` to switch off batch either for the complete model or for a specific binding \(only possible for the complete model in V2\). For more information, see [Batch Control](Batch_Control_74142a3.md).



</td>
</tr>
<tr>
<td valign="top">

OData operations executed via binding: Model does not support the method `callFunction`.



</td>
<td valign="top">

Simplification: Use an operation binding instead; it is now much easier to bind operation execution results to controls.



</td>
</tr>
<tr>
<td valign="top">

No CRUD methods on model: Model does not support the methods `create`, `read`, `remove`, `update`.



</td>
<td valign="top">

Simplification: `read`, `update`, `create` and `remove` operations are available implicitly via the bindings. Bindings can also be used without controls. It is not possible to trigger requests for specific OData URLs. For more information, see [Accessing Data in Controller Code](Accessing_Data_in_Controller_Code_17b30ac.md).



</td>
</tr>
<tr>
<td valign="top">

No metadata access via model: Model does not support methods `getServiceAnnotations`, `getServiceMetadata`, `refreshMetadata` as well as methods corresponding to the events `metadataFailed`, `metadataLoaded`.



</td>
<td valign="top">

Simplification: Metadata is only accessed via `ODataMetaModel`. Metadata is only loaded when needed \(e.g. for type detection or to compute URLs for write requests\); the corresponding methods on the `v4.ODataMetaModel` use promises instead of events.



</td>
</tr>
<tr>
<td valign="top">

 [sap.ui.model.odata.AnnotationHelper](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.AnnotationHelper.html) is not supported for OData V4.



</td>
<td valign="top">

Simplification: Much of the functionality in [sap.ui.model.odata.AnnotationHelper](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.AnnotationHelper.html) is provided by [sap.ui.model.odata.v4.ODataMetaModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataMetaModel.html)and [sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html). You can find the remaining functionality in the OData V4 specific [sap.ui.model.odata.v4.AnnotationHelper](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper.html).

> ### Example:  
> The path syntax supported by the v4.ODataMetaModel, see [sap.ui.model.odata.v4.ODataMetaModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataMetaModel.html), method `requestObject` allows for navigation in the model's metadata; there is no need to use `AnnotationHelper` methods for this.



</td>
</tr>
<tr>
<td valign="top">

The property binding automatically determines the appropriate type depending on the property's metadata, unless a type is specified explicitly.



</td>
<td valign="top">

For more information, see [Type Determination](Type_Determination_53cdd55.md).

> ### Note:  
> By default, a property binding delivers a value formatted according to the target type of the control property it applies to, for example`boolean` in case of `<Icon src="sap-icon://message-warning" visible="{path: 'DeliveryDate', formatter: '.isOverdue'}">`. This leads to errors, because type determination adds the correct type for the `DeliveryDate` property, which is `DateTimeOffset`, and cannot format its value as `boolean`. In such cases, use `targetType: 'any'` as follows:
> 
> ``` xml
> <Icon 
> 	src="sap-icon://message-warning" 
> 	visible="{
> 		path: 'DeliveryDate', 
> 		targetType: 'any', 
> 		formatter: '.isOverdue'
> 	}"/>
> ```
> 
> The above also applies to [Expression Bindings](Expression_Binding_daf6852.md). In this case, there is a convenience notation `%{binding}`, which is a shortcut for `${path: 'binding', targetType: 'any'}`.

> ### Note:  
> A property binding can have an object value. For more information, see [Property Binding With an Object Value](Initialization_and_Read_Requests_fccfb2e.md#loiofccfb2eb41414f0792c165e69a878717__section_g5j_v1r_mgb):
> 
> ``` xml
> <SimpleForm binding="{/BusinessPartnerList('42')}">
> 	<Label text="Phone number list"/>
> 	<Text
> 		text="{
> 			path: 'BP_2_CONTACT', 
> 			mode: 'OneTime', 
> 			targetType: 'any', 
> 			formatter: '.formatPhoneNumbersAsCSV'
> 		}"/>
> </SimpleForm>
> ```



</td>
</tr>
</table>

**Related Information**  


[sap.ui.model.odata.AnnotationHelper](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.AnnotationHelper.html)

[sap.ui.model.odata.v4.ODataMetaModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataMetaModel.html)

[sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataModel.html)

