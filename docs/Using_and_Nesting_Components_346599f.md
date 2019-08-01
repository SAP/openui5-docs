<!-- loio346599f0890d4dfaaa11c6b4ffa96312 -->

| loio |
| -----|
| 346599f0890d4dfaaa11c6b4ffa96312 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/346599f0890d4dfaaa11c6b4ffa96312) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/346599f0890d4dfaaa11c6b4ffa96312)</div>

## Using and Nesting Components

You can use a `ComponentContainer` to wrap a `UIComponent` and reuse it anywhere within the OpenUI5 control tree. You can use reuse components to nest components in other components.

***

<a name="loio346599f0890d4dfaaa11c6b4ffa96312__section_oqk_jhc_zz"/>

### Component Containers

To render UI components, you must wrap them in a `ComponentContainer`. You **cannot** use the `placeAt` method to place UI components directly in a page. A component container carries specific settings and also contains the lifecycle methods of a regular control, such as the `onBeforeRendering` and `onAfterRendering` methods. The lifecycle methods of the `ComponentContainer` are forwarded to the corresponding methods of the nested component.

The `ComponentContainer` separates the application and the nested component. The control tree and data binding of the inner component are decoupled from the outer component.

If you want to share data with the inner component, you can use the `propagateModel` property on the `ComponentContainer` to forward models and binding contexts to the inner component.

You load and create a `UIComponent` in one of the following ways:

-   Load the component asynchronously before creating the container:

``` js
	// "Component" required from module "sap/ui/core/Component"
	// "ComponentContainer" required from module "sap/ui/core/ComponentContainer"
	Component.load({
		name: "samples.components.sample",
	}).then(function(oComponent) {
		var oContainer = new ComponentContainer({
			component: oComponent
		});
		oContainer.placeAt("target");
	});
```

-   Load the component asynchronously while creating the container:

``` js
	// "ComponentContainer" required from module "sap/ui/core/ComponentContainer"
	// "coreLibrary" required from module "sap/ui/core/library"
	var oContainer = new ComponentContainer({
		name: "samples.components.sample",
		lifecycle: coreLibrary.ComponentLifecycle.Container,
		async: true
	});
	oContainer.placeAt("target");
```

-   Load the component asynchronously with "manifest first" mode by specifying the URL of the descriptor \(`manifest.json`\):

``` js
	// "Component" required from module "sap/ui/core/Component"
	// "ComponentContainer" required from module "sap/ui/core/ComponentContainer"
	Component.load({
		manifest: "samples/components/sample/manifest.json",
	}).then(function(oComponent) {
		var oContainer = new ComponentContainer({
			component: oComponent
		});
		oContainer.placeAt("target");
	});
```

-   Load the component asynchronously with "manifest first" mode by specifying the component name:

``` js
	var oContainer = new sap.ui.core.ComponentContainer({
		name: "samples.components.sample",
		manifest: true,
		async: true
	});
	oContainer.placeAt("target");
```


> Note:
> You can use the `lifecycle` property to determine whether the container or your application code will take care of destroying the component.
> 
> 

***

#### Using a Component Container to Load Components from a Different Location

You may want to load components from a location that is different from the location where the OpenUI5 libraries are located or a location that is not registered as a resource root in the OpenUI5 bootstrap.

You can do so by defining the URL of the additional components as a setting for the component factory or the component container:

-   Loading the component asynchronously before creating the container:

``` js
	// "Component" required from module "sap/ui/core/Component"
	// "ComponentLifecycle" required from module "sap/ui/core/ComponentLifecycle"
	Component.load({
		name: "samples.components.sample",
		url: "./"
	}).then(function(oComponent) {
		var oContainer = new ComponentContainer({
			component: oComponent
		});
		oContainer.placeAt("target");
	});
```

-   Loading the component asynchronously when creating the container:

``` js
	// "ComponentContainer" required from module "sap/ui/core/ComponentContainer"
	// "coreLibrary" required from module "sap/ui/core/library"
	var oContainer = new ComponentContainer({
		name: "samples.components.sample",
		lifecycle: coreLibrary.ComponentLifecycle.Container,
		async: true,
		url: "./"
	});
	oContainer.placeAt("target");
```

Here you use the `lifecycle` property to make sure that the component is destroyed when the container is destroyed.


***

<a name="loio346599f0890d4dfaaa11c6b4ffa96312__section_fph_13c_zz"/>

### Reuse Components

To be able to reuse a component, the component has to be declared in the `componentUsages` section of the `manifest.json` descriptor file as follows:

