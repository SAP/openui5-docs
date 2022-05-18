<!-- loioc264d66d6e3c4104818bc52c174a000c -->

| loio |
| -----|
| c264d66d6e3c4104818bc52c174a000c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/c264d66d6e3c4104818bc52c174a000c) | [demo kit latest release](https://sdk.openui5.org/topic/c264d66d6e3c4104818bc52c174a000c)</div>

## Using Component Configuration

OpenUI5 supports the extension of a base controller by merging the delivered standard controller with a custom controller on JavaScript object level.

OpenUI5 supports two different extension variants. The latest and recommended variant is called [Controller Extension](Using_Controller_Extension_21515f0.md). The old variant, called **Component Configuration** is described in the following section / subsections.

The OpenUI5 Component Configuration concept does not support hierarchical inheritance of methods within a chain of controllers. Instead, methods of the custom controller override any methods of the standard controller with the same name. The following controller lifecycle methods are, however, an exception to this rule: `onInit`, `onExit`, `onBeforeRendering`, `onAfterRendering`. For these methods, the controller methods of your custom application are called either after \(for `onInit` and `onAfterRendering`\), or before \(for `onExit` and `onBeforeRendering`\) the standard lifecycle methods.

> ### Restriction:  
> When using the OpenUI5 Component Configuration concept, only the standard controller can be extended, but a custom controller can **not** be extended again. Only one level of controller extension is allowed; nested controller extension is not supported. We recommend using the more recent [Controller Extension](Using_Controller_Extension_21515f0.md) approach for such a use case.

The following examples show how the Component Configuration concept in OpenUI5 works. The following code snippet shows the standard controller `Main.controller.js` of the delivered standard application:

```js
sap.ui.define(["sap/ui/core/mvc/Controller"], function(Controller) {
    "use strict";
    return Controller.extend("samples.components.ext.sap.Main", {
        onInit : function () {
            console.log("samples.components.ext.sap.Main - onInit");
        },

        doSomething: function() {
            alert("this is an original standard action");
        },

        doSomeStandardAction: function() {
            alert("this is another original standard action");
        }
    });
});
```

The controller extension must not be typed as a controller, but as a plain object. If you prefer to use typed controllers, you can follow the [Controller Replacement](Controller_Replacement_b0b14bf.md) approach. The following code snippet represents the custom controller `CustomMain.controller.js`:

```js
sap.ui.define([], function() {
    "use strict";
    return {
       onInit : function () {
            console.log("samples.components.ext.customer.CustomMain - onInit");
        },

        doSomething: function() {
            alert("this is a customer action");
        },

        doSomeCustomAction: function() {
            alert("this is another customer action");
        }
    });
});
```

The following extension in component configuration merges the two controllers:

```js
extensions: {  
    "sap.ui.controllerExtensions": {
        "samples.components.ext.sap.Main": {
            controllerName: "samples.components.ext.customer.CustomMain"
        }
        }
    // .....some more content
}
```

As a result, the `samples.components.ext.customer.CustomMain` controller functions are merged when the controller `samples.components.ext.sap.Main` is called. After initialization, the log contains the following messages:

```
samples.components.ext.sap.Main - onInit
samples.components.ext.customer.CustomMain - onInit
```

The `doSomething` method of the new controller overwrites the `doSomething` method of the standard controller. Thus, if the method is invoked, an alert popup with the following text appears: *this is a customer action*.

The `doSomeStandardAction` method remains available without changes, as no method with the same name exists in the new controller.

The `doSomeCustomAction` method is additionally available and you can use it, for example, in a view extension.

-   **[Example: Component Configuration](Example_Component_Configuration_08608ef.md "The component configuration contains the information about the extension metadata and
        the objects that are replaced or extended in the custom view or control.")**  
The component configuration contains the information about the extension metadata and the objects that are replaced or extended in the custom view or control.
-   **[Providing Hooks in the Standard Controller](Providing_Hooks_in_the_Standard_Controller_8fbf4e7.md "Hooks are extension points in the controller code that are used to make controller
		extensions more stable.")**  
Hooks are extension points in the controller code that are used to make controller extensions more stable.
-   **[View Extension](View_Extension_403c050.md "OpenUI5 uses extension
        points for extending standard views with custom content. The assignment of a custom view to
        an extension point is done in component customizing.")**  
OpenUI5 uses extension points for extending standard views with custom content. The assignment of a custom view to an extension point is done in component customizing.
-   **[View Modification](View_Modification_aa93e1c.md "For modifying views, control properties of standard views can be changed.")**  
For modifying views, control properties of standard views can be changed.
-   **[View Replacement](View_Replacement_98861cf.md "Views of a delivered standard application can be replaced to adapt the application to
		the customer needs.")**  
Views of a delivered standard application can be replaced to adapt the application to the customer needs.
-   **[Controller Replacement](Controller_Replacement_b0b14bf.md "Standard controller can be replaced by specifying a new controller name in a replacement
		View and implementing this Controller.")**  
Standard controller can be replaced by specifying a new controller name in a replacement View and implementing this Controller.

