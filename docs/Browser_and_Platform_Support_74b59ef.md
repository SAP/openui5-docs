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
> We currently do not guarantee that newer ECMAScript standards, such as ES6/ES2015, work with OpenUI5.
> 
> 

Depending on the platform your OpenUI5 apps run on, different browsers in different versions are supported. If you know which platform and which browsers are used by your users, you can decide on which libraries to use for your app.

***

### Overview of Supported Browsers, Platforms, and Reference Devices

The following tables give a general overview of the browsers, platforms, and reference devices supported by the main OpenUI5 libraries.

***

#### Browser and Platform Support Matrix

> Note:
> OpenUI5 plans to end the support for Microsoft Internet Explorer 11 as future direction \(end of 2021 or later\).
> 
> 

|Platform|Device Category|Platform Version|Safari|Web View|Internet Explorer|Microsoft Edge|Google Chrome|Mozilla Firefox|SAP Fiori Client|
|--------|---------------|----------------|------|--------|-----------------|--------------|-------------|---------------|----------------|
|Windows|Desktop|Windows 7, 8.1|-|-|Version 11<sup>2</sup>|-|Latest version|Latest version and Extended Support Release \(ESR\)<sup>1</sup>|-|
|Windows 10|-|Latest version|Latest 2 versions|-|
|Touch<sup>3</sup>|Windows 10|-|Latest version|Version 11<sup>2</sup>|Latest 2 versions|Latest version|Latest version and Extended Support Release \(ESR\)|Latest version|
|macOS|Desktop|Latest 2 versions|Latest 2 versions|-|-|-|Latest version<sup>3</sup>|-|-|
|iOS|Phone and Tablet<sup>3</sup>|Latest 2 versions|Latest 2 versions|Latest version|-|-|-|-|Latest version|
|Android|Phone and Tablet<sup>3</sup>|As of version 5|-|-|-|-|Latest version|-|Latest version|

1\) In regards to handling touch events, there are some issues with Windows 8. For more information, see [Windows 8 Support - Known Issues](Windows_8_Support_-_Known_Issues_8168059.md).  
 2\) Internet Explorer 11 requires add-ons *XML DOM Document* and *XML DOM Document 3.0* to be activated for XML parsing support.  
 3\) Not supported for `sap.ui.commons` and `sap.ui.ux3`.  
 

***

#### Supported Reference Devices

For mobile operating systems, support is restricted to specific reference devices.

When creating support incidents, make sure that the device you refer to belongs to the listed ones:

> Note:
> Touch-enabled devices are not supported by the `sap.ui.commons` and `sap.ui.ux3` libraries.
> 
> 

|Platform|Device|End of Support Date|
|--------|------|-------------------|
|iOS SAP always supports the 2 latest releases of the iOS operating system, not exceeding 3 years from vendor release date. OpenUI5 supports Apple iPhone and iPad series until 3 years from the vendor device release date, except defined otherwise.|Apple iPhone 7|September 2019|
|Apple iPhone 8|September 2020|
|Apple iPhone X|November 2020|
|Apple iPhone XS|September 2021|
|Apple iPhone XR|October 2021|
|Apple iPad \(2017\)|March 2020|
|Apple iPad Pro \(2nd\)|June 2020|
|Apple iPad \(2018\)|March 2021|
|Apple iPad Pro \(3rd\)|October 2021|
|Android Android OS based devices are very fragmented in matters of operating system variants and hardware diversity. OpenUI5 supports Samsung Galaxy S and Galaxy Tab S series until 3 years from vendor device release date, except defined otherwise.|Samsung Galaxy S8, S8+|April 2020|
|Samsung Galaxy S9, S9+|March 2021|
|Samsung Galaxy S10, S10+, S10e|March 2022|
|Samsung Galaxy Tab S3|March 2020|
|Samsung Galaxy Tab S4|August 2021|
|Samsung Galaxy Tab S5e|February 2022|
|Windows OpenUI5 supports Microsoft Surface Pro reference devices until 3 years from vendor device release date, except defined otherwise.|Microsoft Surface Pro \(2017\)|June 2020|
|Microsoft Surface Pro with LTE Advanced|March 2021|
|Microsoft Surface Pro 6|October 2021|

***

### Additional Information

-   **General**

    -   Internet Explorer 11 \(IE11\) provides specific document and enterprise modes for compatibility reasons. OpenUI5 supports only the IE11 document mode. For backward compatibility, IE11 allows to enable a special enterprise mode that can simulate either an IE8 or IE7 within an IE11, which is NOT supported for OpenUI5 apps. This functionality should be used only for critical apps that require an older browser version to run. For more information, see "[Fix web compatibility issues using document modes and the Enterprise Mode site list](https://technet.microsoft.com/itpro/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)" in the Microsoft Windows IT Center.

    -   The PhantomJS browser is not supported. If you are using it for testing purposes, make sure that you use version 2.x or higher. Otherwise you may get an error message, such as "TypeError: 'undefined' is not a function \(evaluating 'f.bind\(null,undefined\)'\)\(line 146\)".

    -   `sap.ui.core`, `sap.ui.layout`, `sap.ui.unified` are basic libraries, supporting all platforms or browsers that are supported by any of the other libraries.

-   **`sap.m`**
    -   For the **maxLines** property of the `sap.m.Text` control, multiline ellipsis handling is not supported for all browsers and devices and is not supported at all for right-to-left text direction. For more information, see [Visual Degradations](Visual_Degradations_f08f296.md).

