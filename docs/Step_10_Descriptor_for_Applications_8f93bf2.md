<!-- loio8f93bf2b2b13402e9f035128ce8b495f -->

| loio |
| -----|
| 8f93bf2b2b13402e9f035128ce8b495f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8f93bf2b2b13402e9f035128ce8b495f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8f93bf2b2b13402e9f035128ce8b495f)</div>

## Step 10: Descriptor for Applications

All application-specific configuration settings will now further be put in a separate descriptor file called `manifest.json`. This clearly separates the application coding from the configuration settings and makes our app even more flexible. For example, all SAP Fiori applications are realized as components and come with a descriptor file in order to be hosted in the SAP Fiori launchpad.

The SAP Fiori launchpad acts as an application container and instantiates the app without having a local HTML file for the bootstrap. Instead, the descriptor file will be parsed and the component is loaded into the current HTML page. This allows several apps to be displayed in the same context. Each app can define local settings, such as language properties, supported devices, and more. And we can also use the descriptor file to load additional resources and instantiate models like our `i18n` resource bundle.

***

### Preview

   
  
<a name="loio8f93bf2b2b13402e9f035128ce8b495f__fig_r1j_pst_mr"/>An input field and a description displaying the value of the input field \(No visual changes to last step\)

 ![](loioe5a9bb4cb06b4d9c8b37914bf5cd2d13_HiRes.png " An input field and a description displaying the value of the input field (No
					visual changes to last step)") 

***

### Coding

You can view and download all files at [Walkthrough - Step 10](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.10/preview).

> ### Caution:  
> Automatic model instantiation is only available as of OpenUI5 version 1.30. If you are using an older version, you can manually instantiate the resource bundle and other models of the app in the `init` method of the `Component.js` file as we did in [Step 9: Component Configuration](Step_9_Component_Configuration_4cfa608.md).

***

### webapp/manifest.json \(New\)

``` js
*HIGHLIGHT START*{
  "_version": "1.12.0",
  "sap.app": {
	"id": "sap.ui.demo.walkthrough",
	"type": "application",
	"i18n": "i18n/i18n.properties",
	"title": "{{appTitle}}",
	"description": "{{appDescription}}",
	"applicationVersion": {
	  "version": "1.0.0"
	}
  },
  "sap.ui": {
	"technology": "UI5",
	"deviceTypes": {
		"desktop": true,
		"tablet": true,
		"phone": true
	}
  },
  "sap.ui5": {
	"rootView": {
		"viewName": "sap.ui.demo.walkthrough.view.App",
		"type": "XML",
		"id": "app"
	},
	"dependencies": {
	  "minUI5Version": "1.93",
	  "libs": {
		"sap.ui.core": {},
		"sap.m": {}
	  }
	},
	"models": {
	  "i18n": {
		"type": "sap.ui.model.resource.ResourceModel",
		"settings": {
		  "bundleName": "sap.ui.demo.walkthrough.i18n.i18n",
		  "supportedLocales": [""],
		  "fallbackLocale": ""
		}
	  }
	}
  }
}*HIGHLIGHT END*
```

> ### Note:  
> In this tutorial, we only introduce the most important settings and parameters of the descriptor file. In SAP Web IDE, you may get validation errors because some settings are missing - you can ignore those in this context.

The content of the `manifest.json` file is a configuration object in JSON format that contains all global application settings and parameters. The manifest file is called the descriptor for applications, components, and libraries and is also referred to as “descriptor” or “app descriptor” when used for applications. It is stored in the `webapp` folder and read by OpenUI5 to instantiate the component. There are three important sections defined by namespaces in the `manifest.json` file:

-   **`sap.app`**

    The `sap.app` namespace contains the following application-specific attributes:

    -   `id` \(mandatory\): The namespace of our application component

        The ID must not exceed 70 characters. It must be unique and must correspond to the component ID/namespace.

    -   `type`: Defines what we want to configure, here: an application

    -   `i18n`: Defines the path to the resource bundle file

    -   `title`: Title of the application in handlebars syntax referenced from the app's resource bundle

    -   `description`: Short description text what the application does in handlebars syntax referenced from the app's resource bundle

    -   `applicationVersion`: The version of the application to be able to easily update the application later on


-   **`sap.ui`**

    The `sap.ui namespace` contributes the following UI-specific attributes:

    -   `technology`: This value specifies the UI technology; in our case we use OpenUI5

    -   `deviceTypes`: Tells what devices are supported by the app: desktop, tablet, phone \(all true by default\)


