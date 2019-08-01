<!-- loiob430345887f1419fba50320b57c1bdf9 -->

| loio |
| -----|
| b430345887f1419fba50320b57c1bdf9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b430345887f1419fba50320b57c1bdf9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b430345887f1419fba50320b57c1bdf9)</div>

## Methods Controlling the Initial Instantiation

OpenUI5 provides two methods for the initial instantiation of the component.

You can use the following methods:

-   `init`

    Overwrite this method for example to connect the model between the control and the component. This method is **not** called by the application directly, but called automatically when you create the instance of the component. The routing instance needs to be initialized here, see [Initializing and Accessing a Routing Instance](Initializing_and_Accessing_a_Routing_Instance_acdb6cd.md).

-   `createContent`

    By default, the UI component creates the `sap.ui5/rootView` declared in the manifest as the root control, see [Descriptor Dependencies to Libraries and Components](Descriptor_Dependencies_to_Libraries_and_Components_8521ad1.md).

    Alternatively, you can overwrite this method and programmatically create the root control:

    ``` js
    sap.ui.define(["sap/ui/core/UIComponent", "sap/m/Label"], function(UIComponent, Label) {
        return UIComponent.extend("my.app.Component", {
            metadata: {
                manifest: "json"
            },
    
            createContent: function () {
                return new Label({ text: "Hello!" });
            }
    
        });
    
    });
    ```


> Note:
> The configuration properties for a component, that is, the settings given in the constructor or the `sap.ui.core.Component.create` or `sap.ui.component` call, are not available in the `Init` and `createContent` methods. Use `componentData` instead. For more information, see [`sap.ui.core.Component.create`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Component/methods/sap.ui.core.Component.create).
> 
> 

You can also overwrite the getters and setters for component properties in the `Component.js` file.

