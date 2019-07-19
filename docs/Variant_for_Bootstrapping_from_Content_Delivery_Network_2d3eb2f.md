<!-- loio2d3eb2f322ea4a82983c1c62a33ec4ae -->

| loio |
| -----|
| 2d3eb2f322ea4a82983c1c62a33ec4ae |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae)</div>

## Variant for Bootstrapping from Content Delivery Network

OpenUI5 can either be loaded locally with a relative path from a Web server or externally from a Content Delivery Network \(CDN\).

> Note:
> Loading OpenUI5 from a CDN improves your app performance: You can load from a server that \(in most cases\) is much closer to your location, and you can benefit from the caching mechanism and the language fallback logic.
> 
> 

***

### Specific Version

Check the available versions with the respective maintenance status at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html).

You can refer to a specific version by using a versioned URL as in the example below:

``` html
<script id="sap-ui-bootstrap"
    type="text/javascript"
    src="https://openui5.hana.ondemand.com/**1.42.6**/resources/sap-ui-core.js"
    data-sap-ui-theme="sap_belize"
    data-sap-ui-libs="sap.m"></script>


```

The first segment of the URL after the host name is used to specify a concrete version.

***

### Default Version

The default version of our libraries has the generic URL [https://openui5.hana.ondemand.com/resources/sap-ui-core.js](https://openui5.hana.ondemand.com/resources/sap-ui-core.js) \(OpenUI5\).

> Note:
> The default version is constantly being upgraded and this might have an impact on the stability of your application. Use this version for testing purposes only.
> 
> If you want to use the default version, you can use the following bootstrap script:
> 
> ``` html
> <script id="sap-ui-bootstrap"
>     type="text/javascript"
>     src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
>     data-sap-ui-theme="sap_belize"
>     data-sap-ui-libs="sap.m"></script>
> 
> ```
> 
> 

***

### Cache Control

The cache control is different for dynamic and static resources. If you refer to the latest maintenance version \(dynamic\), you have a maximum cache age of one week, if you refer to a specific \(static\) version, you have a maximum cache age of 10 years. In both cases, cross-origin resource sharing \(CORS\) headers are set, so that you can consume resources from the central location without any proxy in between.

> Note:
> The Cache Buster is only needed if you consume OpenUI5 without a concrete version in the URL. When you consume OpenUI5 with the concrete version in the URL, this is not needed, as the content served by that unique URLs will never change and can be cached forever.
> 
> 

**Related information**  


[Versioning of OpenUI5](Versioning_of_OpenUI5_91f0214.md)

