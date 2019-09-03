<!-- loiob1fbe1a22f8d4a5bbb601591e27b68d1 -->

| loio |
| -----|
| b1fbe1a22f8d4a5bbb601591e27b68d1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b1fbe1a22f8d4a5bbb601591e27b68d1) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b1fbe1a22f8d4a5bbb601591e27b68d1)</div>

## App Development Using OpenUI5

Develop apps using OpenUI5 and the development environment \(editor and Web server\) of your choice. You can either download all of the sources or refer to the online version of OpenUI5.

***

### Download OpenUI5

The default way of downloading and installing OpenUI5 is to get the runtime from the OpenUI5 website at [http://openui5.org](http://openui5.org) and deploy it on a Web server.

1.  Go to [https://openui5.org/releases/](https://openui5.org/releases/) and choose *Download Stable Release* to download a ZIP file containing the current stable release of the OpenUI5 sources.

2.  Unzip this file and put the entire content on the Web server where your application is running \(or you can even package it within your application to deploy it along with the app\).

3.  In your app’s main HTML file, load OpenUI5 by referring to the `resources/sap-ui-core.js` file that was contained in the ZIP file. \(See [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).\)


***

### Using OpenUI5 Sources from a Content Delivery Network

If you don't want to download the files and don't want to include them in your deployment, you can use the online version of OpenUI5. For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

> Note:
> You can find a list of all available OpenUI5 versions here: [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html).
> 
> Only use the *Stable* version for productive apps. Nevertheless, if you also want to test the [*Nightly*](https://openui5nightly.hana.ondemand.com) version, you are very welcome to send us your feedback!
> 
> 

***

<a name="loiob1fbe1a22f8d4a5bbb601591e27b68d1__section_pfb_lzx_3fb"/>

### Consume OpenUI5 Using the Node Package Manager

You can also use the node package manager \(npm\) to develop your applications. For this, you need to add the OpenUI5 dependencies to your package.json file:

``` js
{
  ...
  "dependencies": {
    "@openui5/sap.m": "^1.60.0",
    "@openui5/sap.ui.core": "^1.60.0",
    "@openui5/sap.ui.layout": "^1.60.0",
    "@openui5/themelib_sap_belize": "^1.60.0"
  },
  ...
}
```

To install single dependencies for your application via npm, simply run the npm install command from your terminal:

```node.js
npm install @openui5/sap.ui.core @openui5/themelib_sap_belize [...]
```

You can find a sample application, which uses this mechanism and describes its usage, on GitHub at [https://github.com/SAP/openui5-sample-app](https://github.com/SAP/openui5-sample-app).

For more information on how to use npm and how to serve your application based on these packages, see the UI5 tooling documentation on GitHub at [https://sap.github.io/ui5-tooling/](https://sap.github.io/ui5-tooling/).

