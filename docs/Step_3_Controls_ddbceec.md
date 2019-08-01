<!-- loioddbceecd7d3d42eea9cf78a820a238fb -->

| loio |
| -----|
| ddbceecd7d3d42eea9cf78a820a238fb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ddbceecd7d3d42eea9cf78a820a238fb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ddbceecd7d3d42eea9cf78a820a238fb)</div>

## Step 3: Controls

Now it is time to build our first little UI by replacing the “Hello World” text in the HTML body by the OpenUI5 control `sap.m.Text`. In the beginning, we will use the JavaScript control interface to set up the UI, the control instance is then placed into the HTML body.

***

### Preview

   
  
The "Hello World" text is now displayed by a OpenUI5 control<a name="loioddbceecd7d3d42eea9cf78a820a238fb__fig_r1j_pst_mr"/>

 ![](loio7cad93a924694474acd782b34e162d4b_HiRes.png "The "Hello World" text is now displayed by a OpenUI5 control") 

***

<a name="loioddbceecd7d3d42eea9cf78a820a238fb__section_ccm_jyv_xfb"/>

### Coding

You can view and download all files at [Walkthrough - Step 3](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.03/preview).

***

<a name="loioddbceecd7d3d42eea9cf78a820a238fb__section_dcm_jyv_xfb"/>

### webapp/index.html

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>SAPUI5 Walkthrough</title>
	<script
		id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-libs="sap.m"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true"
		data-sap-ui-onInit="module:sap/ui/demo/walkthrough/index"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": "./"
		}'>
	</script>
</head>
*HIGHLIGHT START*<body class="sapUiBody" id="content">
</body>
*HIGHLIGHT END*
</html>

```

The class `sapUiBody` adds additional theme-dependent styles for displaying OpenUI5 apps.

***

<a name="loioddbceecd7d3d42eea9cf78a820a238fb__section_yk4_kyv_xfb"/>

### webapp/index.js

``` js
sap.ui.define([
*HIGHLIGHT START*	"sap/m/Text"
*HIGHLIGHT END*
], function (*HIGHLIGHT START*Text*HIGHLIGHT END*) {
	"use strict";

*HIGHLIGHT START*	new Text({
		text: "Hello World"
	}).placeAt("content");
*HIGHLIGHT END*
});

```

Instead of using native JavaScript to display a dialog we want to use a simple OpenUI5 control. Controls are used to define appearance and behavior of parts of the screen.

In the example above, the callback of the `init` event is where we now instantiate a OpenUI5 text control. The name of the control is prefixed by the namespace of its control library `sap/m/` and the options are passed to the constructor with a JavaScript object. For our control we set the `text` property to the value “Hello World”.

We chain the constructor call of the control to the standard method `placeAt` that is used to place OpenUI5 controls inside a node of the document object model \(DOM\) or any other OpenUI5 control instance. We pass the ID of a DOM node as an argument. As the target node we use the body tag of the HTML document and give it the ID `content`.

All controls of OpenUI5 have a fixed set of properties, aggregations, and associations for configuration. You can find their descriptions in the Demo Kit. In addition, each controls comes with a set of public functions that you can look up in the API reference.

Don’t forget to remove the “Hello World” `p`.

> Note:
> Only instances of `sap.ui.core.Control` or their subclasses can be rendered stand-alone and have a `placeAt` function. Each control extends `sap.ui.core.Element` that can only be rendered inside controls. Check the API reference to learn more about the inheritance hierarchy of controls. The API documentation of each control refers to the directly known subclasses.
> 
> 

**Related information**  


[Working with Controls](Working_with_Controls_91f0a22.md)

[API Reference: `sap.m.Text`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.Text.html)

[Samples: `sap.m.Text` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.Text/samples)

[API Reference: `sap.ui.core.Control`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.Control.html)

[API Reference: `sap.ui.core.Element`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.Element.html)

[API Reference: `sap.ui.base.ManagedObject`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.base.ManagedObject.html)

