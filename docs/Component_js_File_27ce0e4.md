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
sap.ui.define(['sap/ui/core/UIComponent'],
	function(UIComponent) {
	"use strict";

	var Component = UIComponent.extend(*HIGHLIGHT START*"samples.components.sample.Component"*HIGHLIGHT END*, {
		metadata : {
			interfaces: [
				"sap.ui.core.IAsyncContentCreation" 
			],
			manifest : "json"
		}
	});
	return Component;
});
```

The metadata of the component controller should be used to declare the runtime metadata only \(which are the properties, aggregations, associations and events\).

We recommend to define the component metadata externally in the descriptor \(`manifest.json`\), because the descriptor for components is mandatory for modern components and allows performance optimizations.

We recommend to add the `sap.ui.core.IAsyncContentCreation` marker interface when defining a new component. Using this interface allows the component to be created fully asynchronously. This interface will implicitly set the component's `rootView` and router configuration to `async`. Nested views will also be handled asynchronously. Additionally, the error handling during the processing of views is stricter and will fail if a view definition contains errors, e.g. broken binding strings.

-   **[Component Metadata](Component_Metadata_0187ea5.md "The component class provides specific metadata for components by extending the
			ManagedObject class. The UIComponent class provides
		additional metadata for the configuration of user interfaces or the navigation between
		views.")**  
The component class provides specific metadata for components by extending the `ManagedObject` class. The `UIComponent` class provides additional metadata for the configuration of user interfaces or the navigation between views.
-   **[Methods Controlling the Initial Instantiation](Methods_Controlling_the_Initial_Instantiation_b430345.md "OpenUI5 provides two
		methods for the initial instantiation of the component.")**  
OpenUI5 provides two methods for the initial instantiation of the component.

**Related Information**  


[Using and Nesting Components](Using_and_Nesting_Components_346599f.md "You can use a ComponentContainer to wrap a UIComponent and reuse it anywhere within the OpenUI5 control tree. With the ComponentContainer you can nest components inside other components.")

