<!-- loio91f2702f6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f2702f6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f2702f6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f2702f6f4d1014b6dd926db0e91070)</div>

## Typed Views and Controllers

More complex use cases may require a more formal way to define views and controllers. For this, typed views and controllers are used.

To create a controller that is a new type of its own, you need to write a boilerplate code and declare the functions of the new prototype:

``` js

/* boilerplate code for typed Controller */
jQuery.sap.declare({modName:"sap.hcm.AddressController", type:"controller"}); // declaring a special type of module   
sap.hcm.AddressController = function () { // the constructor
   sap.ui.core.mvc.Controller.apply(this, arguments);
};
jQuery.sap.require("sap.ui.core.mvc.Controller"); // this is currently required, as the Controller is not loaded by default
sap.hcm.AddressController.prototype = jQuery.sap.newObject(sap.ui.core.mvc.Controller.prototype); // chain the prototypes
/* end of boilerplate code for typed Controller */
        

// to avoid the above we could in the future offer it behind a simple call to:
// sap.ui.defineController("sap.hcm.Address");
        

sap.hcm.AddressController.prototype.onInit = function() {
   // modify control tree - this is the regular lifecycle hook

};
        

// implement an event handler in the Controller
sap.hcm.AddressController.prototype.doSomething = function() {
   alert("Hello World");
};
```

