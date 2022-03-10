<!-- loio2d3eb2f322ea4a82983c1c62a33ec4ae -->

| loio |
| -----|
| 2d3eb2f322ea4a82983c1c62a33ec4ae |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae)</div>

## Variant for Bootstrapping from Content Delivery Network

OpenUI5 can either be loaded locally with a relative path from a Web server or externally from a Content Delivery Network \(CDN\). 

> ### Note:  
> Loading OpenUI5 from a CDN improves your app performance: You can load from a server that \(in most cases\) is much closer to your location, and you can benefit from the caching mechanism and the language fallback logic.

***

<a name="loio2d3eb2f322ea4a82983c1c62a33ec4ae__section_ekc_ct3_vjb"/>

### Bootstrapping From OpenUI5 CDN

***

#### Specific Version

Check the available versions with the respective maintenance status at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html). You can refer to a specific version by using a versioned URL as in the example below:

```html
<script id="sap-ui-bootstrap"
    type="text/javascript"
    src="https://openui5.hana.ondemand.com/[/pandoc/div/div/horizontalrule/horizontalrule/codeblock/strong/span
     {""}) 1.101.0 (span]/resources/sap-ui-core.js"
    data-sap-ui-theme="sap_belize"
    data-sap-ui-libs="sap.m"></script>


```

The first segment of the URL after the host name is used to specify a concrete version, which needs to be provided in the following form: `release_number.version_number.patch_number`. For more information, see [Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md).

> ### Note:  
> Only use the *Stable* version for productive apps. Nevertheless, if you also want to test the [*Nightly*](https://openui5nightly.hana.ondemand.com) version, you are very welcome to send us your feedback!

***

#### Evergreen Version

The evergreen version allows for a bootstrapping process that automatically uses the latest available patch level. You refer to a major.minor long-term maintenance version using a versioned URL as in the following example:

```html
<script id="sap-ui-bootstrap"
    type="text/javascript"
    src="https://openui5.hana.ondemand.com/[/pandoc/div/div/horizontalrule/horizontalrule/codeblock/strong/span
     {""}) 1.101 (span]/resources/sap-ui-core.js"
    data-sap-ui-theme="sap_fiori_3"
    data-sap-ui-async="true"
    data-sap-ui-libs="sap.m"></script>


```

The first segment of the URL after the host name is used to specify an evergreen version, which needs to be provided in the following form: `release_number.version_number`. For more information, see [Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md).

Evergreen versions only support asynchronous bootstrapping. Therefore, the `data-sap-ui-async` bootstrap attribute must be set to `true`.

You can find the available versions with long-term maintenance status at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html).

All long-term maintenance versions \>= 1.71 can be used as evergreen versions to bootstrap OpenUI5 applications.

***

#### Default Version

> ### Caution:  
> The default version is constantly being upgraded and this might have an impact on the stability of your application. Use this version for testing purposes only.
> 
> The default version of our libraries has the generic URL [https://openui5.hana.ondemand.com/resources/sap-ui-core.js](https://openui5.hana.ondemand.com/resources/sap-ui-core.js) \(OpenUI5\). If you want to use the default version, you can use the following bootstrap script:
> 
> ```html
> <script id="sap-ui-bootstrap"
>     type="text/javascript"
>     src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
>     data-sap-ui-theme="sap_belize"
>     data-sap-ui-libs="sap.m"></script>
> 
> ```

***

#### Cache Control

The cache control is different for dynamic and static resources. If you refer to the latest maintenance version \(dynamic\), you have a maximum cache age of one week, if you refer to a specific \(static\) version, you have a maximum cache age of 10 years. In both cases, cross-origin resource sharing \(CORS\) headers are set, so that you can consume resources from the central location without any proxy in between.

> ### Note:  
> The Cache Buster is only needed if you consume OpenUI5 without a concrete version in the URL. When you consume OpenUI5 with the concrete version in the URL, this is not needed, as the content served by that unique URLs will never change and can be cached forever.

**Related Information**  


[Multi-Version Availability of SAPUI5](https://blogs.sap.com/2015/07/30/multi-version-availability-of-sapui5)

[Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md "Versioning and maintenance strategy for OpenUI5.")

