<!-- loio74b59efa0eef48988d3b716bd0ecc933 -->

| loio |
| -----|
| 74b59efa0eef48988d3b716bd0ecc933 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/74b59efa0eef48988d3b716bd0ecc933) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/74b59efa0eef48988d3b716bd0ecc933)</div>

## Browser and Platform Support

Browser and platform support for the OpenUI5 libraries on iOS, Android, macOS, and Windows platforms.

As OpenUI5 is based on CSS3, HTML5, and the ECMAScript 5 \(ES5\) JavaScript API, only browsers with HTML5 capabilities are supported. In general, only major versions that are also supported by the respective platform can be supported by the OpenUI5 framework.

> Note:
> We currently do not guarantee that ECMAScript standards ES6/ES2015 or newer, work with OpenUI5.
> 
> 

Depending on the platform your OpenUI5 apps run on, different browsers in different versions are supported. If you know which platform and which browsers are used by your users, you can decide on which libraries to use for your app.

***

### Overview of Supported Browsers, Platforms, and Reference Devices

The following tables give a general overview of the browsers, platforms, and reference devices supported by the main OpenUI5 libraries.

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__section_bgw_kns_hnb"/>

### Browser and Platform Support Matrix

|Platform|Device Category|Platform Version|Safari|Web View|Internet Explorer<sup>2</sup>|Microsoft Edge \(Chromium\)<sup>3</sup>|Google Chrome|Mozilla Firefox|SAP Fiori Client|
|--------|---------------|----------------|------|--------|-----------------------------|---------------------------------------|-------------|---------------|----------------|
|Windows<sup>1</sup>|Desktop|Windows 8.1|-|-|Version 11<sup>4</sup>|Latest version|Latest version|Latest version and Extended Support Release \(ESR\)|-|
|Windows 10|-|Latest version|-|
|Touch<sup>5</sup>|Windows 10|-|Latest version|Version 11<sup>4</sup>|Latest version|Latest version|Latest version|
|macOS|Desktop|Latest 2 versions|Latest 2 versions|-|-|-|Latest version<sup>5</sup>|-|-|
|iOS|Phone and Tablet<sup>5</sup>|Latest 2 versions|Latest 2 versions|Latest version|-|-|-|-|Latest version|
|Android|Phone and Tablet<sup>5</sup>|As of version 5|-|-|-|-|Latest version|-|Latest version|

1\) The specified browsers are also supported in virtual environments, such as Citrix and VMware. Any issues found must be reproducible in a non-virtualized environment.  
 2\) For the upcoming end of support for Microsoft Internet Explorer 11 in OpenUI5, see section [End of Support for Microsoft Internet Explorer 11 in Future OpenUI5 Versions](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).  
 3\) OpenUI5 detects Microsoft Edge \(Chromium\) as Google Chrome and treats it the same.  
 4\) Internet Explorer 11 requires add-ons *XML DOM Document* and *XML DOM Document 3.0* to be activated for XML parsing support.  
 5\) Not supported for `sap.ui.commons` and `sap.ui.ux3`.  
 

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__MS_IE"/>

### End of Support for Microsoft Internet Explorer 11 in Future OpenUI5 Versions

OpenUI5 1.87 will be the last version that still supports Microsoft Internet Explorer 11 \(IE11\). The last long-term maintenance version of OpenUI5 that supports IE11 is OpenUI5 1.84. All OpenUI5 versions up to and including OpenUI5 1.87 will continue to support IE11 as long as they are in maintenance.

In case you have legacy applications and you still need IE11 with an OpenUI5 version that no longer supports it, we recommend that you either use a dual browser strategy \(for example, your users use another supported browser in addition to IE11\) or you switch to Microsoft Edge \(Chromium\), which has an integrated Internet Explorer runtime mode.

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__section_n3t_dns_hnb"/>

### Supported Reference Devices on iOS and Android

For mobile operating systems, support is restricted to specific reference devices.

When creating support incidents, make sure that the device you refer to belongs to the listed ones:

|Platform|Device|End of Support Date|
|--------|------|-------------------|
|iOS SAP always supports the 2 latest releases of the iOS operating system, not exceeding 3 years from vendor release date. OpenUI5 supports Apple iPhone and iPad series until 3 years from the vendor device release date, except defined otherwise.|Apple iPhone XS|September 2021|
|Apple iPhone XR|October 2021|
|Apple iPhone 11|September 2022|
|Apple iPhone SE \(2nd\)|April 2023|
|Apple iPhone 12|October 2023|
|Apple iPad \(6th\)|March 2021|
|Apple iPad Pro \(3rd\)|October 2021|
|Apple iPad Air \(3rd\)|March 2022|
|Apple iPad Mini \(5th\)|March 2022|
|Apple iPad \(7th\)|September 2022|
|Apple iPad Pro \(4th\)|March 2023|
|Apple iPad \(8th\)|September 2023|
|Apple iPad Air \(4th\)|October 2023|
|Android Android OS based devices are very fragmented in matters of operating system variants and hardware diversity. OpenUI5 supports Samsung Galaxy S and Galaxy Tab S series until 3 years from vendor device release date, except defined otherwise.|Samsung Galaxy S9|March 2021|
|Samsung Galaxy S10|March 2022|
|Samsung Galaxy S20|March 2023|
|Samsung Galaxy Tab S4|August 2021|
|Samsung Galaxy Tab S5e|April 2022|
|Samsung Galaxy Tab S6|August 2022|
|Samsung Galaxy Tab S6 Lite|July 2023|
|Samsung Galaxy Tab S7|August 2023|

***

### Additional Information

-   **General**

    -   Internet Explorer 11 \(IE11\) provides specific document and enterprise modes for compatibility reasons. OpenUI5 supports only the IE11 document mode. For backward compatibility, IE11 allows to enable a special enterprise mode that can simulate either an IE8 or IE7 within an IE11, which is NOT supported for OpenUI5 apps. This functionality should be used only for critical apps that require an older browser version to run. For more information, see "[Fix web compatibility issues using document modes and the Enterprise Mode site list](https://technet.microsoft.com/itpro/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)" in the Microsoft Windows IT Center.

    -   Microsoft Edge \(EdgeHTML\) is not supported.

    -   PhantomJS is not supported.

-   **`sap.m`**
    -   For the **maxLines** property of the `sap.m.Text` control, multiline ellipsis handling is not supported for all browsers and devices and is not supported at all for right-to-left text direction. For more information, see [Visual Degradations](Visual_Degradations_f08f296.md).

