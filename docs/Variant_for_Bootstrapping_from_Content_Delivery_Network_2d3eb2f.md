<!-- loio2d3eb2f322ea4a82983c1c62a33ec4ae -->

| loio |
| -----|
| 2d3eb2f322ea4a82983c1c62a33ec4ae |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/2d3eb2f322ea4a82983c1c62a33ec4ae) | [demo kit latest release](https://sdk.openui5.org/topic/2d3eb2f322ea4a82983c1c62a33ec4ae)</div>

## Variant for Bootstrapping from Content Delivery Network

OpenUI5 can either be loaded locally with a relative path from a Web server or externally from a Content Delivery Network \(CDN\). 

> ### Note:  
> Loading OpenUI5 from a CDN improves your app performance: You can load from a server that \(in most cases\) is much closer to your location, and you can benefit from the caching mechanism and the language fallback logic.

***

<a name="loio2d3eb2f322ea4a82983c1c62a33ec4ae__section_CDN"/>

### Bootstrapping From OpenUI5 CDN

> ### Note:  
> To ensure outdated versions no longer pose a potential security risk, SAP removes OpenUI5 versions from the OpenUI5 CDN one year after their end of maintenance. Also patches of versions in maintenance which are older than one year will be removed. For more information, see [this blog post](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/). The end dates for the cloud provisioning of OpenUI5 versions and patches can be found at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html)

***

#### Specific Version

The specific version allows you to select a particular fixed version for bootstrapping. You can refer to a specific version by using a versioned URL as in the following example:

```html
<script id="sap-ui-bootstrap"
    type="text/javascript"
    src="https://sdk.openui5.org/[/pandoc/div/div/horizontalrule/horizontalrule/codeblock/strong/span
     {""}) 1.104.0 (span]/resources/sap-ui-core.js"
    data-sap-ui-theme="sap_fiori_3"
    data-sap-ui-async="true"
    data-sap-ui-libs="sap.m"></script>


```

The first segment of the URL after the host name is used to specify a concrete version, which needs to be provided in the following form: `release_number.version_number.patch_number`. For more information, see [Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md).

Check the available versions with the respective maintenance status at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html).

> ### Note:  
> Only use the *Stable* version for productive apps. Nevertheless, if you also want to test the [*Nightly*](https://openui5nightly.hana.ondemand.com) version, you are very welcome to send us your feedback!

***

#### Default Version

> ### Caution:  
> The default version is constantly being upgraded and this might have an impact on the stability of your application. Use this version for testing purposes only.
> 
> The default version of our libraries has the generic URL [https://sdk.openui5.org/resources/sap-ui-core.js](https://sdk.openui5.org/resources/sap-ui-core.js) \(OpenUI5\). If you want to use the default version, you can use the following bootstrap script:
> 
> ```html
> <script id="sap-ui-bootstrap"
>     type="text/javascript"
>     src="https://sdk.openui5.org/resources/sap-ui-core.js"
>     data-sap-ui-theme="sap_fiori_3"
>     data-sap-ui-async="true"
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

[Set Up a CDN for SAPUI5 on Your On-Premise SAP ABAP Server](https://blogs.sap.com/2021/08/17/set-up-a-cdn-for-sapui5-on-your-on-premise-sap-abap-server/)

[Versioning and Maintenance of OpenUI5](Versioning_and_Maintenance_of_OpenUI5_91f0214.md "Versioning and maintenance strategy for OpenUI5.")

