<!-- loio851bde42e4e1410c96abbe402fa9128c -->

| loio |
| -----|
| 851bde42e4e1410c96abbe402fa9128c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/851bde42e4e1410c96abbe402fa9128c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/851bde42e4e1410c96abbe402fa9128c)</div>

## Step 1: Ready...

Let's get you ready for your journey! We bootstrap OpenUI5 in an HTML page and implement a simple "Hello World" example.

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_cpm_14c_1gb"/>

### Preview

   
  
The browser shows a "Ready" button that triggers a "Hello World" message<a name="loio851bde42e4e1410c96abbe402fa9128c__fig_vf2_vfl_4s"/>

 ![](loio9c157e9764b846fea7de519d141c33ac_LowRes.png "The browser shows a "Ready" button that triggers a "Hello World" message") 

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_zzy_mpc_1gb"/>

### Coding

You can view and download all files at [Quick Start - Step 1](https://openui5.hana.ondemand.com/#/sample/sap.m.tutorial.quickstart.01/preview).

***

### webapp/index.html \(new\)

``` html
*HIGHLIGHT START*<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Quickstart Tutorial</title>
	<script id="sap-ui-bootstrap"
		src="../../../../../../../../resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-libs="sap.m"
		data-sap-ui-resourceroots='{"Quickstart": "./"}'
		data-sap-ui-onInit="module:Quickstart/index"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>
</head>
<body class="sapUiBody" id="content"></body>
</html>*HIGHLIGHT END*
```

In your development environment \(SAP Web IDE is recommended\), create the folder `webapp`. In this folder, create an `index.html` file, and paste the above code to this file.

With the `script` tag, we load and initialize OpenUI5 with typical bootstrap parameters. We define, for example, a theme, control libraries, as well as performance and compatibility flags.

First, we need a source to load OpenUI5 from. To keep things convenient, we use the path to our Content Delivery Network \(CDN\) for OpenUI5.

The bootstrap property `resourceroots` defines the namespace for all resources of the app. This way, we can easily reference additional files that we are about to create in this step.

The `index` module that we load with the `onInit` parameter will hold the application logic.

The `body` tag is defined with the `sapUiBody` class and the `content` ID. This is where we will add the content of the app in the next steps.

> Note:
> For more information about bootstrapping from the CDN, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).
> 
> 

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_fh4_t23_1gb"/>

### webapp/index.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
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

});*HIGHLIGHT END*
```

In your `webapp` folder, create a new file `index.js` that will be called as soon as OpenUI5 is loaded and initialized.

We load two UI controls - a button and a message toast - and place the button in the element with the `content` ID. The button is defined with a `text` property and a callback attached to its `press` event.

Now open the `index.html` file in your browser. When the button is pressed, a message toast with the "Hello World" message is shown at the bottom of the screen.

***

<a name="loio851bde42e4e1410c96abbe402fa9128c__section_ghq_k4d_b3b"/>

### neo-app.json \(new, optional\)

> Note:
> This file is necessary if you use SAP Web IDE as your development environment. It contains all project settings and is located in the root folder of your project. This file is **not** part of the downloadable code in the Demo Kit, so just copy the content from here.
> 
> 

``` json
*HIGHLIGHT START*{
  "welcomeFile": "/webapp/index.html",
  "routes": [
    {
      "path": "/resources",
      "target": {
        "type": "application",
        "name": "sapui5preview",
        "entryPath": "/resources"
      },
      "description": "SAPUI5 Resources"
    },
    {
      "path": "/resources",
      "target": {
        "type": "service",
        "name": "sapui5",
        "entryPath": "/resources"
      },
      "description": "SAPUI5 Resources"
    }
  ],
  "sendWelcomeFileRedirect": true
}*HIGHLIGHT END*
```

**Related information**  


[Development Environment](Development_Environment_7bb04e0.md)

[Create a neo-app.json Project Configuration File](Create_a_neo-app.json_Project_Configuration_File_28fa753.md)

[Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)

