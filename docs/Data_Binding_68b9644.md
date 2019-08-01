<!-- loio68b9644a253741e8a4b9e4279a35c247 -->

| loio |
| -----|
| 68b9644a253741e8a4b9e4279a35c247 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/68b9644a253741e8a4b9e4279a35c247) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/68b9644a253741e8a4b9e4279a35c247)</div>

## Data Binding

You use data binding to bind UI elements to data sources to keep the data in sync and allow data editing on the UI.

***

![](loio544b09736447477198202b636048bab8_LowRes.png)

-   [Views](Views_91f27e3.md)
-   [Models](Models_e1b6259.md)
-   [Resource Bundles](Resource_Bundles_91f225c.md)

OpenUI5 follows the "Model View Controller" \(MVC\) paradigm, which means that we clearly separate data sources \(model\), UI \(view\), and application logic \(controller\) from each other. Data binding defines how models and views communicate with each other.

Depending on which external data source you use, you can choose between different model types to represent it. OpenUI5 supports OData V4 \(with restrictions\), OData V2, JSON, and XML models.

There are also internal data sources that are defined in the app for specific purposes. For those, an app contains the following models:

-   The **resource model** is used to communication with the resource bundle that contains translatable texts in multiple languages

-   The **device model** is provided by the framework and defines device-specific settings

-   **View models** can be, for example, JSON models that communicate with a corresponding JSON object. JSON data can also be edited in the app, but they are not stored - as soon as you refresh the browser or restart the app, the changes are reset.


Most of the models are client-side models. This means that all data is initially loaded to the model when the app is started. All actions performed on the data are only executed on the client, and only sent back to the data source when this is triggered by the app. Client-side models are therefore only recommended for small data sets.

The OData models \(V2 and V4\) are server-side models, which means that data is only requested on demand from the back end. Filtering, sorting, and paging actions are performed on the server. This means, for example, that you don't have to load a complete table on the UI to be able to sort the entries.

In the view, you bind data by specifying the **binding path** for a control. You can use **data types** and **formatters** to validate and format the data on the UI.

> Note:
> To learn more about data binding use the tutorial: [Data Binding](Data_Binding_e531093.md)
> 
> 

***

<a name="loio68b9644a253741e8a4b9e4279a35c247__section_emw_hxq_5cb"/>

### Binding Modes: One-time Binding, One-way Binding, and Two-way Binding

The binding mode defines how the data sources are bound. OpenUI5 provides the following binding modes:

-   One-way binding means a binding from the model to the view; value changes in the model update all corresponding bindings and the view

-   Two-way binding means a binding from the model to the view and from the view to the model, changes in the model and in the view fire events that automatically trigger updates all corresponding bindings and the view and model

-   One-time binding means from model to view once.


The following table shows which binding modes the respective binding models support:

|Model|One-time|One-way|Two-way|
|-----|--------|-------|-------|
|OData V4 model| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)|
|OData V2 model| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|ODataMetaModel V4| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Not supported](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|ODataMetaModel| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)| ![Not supported](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Not supported](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|JSON model| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)|
|XML model| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)|
|Resource model| ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Supported](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) \(default\)| ![Not supported](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |

For more information, see [API Reference: `sap.ui.model.BindingMode`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.BindingMode.html). 

