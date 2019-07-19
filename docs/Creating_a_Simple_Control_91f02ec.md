<!-- loio91f02ece6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f02ece6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f02ece6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f02ece6f4d1014b6dd926db0e91070)</div>

## Creating a Simple Control

Example of a simple control with a `name` property

The control is used to render the text "Hello <name\>":

``` js

sap.ui.core.Control.extend("my.Hello", {      // call the new Control type "my.Hello" 
                                              // and let it inherit from sap.ui.core.Control
    metadata : {                              // the Control API
        properties : {
            "name" : "string"                 // setter and getter are created behind the scenes, 
                                              // including data binding and type validation
        }
    },

    renderer : function(oRm, oControl) {      // the part creating the HTML
        oRm.write("<span>Hello ");
        oRm.writeEscaped(oControl.getName()); // write the Control property 'name', with XSS protection
        oRm.write("</span>");
    }
});
```

> Note:
> In this example, `writeControlData(oControl)` and `writeClasses()` are not called inside the root HTML element of the control to keep the example simple. In productive controls this needs to be done.
> 
> 

The new control is ready for use now. To instantiate and display the control, use the following code:

``` js

new my.Hello({name:"UI5"}).placeAt("content");
```

