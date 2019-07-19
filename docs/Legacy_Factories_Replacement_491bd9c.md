<!-- loio491bd9c70b9f4c4d913c8c7b4a970833 -->

| loio |
| -----|
| 491bd9c70b9f4c4d913c8c7b4a970833 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/491bd9c70b9f4c4d913c8c7b4a970833) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/491bd9c70b9f4c4d913c8c7b4a970833)</div>

## Legacy Factories Replacement

Overview of the replacement of global functions with the factory functions

The AMD module syntax already avoids Globals and enforces the strict dependency declaration. The following table shows how APIs which use synchronous requests to fetch modules or resources internally, can be replaced with asynchronous alternatives. The W3C has already deprecated the use of synchronous requests in the browser main thread, so this replacement prepares your applications for the removal of synchronous requests.

The OpenUI5 framework by default uses synchronous requests internally in several places. Most have already been replaced by asynchronous alternatives, or prepared to exchange the synchronous behaviour shown below. The asynchronous adoption starts from the beginning with the bootstrap script tag, where the `async` configuration parameter should be set to `true`. Applications can register an event callback via [`sap.ui.getCore()#attachInit`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Core/methods/attachInit). . The examples below show only the most frequently used synchronous APIs. There are more of these APIs, and most often the asynchronous alternatives return a `Promise` that can be used to retrieve the former return value.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Legacy, synchronous API</th>
			<th>Modern API</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Declarative App Description</td>
			<td> 

```

sap.ui.component({

    name: "my.comp"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/Component'], function(Component){

    Component.create({

        name: "my.comp"

        // default: manifest: true

    }).then(function(oComp) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Components - Some API still experimental</td>
			<td> 

```

var oComponentInstance = sap.ui.component({

    name: "my.comp"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/Component'], function(Component){

    Component.create({

        name: "my.comp"

    }).then(function(oComp) { ... });

```

 Alternatively, migrate to `componentUsages` with an additional adaption in the `manifest.json` file: ```

createContent: function() {

   var oReuseComponentPromise = this.createComponent({

    "usage": "reuse"

  }).then(function(oComp) { ... });

}

```
			</td>
		</tr>
		<tr>
			<td> 

```

var oComponentClass = sap.ui.component.load({

    name: "my.comp"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/Component'], function(Component){

    Component.load({

        name: "my.comp"

    }).then(function(oClass) {

        var oComponentInstance = new oClass({...});

    });

});

```
			</td>
		</tr>
		<tr>
			<td> 

```
var oComponentInstance = sap.ui.component("my-comp-id");
```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/Component'], function(Component){

 

    var oComponentInstance = Component.get("my-comp-id");

});

```
			</td>
		</tr>
		<tr>
			<td>i18n texts</td>
			<td> 

```

jQuery.sap.resources({

    url: "mybundle.properties"

});

```
			</td>
			<td> 

```

// sap/ui/Resources -> sap/base/i18n/ResourceBundle

sap.ui.require(['sap/base/i18n/ResourceBundle'], function(Resource){

    ResourceBundle.create({

        url: "mybundle.properties",
	   asynch: true

    }).then(function(oResource) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Views</td>
			<td> 

```

var oView = sap.ui.view({

    viewName: "my.View",

    type: "XML"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/mvc/View'], function(View){

    View.create({ 

        viewName: "my.View",

        type: "XML"

    }).then(function(oView) { ... });

```
			</td>
		</tr>
		<tr>
			<td> 

```

var oView = sap.ui.xmlview({

    viewName: "my.View"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/mvc/XMLView'], function(XMLView){

    XMLView.create({ 

        viewName: "my.View"

    }).then(function(oView) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Controllers</td>
			<td> 

```
var oController = sap.ui.controller({ ... });
```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/mvc/Controller'], function(Controller){

    Controller.create({ 

        ...

    }).then(function(oController) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Extension Points</td>
			<td> 

```
var oView = sap.ui.extensionpoint( ... );
```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/ExtensionPoint'], function(ExtensionPoint){

    ExtensionPoint.load({ 

        ...

    }).then(function(aControls) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Fragments</td>
			<td> 

```

var oView = sap.ui.fragment({ 

    name: "my.fragment",

    type: "XML"

});

```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/Fragment'], function(Fragment){

    Fragment.load({

        name: "my.fragment",

        type: "XML"

    }).then(function(aControls) { ... });

```
			</td>
		</tr>
		<tr>
			<td>Version Info</td>
			<td> 

```
var oView = sap.ui.getVersionInfo();
```
			</td>
			<td> 

```

sap.ui.require(['sap/ui/core/VersionInfo'], function(VersionInfo){

    VersionInfo.load({ 

        ...

    }).then(function(oVersionInfo) { ... });

```
			</td>
		</tr>
	</tbody>
</table>

