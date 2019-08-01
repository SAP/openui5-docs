<!-- loiob0b14bf4dcdb476fb0d63877c1beff7c -->

| loio |
| -----|
| b0b14bf4dcdb476fb0d63877c1beff7c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b0b14bf4dcdb476fb0d63877c1beff7c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b0b14bf4dcdb476fb0d63877c1beff7c)</div>

## Controller Replacement

Standard controller can be replaced by specifying a new controller name in a replacement View and implementing this Controller.

For a view replacement, you can either use the standard controller of the replaced view by setting its name as `controllerName`, or use and extend the standard controller, or you can replace the controller by specifying a new controller name in the new view and implementing the new controller.

An extension option is available that allows to replace an original controller without replacing its view. This is especially useful for typed controllers, that is, controllers that have been defined with the `extend` syntax:

``` js
sap.ui.define([
    "sap/ui/core/mvc/Controller"
], function(Controller) {
    "use strict";
 
    return Controller.extend("samples.components.ext.customer.CustomMain", {
        onInit: function() { /* do something */ },
        onBeforeRendering: function() { /* do something */ },
        onAfterRendering: function() { /* do something */ },
        onExit: function() { /* do something */ },
        myEventHandler: function(oEvent) { /* do something */ }
    });
 
});
```

To replace the controller of the standard application with the custom controller, use the following extension configuration:

``` js
extensions: { 
    "sap.ui.controllerReplacements": {
        "samples.components.ext.sap.Main": "samples.components.ext.customer.CustomMain"
    },
    .....some more content
```

> Note:
> Typed controllers cannot be extended by using the controller extension configuration \(`sap.ui.controllerExtensions`\). Instead, you use the controller replacement configuration \(`sap.ui.controllerReplacements`\) to extend a typed controller with the `extend` syntax and call the original methods in the custom implementation:
> 
> ``` js
> sap.ui.define([
>     "samples/components/ext/customer/CustomMain"
> ], function(CustomController) {
>     "use strict";
>   
>     return CustomController.extend("samples.components.ext.partner.PartnerMain", {
>         onInit: function() { 
>             CustomController.prototype.onInit.apply(this, arguments);
>             /* do something */ 
>         },
>         onBeforeRendering: function() { 
>             CustomController.prototype.onBeforeRendering.apply(this, arguments);
>             /* do something */ 
>         },
>         onAfterRendering: function() {
>             /* do something */
>             CustomController.prototype.onAfterRendering.apply(this, arguments);
>         },
>         onExit: function() {
>             /* do something */
>             CustomController.prototype.onExit.apply(this, arguments);
>         },
>         myEventHandler: function(oEvent) {
>             CustomController.prototype.myEventHandler.apply(this, arguments);
>             /* do something */ 
>         }
>     });
>   
> });
> ```
> 
> The chaining of the lifecycle methods is **not** done automatically. You can control on your own, if or when to call the parent lifecycle methods. In addition, you can always access the methods defined in the original controller.
> 
> 

