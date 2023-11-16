<!-- loio2a46b7567a73457c81b1b67741146063 -->

| loio |
| -----|
| 2a46b7567a73457c81b1b67741146063 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/2a46b7567a73457c81b1b67741146063) | [demo kit latest release](https://sdk.openui5.org/topic/2a46b7567a73457c81b1b67741146063)</div>

## Step 10: Descriptor for Applications \(TypeScript\)

All application-specific configuration settings will now further be put in a separate descriptor file called `manifest.json`. This clearly separates the application coding from the configuration settings and makes our app even more flexible. For example, all SAP Fiori applications are realized as components and come with a descriptor file in order to be hosted in the SAP Fiori launchpad.

The SAP Fiori launchpad acts as an application container and instantiates the app without having a local HTML file for the bootstrap. Instead, the descriptor file will be parsed and the component is loaded into the current HTML page. This allows several apps to be displayed in the same context. Each app can define local settings, such as language properties, supported devices, and more. And we can also use the descriptor file to load additional resources and instantiate models like our `i18n` resource bundle.

***

### Preview

  
  
**An input field and a description displaying the value of the input field \(No visual changes to last step\)**

![](images/loio7b2aef85c016485da4a31c087bf4c0f0_LowRes.png " An input field and a description displaying the value of the input field (No
					visual changes to last step)")

***

### Coding

You can view and download all files at [Walkthrough - Step 10](https://github.com/sap-samples/).

***

<a name="loio2a46b7567a73457c81b1b67741146063__section_oxj_qkk_lzb"/>

### webapp/i18n/i18n.properties

We add new key/value pairs to our text bundle for the app title and the app description; we'll use these texts in our app descriptor. We also add comments to separate the bundle texts semantically.

```ini
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}

```

***

### webapp/manifest.json \(New\)

The content of the `manifest.json` file is a configuration object in JSON format that contains all global application settings and parameters. It is called the descriptor for applications, components, and libraries, and is also referred to as “descriptor” or “app descriptor” when used for applications. It is stored in the `webapp` folder and read by OpenUI5 to instantiate the component.

There are three important sections defined by namespaces in the `manifest.json` file:

-   **`sap.app`**

    The `sap.app` namespace contains the following application-specific attributes:

    -   `id` \(mandatory\): The namespace of our application component. The ID must not exceed 70 characters. It must be unique and must correspond to the component ID/namespace.

    -   `type`: Defines what we want to configure; we describe here an application.

    -   `i18n`: Defines the path to the resource bundle file. The `supportedLocales` and `fallbackLocale` properties are set to empty strings, as our demo app uses only one `i18n.properties` file for simplicity and we'd like to prevent the browser from trying to load additional `i18n_*.properties` files based on your browser settings and your locale.

    -   `title` \(mandatory\): Title of the application in handlebars syntax referenced from the app's resource bundle.

    -   `description`: Short description text what the application does in handlebars syntax referenced from the app's resource bundle.

        > ### Remember:  
        > Properties of the resource bundle are enclosed in two curly brackets in the descriptor. This is not an OpenUI5 data binding syntax, but a variable reference to the resource bundle in the descriptor in handlebars syntax. The referred texts are not visible in the app built in this tutorial but can be read by an application container like the SAP Fiori launchpad.

    -   `applicationVersion` \(mandatory\): The version of the application to be able to update the application easily later on.


-   **`sap.ui`**

    The `sap.ui namespace` contributes the following UI-specific attributes:

    -   `technology`: This value specifies the UI technology; it is `UI5` in our case

    -   `deviceTypes` \(mandatory\): Tells what devices are supported by the app: desktop, tablet, phone \(all true by default\)


-   **`sap.ui5`**

    The `sap.ui5` namespace adds OpenUI5-specific configuration parameters that are automatically processed by OpenUI5. The most important parameters are:

    -   `dependencies` \(mandatory\): Here we declare the dependencies that should be loaded by the OpenUI5 core during the initialization phase of the component and used afterwards. It's mandatory to set via `minUI5Version` the mimimum version of OpenUI5 our component requires. Additionally, we declare the dependency to the libraries `sap.ui.core` and `sap.m` in order to benefit from the asynchronous library preload.

    -   `rootView`: If you specify this parameter, the component will automatically instantiate the view and use it as the root for this component.

    -   `models`: In this section of the descriptor we can define models that will be automatically instantiated by OpenUI5 when the app starts. Here we can now define the local resource bundle. We define the name of the model "i18n" as key and specify the bundle file by namespace. As in the previous steps, the file with our translated texts is stored in the `i18n` folder and named `i18n.properties`. We simply prefix the path to the file with the namespace of our app. The manual instantiation in the app component's `init` method will be removed later in this step. The `supportedLocales` and `fallbackLocale` properties are set to empty strings, as in this tutorial our demo app uses only one `i18n.properties` file for simplicity, and we'd like to prevent the browser from trying to load additional `i18n_*.properties` files based on your browser settings and your locale.


    For compatibility reasons the root object and each of the sections state the descriptor version number under the internal property `_version`. Every new version of OpenUI5 implies a new version of the app descriptor. Features might be added or changed in future versions of the descriptor, and the version number helps to identify the application settings by tools that read the descriptor. You can look up the value of `_version` for eachOpenUI5 release in [this table](https://github.com/SAP/ui5-manifest/blob/master/mapping.json).


```
{
    "_version": "1.59.0",
    "sap.app": {
        "id": "ui5.walkthrough",
        "type": "application",
        "i18n": {
            "bundleUrl": "i18n/i18n.properties",
            "supportedLocales": [
                ""
            ],
            "fallbackLocale": ""
        },
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
        "dependencies": {
            "minUI5Version": "1.108",
            "libs": {
                "sap.ui.core": {},
                "sap.m": {}
            }
        },
        "rootView": {
            "viewName": "ui5.walkthrough.view.App",
            "type": "XML",
            "id": "app"
        },
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "settings": {
                    "bundleName": "ui5.walkthrough.i18n.i18n",
                    "supportedLocales": [
                        ""
                    ],
                    "fallbackLocale": ""
                }
            }
        }
    }
}
```

> ### Note:  
> In this tutorial, we only introduce the most important settings and parameters of the descriptor file. In some development environments you may get validation errors because some settings are missing - you can ignore those in this context.

The existence of the `manifest.json` file must be declared in the component metadata; the Component file is delivered as part of the application archive. So let's do this as a next step.

***

### webapp/Component.ts

In the component's `metadata` section, we now replace the `rootView` property with the property key `manifest` and the value `json`. This defines a reference to the descriptor that will be loaded and parsed automatically when the component is instantiated. We can now completely remove the lines of code containing the model instantiation for our resource bundle. It is done automatically by OpenUI5 with the help of the configuration entries in the descriptor. We can also remove the dependency to `sap/ui/model/resource/ResourceModel` and the corresponding formal parameter `ResourceModel` because we will not use this inside our anonymous callback function.

***

```js
import UIComponent from "sap/ui/core/UIComponent";
import JSONModel from "sap/ui/model/json/JSONModel";

/**
 * @namespace ui5.walkthrough
 */
export default class Component extends UIComponent {
    public static metadata = {
        "interfaces": ["sap.ui.core.IAsyncContentCreation"],
        "manifest": "json" 
    };
    init(): void {
        // call the init function of the parent
        super.init();
        
        // set data model
        const data = {
            recipient: {
                name: "World"
            }
        };
        const dataModel = new JSONModel(data);
        this.setModel(dataModel);
    };
};
```

***

> ### Tip:  
> In previous versions of OpenUI5, additional configuration settings for the app, like the service configuration, the root view, and the routing configuration, had to be added to the metadata section of the Component file. As of OpenUI5 version 1.30, we recommend that you define these settings in the `manifest.json` descriptor file. Apps and examples that were created based on an older OpenUI5 version still use the `Component.js` file for this purpose - so it is still supported, but not recommended.

***

<a name="loio2a46b7567a73457c81b1b67741146063__section_ok2_4n5_zgb"/>

### webapp\\index.html

Now we declare our component in the body of our `index.html`. In the bootstrapping script of our `index.html`, we enable the `ComponentSupport` module. Then we declare our component in the body via a `div` tag. This will instantiate the component when the `onInit` event is executed.

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>UI5 Walkthrough</title>
	<script
		id="sap-ui-bootstrap"
		src="resources/sap-ui-core.js"
		data-sap-ui-theme="sap_horizon"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true"
		data-sap-ui-oninit="module:sap/ui/core/ComponentSupport"
		data-sap-ui-resourceroots='{
			"ui5.walkthrough": "./"
		}'>
	</script>
</head>
<body class="sapUiBody" id="content">
	<div data-sap-ui-component data-name="ui5.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>
</body>
</html>
```

We can delete our `index.ts`, because the descriptor now takes care of everything.

***

### Conventions

-   The descriptor file is named `manifest.json` and stored as a JSON file.

-   The descriptor file is located in the `webapp` folder.

-   Use translatable strings for the title and the description of the app.


**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 9: Component Configuration \(TypeScript\)](Step_9_Component_Configuration_TypeScript_f9d0e2f.md "After we have introduced all three parts of the Model-View-Controller (MVC) concept, we now come to another important structural aspect of OpenUI5.")

**Previous:**[Step 11: Pages and Panels](Step_11_Pages_and_Panels_feed613.md "After all the work on the app structure it’s time to improve the look of our app. We will use two controls from the sap.m library to add a bit more &quot;bling&quot; to our UI. You will also learn about control aggregations in this step.")

**Related Information**  


[Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md "The descriptor for applications, components, and libraries (in short: app descriptor) is inspired by the WebApplication Manifest concept introduced by the W3C. The descriptor provides a central, machine-readable, and easy-to-access location for storing metadata associated with an application, an application component, or a library.")

[Methods Controlling the Initial Instantiation](Methods_Controlling_the_Initial_Instantiation_b430345.md "OpenUI5 provides two methods for the initial instantiation of the component.")

[Advanced Concepts for OpenUI5 Components](Advanced_Concepts_for_OpenUI5_Components_ecbc417.md "Advanced concepts for components include routing and navigation and component data as well as the event bus.")

