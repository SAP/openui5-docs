<!-- loiof665d0de4dba405f9af4294de824b03b -->

| loio |
| -----|
| f665d0de4dba405f9af4294de824b03b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f665d0de4dba405f9af4294de824b03b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f665d0de4dba405f9af4294de824b03b)</div>

## Step 6: Modules

In OpenUI5, resources are often referred to as modules. In this step, we replace the alert from the last exercise with a proper Message Toast from the `sap.m` library. The required modules are enabled to be loaded asynchronously.

***

### Preview

   
  
A message toast displays the "Hello World" message<a name="loiof665d0de4dba405f9af4294de824b03b__fig_r1j_pst_mr"/>

 ![](loio7c11ea91acc94ac3870831f1dd7c1c07_HiRes.png "A message toast displays the "Hello World" message") 

***

### Coding

You can view and download all files at [Walkthrough - Step 6](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.06/preview).

``` js
sap.ui.define([
   "sap/ui/core/mvc/Controller"*HIGHLIGHT START*,
   "sap/m/MessageToast"*HIGHLIGHT END*
], function (Controller, *HIGHLIGHT START*MessageToast*HIGHLIGHT END*) {
   "use strict";
   return Controller.extend("sap.ui.demo.walkthrough.controller.App", {
      onShowHello : function () {
        *HIGHLIGHT START* MessageToast.show("Hello World");*HIGHLIGHT END*
      }
   });
});
```

We extend the array of required modules with the fully qualified path to `sap.m.MessageToast`. Once both modules, `Controller` and `MessageToast`, are loaded, the callback function is called and we can make use of both objects by accessing the parameters passed on to the function.

This Asynchronous Module Definition \(AMD\) syntax allows to clearly separate the module loading from the code execution and greatly improves the performance of the application. The browser can decide when and how the resources are loaded prior to code execution.

***

### Conventions

-   Use `sap.ui.define` for controllers and all other JavaScript modules to define a global namespace. With the namespace, the object can be addressed throughout the application.

-   Use `sap.ui.require` for asynchronously loading dependencies but without declaring a namespace, for example code that just needs to be executed, but does not need to be called from other code.

-   Use the name of the artifact to load for naming the function parameters \(without namespace\).


**Related information**  


[API Reference: `sap.ui.define`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.define)

[API Reference: `sap.ui.require`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.require)