-   **`**sap.ui5**`**

    The `sap.ui5` namespace adds OpenUI5-specific configuration parameters that are automatically processed by OpenUI5. The most important parameters are:

    -   `rootView`: If you specify this parameter, the component will automatically instantiate the view and use it as the root for this component

    -   `dependencies`: Here we declare the UI libraries used in the application

    -   `models`: In this section of the descriptor we can define models that will be automatically instantiated by OpenUI5 when the app starts. Here we can now define the local resource bundle. We define the name of the model "i18n" as key and specify the bundle file by namespace. As in the previous steps, the file with our translated texts is stored in the `i18n` folder and named `i18n.properties`. We simply prefix the path to the file with the namespace of our app. The manual instantiation in the app component's init method will be removed later in this step. The `supportedLocales` and `fallbackLocale` properties are set to empty strings, as in this tutorial our demo app uses only one `i18n.properties` file for simplicity, and we'd like to prevent the browser from trying to load additional `i18n_*.properties` files based on your browser settings and your locale.


    For compatibility reasons the root object and each of the sections state the descriptor version number `1.1.0` under the internal property `_version`. Features might be added or changed in future versions of the descriptor and the version number helps to identify the application settings by tools that read the descriptor.


> ### Note:  
> Properties of the resource bundle are enclosed in two curly brackets in the descriptor. This is not a OpenUI5 data binding syntax, but a variable reference to the resource bundle in the descriptor in handlebars syntax. The referred texts are not visible in the app built in this tutorial but can be read by an application container like the SAP Fiori launchpad.

***

<a name="loio8f93bf2b2b13402e9f035128ce8b495f__section_ok2_4n5_zgb"/>

### webapp\\index.html

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
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": "./"
		}'
*HIGHLIGHT START*		data-sap-ui-oninit="module:sap/ui/core/ComponentSupport"*HIGHLIGHT END*
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>
</head>
<body class="sapUiBody" id="content">
*HIGHLIGHT START*	<div data-sap-ui-component data-name="sap.ui.demo.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>*HIGHLIGHT END*
</body>
</html>
```

Now we declare our component in the body of our `index.html`. In the bootstrapping script of our `index.html`, we enable the `ComponentSupport` module and remove the `sap.m` library. Then, we declare our component in the body via a `div` tag. This will instantiate the component when the `onInit` event is executed.

We will no longer need our `index.js` from now on, because the descriptor takes care of everything.

***

### webapp/i18n/i18n.properties

``` prefs
*HIGHLIGHT START*# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel*HIGHLIGHT END*
showHelloButtonText=Say Hello
helloMsg=Hello {0}

```

In the resource bundle we simply add the texts for the app and add comments to separate the bundle texts semantically.

***

### webapp/Component.js

``` js
sap.ui.define([
   "sap/ui/core/UIComponent",
   "sap/ui/model/json/JSONModel"
], function (UIComponent, JSONModel) {
   "use strict";
   return UIComponent.extend("sap.ui.demo.walkthrough.Component", {
      *HIGHLIGHT START*metadata : {
            interfaces: ["sap.ui.core.IAsyncContentCreation"],
            manifest: "json"
      },*HIGHLIGHT END*
      init : function () {
         // call the init function of the parent
         UIComponent.prototype.init.apply(this, arguments);
         // set data model
         var oData = {
            recipient : {
               name : "World"
            }
         };
         var oModel = new JSONModel(oData);
         this.setModel(oModel);
      }
   });
});

```

In the component's `metadata` section, we now replace the `rootView` property with the property key `manifest` and the value `json`. This defines a reference to the descriptor that will be loaded and parsed automatically when the component is instantiated. We can now completely remove the lines of code containing the model instantiation for our resource bundle. It is done automatically by OpenUI5 with the help of the configuration entries in the descriptor. We can also remove the dependency to `sap/ui/model/resource/ResourceModel` and the corresponding formal parameter `ResourceModel` because we will not use this inside our anonymous callback function.

***

> ### Tip:  
> In previous versions of OpenUI5, additional configuration settings for the app, like the service configuration, the root view, and the routing configuration, had to be added to the metadata section of the `Component.js` file. As of OpenUI5 version 1.30, we recommend that you define these settings in the `manifest.json` descriptor file. Apps and examples that were created based on an older OpenUI5 version still use the `Component.js` file for this purpose - so it is still supported, but not recommended.

***

### Conventions

-   The descriptor file is named `manifest.json` and located in the `webapp` folder.

-   Use translatable strings for the title and the description of the app.


**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 9: Component Configuration](Step_9_Component_Configuration_4cfa608.md "After we have introduced all three parts of the Model-View-Controller (MVC) concept, we now come to another important structural aspect of OpenUI5.")

**Previous:** [Step 11: Pages and Panels](Step_11_Pages_and_Panels_3b9d9f8.md "After all the work on the app structure it’s time to improve the look of our app. We will use two controls from the sap.m library to add a bit more &quot;bling&quot; to our UI. You will also learn about control aggregations in this step.")

**Related Information**  


[Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md "The descriptor for applications, components, and libraries (in short: app descriptor) is inspired by the WebApplication Manifest concept introduced by the W3C. The descriptor provides a central, machine-readable, and easy-to-access location for storing metadata associated with an application, an application component, or a library.")

[Methods Controlling the Initial Instantiation](Methods_Controlling_the_Initial_Instantiation_b430345.md "OpenUI5 provides two methods for the initial instantiation of the component.")

[Advanced Concepts for OpenUI5 Components](Advanced_Concepts_for_OpenUI5_Components_ecbc417.md "Advanced concepts for components include routing and navigation and component data as well as the event bus.")