``` json
"sap.ui5": {
  "componentUsages": {
    "myreuse": {
      "name": "sap.reuse.component",
      "settings": {},
      "componentData": {},
      "lazy": false
    }
  }
}
```

The reuse component is declared via its `componentUsage` ID as the key and the supported values are `name` \(name of the component\), `settings`, `componentData` and `lazy`. The values defined in the `manifest.json` file will be merged with the values specified in the instance-specific component factory function An exception to this is the lazy flag which is an indicator for the Component factory function how to handle the dependency. Allowed values in the instance-specific factory function are `settings`, `componentData`, `async`, and `id`.

The `lazy` flag is used to indicate whether the Component should be already preloaded or not. By default, the Components defined in the usage are lazy. A Component preloaded with the flag `lazy: false` has to be explicitly maintained in the `manifest.json`.

For more information, see [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md).

If you want to exchange the reuse component, for example, to extend an app, you simple exchange the reuse component in the `manifest.json` descriptor file.

Reuse components that are embedded by a library must have an explicit entry in the `manifest.json` in the `sap.app/embeddedBy` section:

```
"sap.app": {
  "embeddedBy": "../"
}
```

Under `embeddedBy`, you specify the relative path to the namespace root of the library. This ensures that tools like the application index can discover embedded libraries and won't include them in the transitive scope \(otherwise you would get unwanted 404 requests\). Additionally tools should declare a library dependency to the embedding library. This will ensure that the library containing the component preload will be loaded automatically instead of the trying to load the component preload by itself.

***

#### Instantiation

To instantiate the reuse component in the current component, you use an instance-specific factory function. The factory function requires at least the `componentUsage ID` as a parameter \(simplified usage\) or a configuration object that contains the `usage` and optionally `settings` and `componentData` \(extended usage\).

-   Example for simplified usage \(Async\):

``` js
this.createComponent("myreuse").then(function(oComponent) {
  // ...
});
```

-   Example for simplified usage \(Sync, but not recommended\):

``` js
var oComponent = this.createComponent({ 
  usage: "myreuse"
  settings: {},
  componentData: {},
  async: false 
});
```

-   Example for extended usage:

``` js
var oComponentPromise = this.createComponent({
  usage: "myreuse"
  settings: {},
  componentData: {},
  async: true 
});
```


***

#### Declarative Usage

You can also declare a reuse component directly, for example, in your JavaScript or XML code. In an XML view, the local service factory can only be used via the `ComponentContainer` that has a superordinate component.

``` xml
<View ...>
  <ComponentContainer usage="myreuse" async="true"></ComponentContainer>
</View>
```

***

#### Migration

If you have been reusing components before we introduced the reuse feature described above, we recommend that you refactor your code and implement the new logic.

If you use a component that is embedded in a library, and the application declares a dependency to that library, remove the dependency to the library from the embedding application. Make sure that the application code does not contain any direct references to the component or the embedding application.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Old Code</th>
			<th>Recommended Code</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `manifest.json` with dependency declaration only:
``` json
{
  "sap.ui5": {
    "dependencies": {
      "components": {
        "sap.reuse.component": {}
``` json
{
  "sap.ui5": {
    "dependencies": {
      "components": {
        "sap.reuse.component": {}
      }
    },
    *HIGHLIGHT START*"componentUsages": {
      "reuse": {
        "name": "sap.reuse.component",
        "lazy": false
      }
    }
*HIGHLIGHT END*
  }
}
```
        "lazy": false
      \}
    \}
**
  }
}
```

 > Note:
 > As of version 1.56 it is sufficient to declare the component usage and to indicate whether the component should be lazy loaded or not. The declaration of the component dependencies can and should be avoided in this case.
			</td>
		</tr>
		<tr>
			<td> `Component.js` with nested reuse component:
``` js
createContent: function() {
   
  var oReuseComponent = sap.ui.component({
    "name": "sap.reuse.component"
  });
 
``` js
createContent: function() {
   
*HIGHLIGHT START*  var oReuseComponentPromise = this.createComponent({ /* this = Component instance */
    "usage": "reuse"
  });*HIGHLIGHT END*
 
}
```
  \}\);**
 
}
```
			</td>
		</tr>
	</tbody>
</table>

**Related information**  


[Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md)

[API Reference: `sap.ui.core.ComponentContainer`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.ComponentContainer.html)

[API Reference: `sap.ui.core.ComponentContainer.setLifecycle`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.ComponentContainer/methods/setLifecycle)

[Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

