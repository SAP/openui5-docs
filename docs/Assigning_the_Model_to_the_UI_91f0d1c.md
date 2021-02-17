<!-- loio91f0d1c56f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f0d1c56f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f0d1c56f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f0d1c56f4d1014b6dd926db0e91070)</div>

## Assigning the Model to the UI

If you don't want to use a component or descriptor file, you have to assign the model instance manually to the UI, before you can bind controls to this model instance.

OpenUI5 provides a flexible and modularized concept in which you can not only define one model for your applications, but define different areas in your application with different models and assign single controls to a model. You can, for example, define a JSON model for the application and an OData model for a table contol that is contained in the application. You can also set multiple models for a control, a UI area, or the core by specifying a name for the model. These models can be accessed by their name.

``` js
var oJSONModel = new sap.ui.model.json.JSONModel();
var oODataModel  = new sap.ui.model.odata.v2.ODataModel("myServicelUrl");
var oControl  = new sap.m.Input();

oControl.setModel(oODataModel);
//set the JSONModel with the name 'myJSONModel' to the same control
oControl.setModel(oJSONModel,"myJSONModel");
```

When you set a model to a UI area or control, it will be propagated to all aggregated child controls. So if you set a model to a container control, for example, all controls that are contained \(aggregated\) in this container have access to this model. If one of the contained controls has its own model set \(with the same name\), the propagation stops. It is not possible to have two models with the same name set to one control instance.

Choose one of the following options:

-   If you use a Component for your app, you should set the model in the `manifest.json`:

    > Example:  
    > **Setting a model in the manifest.json**
    > 
    > ``` json
    > {
    >   "_version": "1.12.0",
    >   "sap.app": {
    >     ...
    >     "dataSources": {
    >       "invoiceRemote": {
    >         "uri": "https://services.odata.org/V2/Northwind/Northwind.svc/",
    >         "type": "OData",
    >         "settings": {
    >           "odataVersion": "2.0"
    >         }
    >       }
    >     }
    >   },
    >   ...
    >   "sap.ui5": {
    >     ...
    >     "models": {
    >       "i18n": {
    >          ...
    >       },
    >       "invoice": {
    >         "dataSource": "invoiceRemote"
    >       }
    >     }
    >   }
    > }
    > ```

-   You can define a specific model for a particular view by using the `setModel` method available on any control. When the model name `myModel` is omitted, the default model is set.

    ``` js
    this.getView().setModel(oModel, "myModel");
    ```

-   You can also define a specific model for sections within a UI area, for example, inside a panel or for a table control:

    ``` js
    
    var oTable = this.getView().byId("table");
    oTable.setModel(oModel, "myModel");
    ```


**Related information**  


[Components](Components_958ead5.md)

[Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

