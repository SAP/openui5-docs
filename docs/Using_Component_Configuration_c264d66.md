<!-- loioc264d66d6e3c4104818bc52c174a000c -->

| loio |
| -----|
| c264d66d6e3c4104818bc52c174a000c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c264d66d6e3c4104818bc52c174a000c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c264d66d6e3c4104818bc52c174a000c)</div>

## Using Component Configuration

OpenUI5 supports the extension of a base controller by merging the delivered standard controller with a custom controller on JavaScript object level.

The OpenUI5 controller extension concept does **not** use inheritance. Instead, methods of the custom controller override standard methods with the same name. The following controller lifecycle methods are, however, an exception to this rule: `onInit`, `onExit`, `onBeforeRendering`, `onAfterRendering`. For these methods, the controller methods of your custom application are called either after \(for `onInit` and `onAfterRendering`\), or before \(for `onExit` and `onBeforeRendering`\) the standard lifecycle methods.

The following examples show how controller extension concept in OpenUI5 works. The following code snippet shows the standard controller `Main.controller.js` of the delivered standard application:

``` js
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

The following code snippet represents the custom controller `CustomMain.controller.js`:

``` js
sap.ui.define(["sap/ui/core/mvc/Controller"], function(Controller) {
    "use strict";
    return Controller.extend("samples.components.ext.customer.CustomMain", {
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

``` js
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

The controller extensions are applied to all controllers with the specified name within the customized component, regardless of whether the controller is instantiated explicitly or belongs to a view.

