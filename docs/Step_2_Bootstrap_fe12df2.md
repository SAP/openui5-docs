<!-- loiofe12df2e338e43598977d09f3d191b7b -->

| loio |
| -----|
| fe12df2e338e43598977d09f3d191b7b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fe12df2e338e43598977d09f3d191b7b) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fe12df2e338e43598977d09f3d191b7b)</div>

## Step 2: Bootstrap

Before we can do something with OpenUI5, we need to load and initialize it. This process of loading and initializing OpenUI5 is called **bootstrapping**. Once this bootstrapping is finished, we simply display an alert.

***

### Preview

   
  
An alert "UI5 is ready" is displayed<a name="loiofe12df2e338e43598977d09f3d191b7b__fig_r1j_pst_mr"/>

 ![](loiof997780100fe40e7b149abd05bd82677_HiRes.png "An alert "UI5 is ready" is displayed") 

***

### Coding

You can view and download all files at [Walkthrough - Step 2](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.02/preview).

> Note:
> OpenUI5 is a JavaScript library that can either be loaded from the same Web server where the app resides, or from a different server. If OpenUI5 is deployed somewhere else on the server or you want to use a different server, then you need to adjust the corresponding paths in the bootstrap \(here: `src="/resources/sap-ui-core.js"`\) in this tutorial according to your own requirements.
> 
> You can use this reference to the latest stable version of OpenUI5 for the tutorial or for testing purposes, but never use this for productive use. In an actual app, you always have to specify an OpenUI5 version explicitly.
> 
> For more information about the CDN, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).
> 
> In case you are using SAP Web IDE, you can right-click the project and select *New* \> *HTML5 Application Descriptor* to make the `/resources…` reference work. This creates the `neo-app.json` file, which configures a URL mapping for this path.
> 
> 

***

### webapp/index.html

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>SAPUI5 Walkthrough</title>
*HIGHLIGHT START*	<script
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

	</script>*HIGHLIGHT END*
</head>
<body>
<div>Hello World</div>

</body>
</html>
```

In this step, we load the OpenUI5 framework from our local webserver and initialize the core modules with the following configuration options:

-   The `src` attribute of the `<script>` tag tells the browser where to find the OpenUI5 core library – it initializes the OpenUI5 runtime and loads additional resources, such as the libraries specified in the `data-sap-ui-libs` attribute.

-   The OpenUI5 controls support different themes, we choose `sap_belize` as our default theme.

-   We specify the required UI library `sap.m` containing the UI controls we need for this tutorial.

-   To make use of the most recent functionality of OpenUI5 we define the compatibility version as `edge`.

-   We configure the process of “bootstrapping” to run asynchronously.

    This means that the OpenUI5 resources can be loaded simultaneously in the background for performance reasons.

-   We define the module to be loaded initially in a declarative way. With this, we avoid directly executable JavaScript code in the HTML file. This makes your app more secure. We will create the script that this references to further down in this step.
-   We tell OpenUI5 core that resources in the `sap.ui.demo.walkthrough` namespace are located in the same folder as `index.html`. This is, for example, necessary for apps that run in the SAP Fiori launchpad.


***

<a name="loiofe12df2e338e43598977d09f3d191b7b__section_ks2_1bv_xfb"/>

### webapp/index.js \(New\)

``` js
sap.ui.define([

], function () {
	"use strict";


	alert("UI5 is ready");
});

```

Now, we create a new `index.js` script that will contain the application logic for this tutorial step. We do this to avoid having executable code directly in the HTML file for security reasons. This script will be called by the `index.html`. We defined it there as a module in a declarative way.

**Related information**  


[Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing__a04b0d1.md)

[Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md)

[Compatibility Version Information](Compatibility_Version_Information_9feb96d.md)

[Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)

[https://jquery.org/](https://jquery.org/)

[Content Security Policy](Content_Security_Policy_fe1a6db.md)

