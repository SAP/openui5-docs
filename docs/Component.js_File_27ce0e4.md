<!-- loio27ce0e4987cd426f8fa3e60836316428 -->

| loio |
| -----|
| 27ce0e4987cd426f8fa3e60836316428 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/27ce0e4987cd426f8fa3e60836316428) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/27ce0e4987cd426f8fa3e60836316428)</div>

## Component.js File

The `Component.js` file is the component controller and provides the runtime metadata and the component methods.

A component controller is defined with the asynchronous module definition \(AMD\) syntax. In the `sap.ui.define` statement; the required dependencies can be declared which can be used in the controller.

To create an OpenUI5 component, you extend either the `Component` or `UIComponent` base class and pass the name of the module \(namespace + `.Component`\).

``` js
sap.ui.define(['jquery.sap.global', 'sap/ui/core/UIComponent'],
	function(jQuery, UIComponent) {
	"use strict";

	var Component = UIComponent.extend(*HIGHLIGHT START*"samples.components.sample.Component"*HIGHLIGHT END*, {
		metadata : {
			manifest : "json"
		}
	});
	return Component;
});
```

The metadata of the component controller should be used to declare the runtime metadata only \(which are the properties, aggregations, associations and events\).

We recommend to define the component metadata externally in the descriptor \(`manifest.json`\), because the descriptor for components is mandatory for modern components and allows performance optimizations.

**Related information**  


[Using and Nesting Components](Using_and_Nesting_Components_346599f.md)

