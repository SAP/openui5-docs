<!-- loioc9ab34570cc14ea5ab72a6d1a4a03e3f -->

| loio |
| -----|
| c9ab34570cc14ea5ab72a6d1a4a03e3f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c9ab34570cc14ea5ab72a6d1a4a03e3f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c9ab34570cc14ea5ab72a6d1a4a03e3f)</div>

## Renderer Methods

The `renderer` method is responsible for creating the HTML structure for the control.

The `renderer` method is a static method, so no `this` keyword is available, but a control instance and a `RenderManager` instance are given to the method. The `RenderManager` collects and concatenates string fragments and places them in the DOM at the appropriate position.

``` js
renderer: function(oRM, oControl) {
   oRM.write("<div>", oControl.getText(), "</div>");
}
```

A control must have exactly one HTML element as a root node, additional elements may be added below this node. `oRM.writeControlData(oControl);` must be called while the root node is written. Thus, the root element can be marked as OpenUI5 control root and the ID of the control is written. Also, `oRM.writeClasses();` must be called in the root element of the control, in order to enable support of `addStyleClass()` for the control.

A new renderer type inherits from the renderer of the parent control. If a control extends, for example, the `InputBase` control, the function is added to a class that inherits from `sap.m.InputBaseRenderer` and can access the respective functions.

``` js
sap.ui.define(['sap/ui/core/Renderer', 'sap/m/InputBaseRenderer'],
                function(Renderer, InputBaseRenderer) {
                "use strict";
                
                var CustomInputRenderer = Renderer.extend(InputBaseRenderer);


                ...

                return CustomInputRenderer;
}, /* bExport= */ true);

```

If an existing renderer is used without modification, you can use the name of the respective renderer class:

``` js
renderer: "sap.m.ButtonRenderer"
```

A control renderer can also override or implement methods from the renderer superclass. And it can separate out helper functions.

This is shown in the following example. Note that the methods need to be packed together into an object to indicate that they all go into the control renderer. The main rendering method is called `render`. The `this` keyword refers to the control renderer type and is used to access the other methods:

``` js

renderer: {

   render: function(oRM, oControl) {

      oRM.write("<div>");

      oRM.writeEscaped(this.square(oControl.getValue()));

      oRM.write("</div>");

   },

   square: function(value) {

      return value * value;

   }

}
```

