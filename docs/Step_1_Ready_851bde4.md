<!-- loio851bde42e4e1410c96abbe402fa9128c -->

| loio |
| -----|
| 851bde42e4e1410c96abbe402fa9128c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/851bde42e4e1410c96abbe402fa9128c) | [demo kit latest release](https://sdk.openui5.org/topic/851bde42e4e1410c96abbe402fa9128c)</div>

## Step 1: Ready...

Let's get you ready for your journey! We bootstrap OpenUI5 in an HTML page and implement a simple "Hello World" example.

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_cpm_14c_1gb"/>

### Preview

   
  
<a name="loio851bde42e4e1410c96abbe402fa9128c__fig_vf2_vfl_4s"/>The browser shows a "Ready" button that triggers a "Hello World" message

 ![](images/loio9c157e9764b846fea7de519d141c33ac_LowRes.png "The browser shows a "Ready" button that triggers a "Hello World" message") 

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_zzy_mpc_1gb"/>

### Coding

You can view and download all files at [Quick Start - Step 1](https://sdk.openui5.org/sample/sap.m.tutorial.quickstart.01/preview).

***

### webapp/index.html \(new\)

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Quickstart Tutorial</title>
	<script id="sap-ui-bootstrap"
		src="https://sdk.openui5.org/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-libs="sap.m"
		data-sap-ui-resourceroots='{"Quickstart": "./"}'
		data-sap-ui-onInit="module:Quickstart/index"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>
</head>
<body class="sapUiBody" id="content"></body>
</html>
```

In your development environment, create the folder `webapp`. In this folder, create an `index.html` file, and paste the above code to this file.

With the `script` tag, we load and initialize OpenUI5 with typical bootstrap parameters. We define, for example, a theme, control libraries, as well as performance and compatibility flags.

First, we need a source to load OpenUI5 from. To keep things convenient, we use the path to our Content Delivery Network \(CDN\) for OpenUI5.

The bootstrap property `resourceroots` defines the namespace for all resources of the app. This way, we can easily reference additional files that we are about to create in this step.

The `index` module that we load with the `onInit` parameter will hold the application logic.

The `body` tag is defined with the `sapUiBody` class and the `content` ID. This is where we will add the content of the app in the next steps.

> ### Tip:  
> For more information about bootstrapping from the CDN, see [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_fh4_t23_1gb"/>

### webapp/index.js \(New\)

```js
sap.ui.define([
	"sap/m/Button",
	"sap/m/MessageToast"
], function (Button, MessageToast) {
	"use strict";

	new Button({
		text: "Ready...",
		press: function () {
			MessageToast.show("Hello World!");
		}
	}).placeAt("content");

});
```

In your `webapp` folder, create a new file `index.js` that will be called as soon as OpenUI5 is loaded and initialized.

We load two UI controls - a button and a message toast - and place the button in the element with the `content` ID. The button is defined with a `text` property and a callback attached to its `press` event.

Now, start the webserver, serve the sources of the \`webapp\` folder, and open the `index.html` file in your browser. When the button is pressed, a message toast with the "Hello World" message is shown at the bottom of the screen.

**Parent topic:** [Quick Start](Quick_Start_592f36f.md "Unleash your OpenUI5 skills with this simple three-step tutorial. We start with a simple &quot;Hello World&quot; example, and convert it to a minimalist two-page app.")

**Previous:** [Step 2: Steady...](Step_2_Steady_128214a.md "Now we extend our minimalist HTML page to a basic app with a view and a controller.")

**Related Information**  


[Development Environment](Development_Environment_7bb04e0.md "This part of the documentation introduces you to some common and recommended use cases for the installation, configuration, and setup of OpenUI5 development environments.")

[Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md "OpenUI5 can either be loaded locally with a relative path from a Web server or externally from a Content Delivery Network (CDN).")

