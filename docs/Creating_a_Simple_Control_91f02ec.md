<!-- loio91f02ece6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f02ece6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f02ece6f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f02ece6f4d1014b6dd926db0e91070)</div>

## Creating a Simple Control

Example of a simple control with a `name` property

The control is used to render the text "Hello <name\>":

```js
// "Control" required from "sap/ui/core/Control"

Control.extend("my.Hello", {                  // call the new Control type "my.Hello" 
                                              // and let it inherit from sap.ui.core.Control
    metadata : {                              // the Control API
        properties : {
            "name" : "string"                 // setter and getter are created behind the scenes, 
                                              // including data binding and type validation
        }
    },

    renderer : {
        apiVersion: 2,                        // see 'Renderer Methods' for an explanation of this flag
        render: function(oRm, oControl) {     // the part creating the HTML
            oRm.openStart("span", oControl).openEnd();
            oRm.text("Hello " + oControl.getName()); // write the Control property 'name', with automatic XSS protection
            oRm.close("span");
        }
    }
});
```

The new control is ready for use now. To instantiate and display the control, use the following code:

```js

new my.Hello({name:"UI5"}).placeAt("content");
```

