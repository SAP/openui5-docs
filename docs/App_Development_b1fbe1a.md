<!-- loiob1fbe1a22f8d4a5bbb601591e27b68d1 -->

| loio |
| -----|
| b1fbe1a22f8d4a5bbb601591e27b68d1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/b1fbe1a22f8d4a5bbb601591e27b68d1) | [demo kit latest release](https://sdk.openui5.org/topic/b1fbe1a22f8d4a5bbb601591e27b68d1)</div>

## App Development

There are several ways to develop OpenUI5 applications. Select the one that meets the requirements of your projects and your expectations best.

***

### Leverage UI5 Tooling

[UI5 Tooling](https://sap.github.io/ui5-tooling/) complements the framework as an open and modular toolchain. It comes with a [command line interface \(CLI\)](https://sap.github.io/ui5-tooling/pages/CLI/) based on Node.js and npm.

For an application project which has not been enabled yet for UI5 Tooling, follow the concise [Getting Started](https://sap.github.io/ui5-tooling/pages/GettingStarted/) documentation for initial project setup.

The [OpenUI5 sample application](https://github.com/SAP/openui5-sample-app#openui5-sample-app), available on GitHub, shows typical development steps in your application project. The full set of commands can be seen in the [CLI](https://sap.github.io/ui5-tooling/pages/CLI/#commands) documentation.

***

### Using a Content Delivery Network

If you don't want to download the files and don't want to include them in your deployment, you can use the online version of OpenUI5 . For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

***

<a name="loiob1fbe1a22f8d4a5bbb601591e27b68d1__section_pfb_lzx_3fb"/>

### Download OpenUI5

You may just want to get the runtime from the OpenUI5 website at [http://openui5.org](http://openui5.org) and deploy it on a web server.

1.  Go to [https://openui5.org/releases/](https://openui5.org/releases/) and choose *Download Stable Release* to download a ZIP file containing the current stable release of the OpenUI5 sources.

2.  Unzip this archive and put the entire content onto the web server where your application runs \(or you could package it within your application to deploy it along with the app\).

3.  In your app’s main HTML file, load OpenUI5 by referring to the `resources/sap-ui-core.js` file that was contained in the ZIP archive. \(See [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).\)


