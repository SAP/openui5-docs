<!-- loioe2e6f4127fe4450ab3cf1339c42ee832 -->

| loio |
| -----|
| e2e6f4127fe4450ab3cf1339c42ee832 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e2e6f4127fe4450ab3cf1339c42ee832) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e2e6f4127fe4450ab3cf1339c42ee832)</div>

## Binding Syntax

You bind UI elements to data of a data source by defining a binding path to the model that represents the data source in the app.

***

When defining a binding path for a control, a binding context is created which connects this control to a data model. The UI control then gets the data through that context and displays it on the screen.

![](loio493c875d822445458e0b56e0cc6451b2_LowRes.png)

-   [Views](Views_91f27e3.md)
-   [Models](Models_e1b6259.md)
-   [Binding Path](Binding_Path_2888af4.md)

***

<a name="loioe2e6f4127fe4450ab3cf1339c42ee832__section_ezj_nhr_5cb"/>

### Simple Binding

To reference model data in a view , you can use the simple binding syntax "`{*/path/to/data*}`":

``` xml
<Input value="{/firstName}"/>
```

You can add other properties, such as formatters, data types, or events:

-   Data type:

    ``` xml
    <Input value="{path: '/firstName', type: 'sap.ui.model.type.String'}"/>
    ```

-   Formatter:

    ``` xml
    <Input value="{path: '/firstName', formatter: 'my.globalFormatter'}"/>
    ```

-   Event:

    ``` xml
    <Input value="{path: '/firstName', events: { dataRequested: '.onMyDataRequested'}"/>
    ```


For more information, see [Binding Path](Binding_Path_2888af4.md).

For more information about data types and formatters, see [Formatting, Parsing, and Validating Data](Formatting_Parsing_and_Validating_Data_07e4b92.md).

***

<a name="loioe2e6f4127fe4450ab3cf1339c42ee832__section_njl_ypr_5cb"/>

### Composite Binding

If a control requires data from multiple different model properties, you use a `parts` array of `path`s to define composite binding paths:

``` xml
<TextField value="{
	parts: [
		{path:'birthday/day'},
		{path:'birthday/month'},
		{path:'birthday/year'}
	], 
	formatter:'my.globalFormatter'
}"/>
```

For more information, see [Composite Binding](Composite_Binding_a2fe8e7.md) and [Examples for Data Binding in Different View Types](Examples_for_Data_Binding_in_Different_View_Types_25ab54b.md).

***

<a name="loioe2e6f4127fe4450ab3cf1339c42ee832__section_htn_jqr_5cb"/>

### Expression Binding in XML Views

Expression binding is a simple way to calculate values directly in the view. For example, if you want to change the color of the price depending on whether it is above or below some threshold. With expression binding you don't have to declare a separate formatter:

``` xml
<ObjectStatus state="{= ${products>UnitPrice}  > ${/priceThreshold} ? 'Error' : 'Success' }"/>
```

For more information, see [Expression Binding](Expression_Binding_daf6852.md).

***

<a name="loioe2e6f4127fe4450ab3cf1339c42ee832__section_kft_lqr_5cb"/>

### Property Metadata Binding for OData Services

With metadata binding, you can bind properties of a control to the corresponding property that is defined in the metadata of an OData service:

``` xml
<Input maxLength="{/#Company/ZipCode/@maxLength}"/>
```

For more information, see [Property Metadata Binding](Property_Metadata_Binding_f5aa4bb.md).

-   **[Binding Path](Binding_Path_2888af4.md "Binding paths address the different properties and lists in a model and define how a node in the hierarchical data tree can be found.")**  
Binding paths address the different properties and lists in a model and define how a node in the hierarchical data tree can be found.
-   **[Composite Binding](Composite_Binding_a2fe8e7.md "Calculated fields enable the binding of multiple properties in different models to a
		single property of a control.")**  
Calculated fields enable the binding of multiple properties in different models to a single property of a control.
-   **[Expression Binding](Expression_Binding_daf6852.md "Expression binding is an enhancement of the OpenUI5 binding syntax, which
		allows for providing expressions instead of custom formatter functions.")**  
Expression binding is an enhancement of the OpenUI5 binding syntax, which allows for providing expressions instead of custom formatter functions.
-   **[Property Metadata Binding](Property_Metadata_Binding_f5aa4bb.md "An extended data binding syntax makes it possible to access the metadata for certain properties of an entity in OData services, such as
		heading, label, and precision.")**  
An extended data binding syntax makes it possible to access the metadata for certain properties of an entity in OData services, such as heading, label, and precision.
-   **[Examples for Data Binding in Different View Types](Examples_for_Data_Binding_in_Different_View_Types_25ab54b.md "Examples how complex syntax can be used for calculated fields in XML, HTML, and JS
        views.")**  
Examples how complex syntax can be used for calculated fields in XML, HTML, and JS views.

**Related Information**  


[API Reference: `sap.ui.base.ManagedObject.bindProperty`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindProperty)

[API Reference: `sap.ui.base.ManagedObject.bindAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindAggregation)

[API Reference: `sap.ui.base.ManagedObject.bindObject`](https://openui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject/methods/bindObject)

