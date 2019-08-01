<!-- loio28b59ca857044a7890a22aec8cf1fee9 -->

| loio |
| -----|
| 28b59ca857044a7890a22aec8cf1fee9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/28b59ca857044a7890a22aec8cf1fee9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/28b59ca857044a7890a22aec8cf1fee9)</div>

## App Overview: The Basic Files of Your App

We recommend creating at least three files for your app: the descriptor \(`manifest.json`\), the component \(`Component.js`\), and the main view of the app \(`App.view.xml`\).

 ![](loioeeae30fe7983476a9777e809a8820147_LowRes.png) 

***

### Descriptor \(`manifest.json`\)

We recommend that you use the `manifest.json` file to configure the app settings and put all important information needed to run the app in there. Using this approach means you need to write less application code, and you can already access the information before the app is instantiated.

Some attributes in the descriptor are just for information purposes, such as the minimum OpenUI5 version \(`minUI5version`\), others help external components \(for example the SAP Fiori launchpad \(FLP\)\) to integrate the application correctly, but most of the attributes are actually used to configure specific aspects of the app that are needed frequently.

The most important configuration settings are:

-   **Models**. Examples of models are the configuration of the OData service \(default model\) and language files \(i18n model\). All models described in the `manifest.json` file are automatically instantiated when the app is started.

-   **Libraries** and **components** that are used in the app and have to be loaded during app initialization.

-   The **root view** of your application.

-   **Routing** configuration that defines the navigation between views.


***

### Root View \(`App.view.xml`\)

The `App.view.xml` file defines the root view of the app. In most cases, it contains an `App` control or a `SplitApp` control as a root control.

OpenUI5 supports multiple view types \(XML, HTML, JavaScript, JSON\). We recommend using XML views, as for these you have to separate the controller logic from the view definition in a controller file \(for example `App.controller.js`\).

We also recommend creating a separate view file for each view you want to use in your app.

***

### Component \(`Component.js`\)

The `Component.js` file holds the app setup. The `init` function of the component is automatically started by OpenUI5 when the component is instantiated.

> Note:
> Your component extends `UIComponent`. If you are overriding the init function of your component, you have to make sure that you call the `init` function of `UIComponent` and initialize the router afterwards.
> 
> 

In the metadata section of the component, you define a reference to the descriptor file. When the component is instantiated, the descriptor is loaded and parsed automatically.

***

### HTML Page

All apps are started using an HTML page that loads OpenUI5 and the component. You have two options: You can build an app for the FLP or build a standalone app.

-   **App for FLP**

    The FLP instantiates the component based on the information given in the descriptor file. The FLP can contain multiple apps at the same time. Each app can define local settings, such as supported themes or supported devices.

    This app cannot be run standalone, meaning no `index.html` file is created but only HTML files for testing the app in the FLP sandbox.

    For more information, search for *Embedding SAPUI5 Applications* in the documentation of your SAP NetWeaver version on the SAP Help Portal at [https://help.sap.com/viewer/p/SAP\_NETWEAVER](https://help.sap.com/viewer/p/SAP_NETWEAVER).

-   **Standalone app**

    If you want to run your app standalone, you need to create an `index.html` file. Within this file, you instantiate the component.


**Related information**  


[Folder Structure: Where to Put Your Files](Folder_Structure_Where_to_Put_Your_Files_003f755.md)

[App Initialization: What Happens When an App Is Started?](App_Initialization_What_Happens_When_an_App_Is_Started_d2f5869.md)

[Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

[Model View Controller \(MVC\)](Model_View_Controller_(MVC)_91f2334.md)

[Controller](Controller_121b8e6.md)

[Views](Views_91f27e3.md)

[Models](Models_e1b6259.md)

[Routing and Navigation](Routing_and_Navigation_3d18f20.md)

[Components](Components_958ead5.md)

