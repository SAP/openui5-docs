<!-- loio74b59efa0eef48988d3b716bd0ecc933 -->

| loio |
| -----|
| 74b59efa0eef48988d3b716bd0ecc933 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/74b59efa0eef48988d3b716bd0ecc933) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/74b59efa0eef48988d3b716bd0ecc933)</div>

## Browser and Platform Support

Browser and platform support for the OpenUI5 libraries on iOS, Android, macOS, and Windows platforms.

As OpenUI5 is based on CSS3, HTML5, and the ECMAScript 5 \(ES5\) JavaScript API, only browsers with HTML5 capabilities are supported. In general, only major versions that are also supported by the respective platform can be supported by the OpenUI5 framework.

> ### Restriction:  
> We currently do not guarantee that ECMAScript standards ES6/ES2015 or newer, work with OpenUI5.

Depending on the platform your OpenUI5 apps run on, different browsers in different versions are supported. If you know which platform and which browsers are used by your users, you can decide on which libraries to use for your app.

***

### Overview of Supported Browsers, Platforms, and Reference Devices

The following tables give a general overview of the browsers, platforms, and reference devices supported by the main OpenUI5 libraries. There are certain known device-browser combinations that lead to visual degradations. For more information, see [Visual Degradations](Visual_Degradations_f08f296.md).

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__section_bgw_kns_hnb"/>

### Browser and Platform Support Matrix


<table>
<tr>
<th valign="top">

Platform



</th>
<th valign="top">

Device Category



</th>
<th valign="top">

Platform Version



</th>
<th valign="top">

Safari



</th>
<th valign="top">

Web View



</th>
<th valign="top">

Microsoft Edge \(Chromium\)<sup>2</sup>



</th>
<th valign="top">

Google Chrome



</th>
<th valign="top">

Mozilla Firefox



</th>
<th valign="top">

SAP Fiori Client



</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Windows<sup>1</sup>



</td>
<td valign="top" rowspan="2">

Desktop



</td>
<td valign="top">

Windows 8.1



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top" rowspan="2">

Latest version



</td>
<td valign="top" rowspan="2">

Latest version



</td>
<td valign="top" rowspan="3">

Latest version and latest Extended Support Release \(ESR\)



</td>
<td valign="top">

-



</td>
</tr>
<tr>
<td valign="top">

Windows 10



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

-



</td>
</tr>
<tr>
<td valign="top">

Touch<sup>3</sup>



</td>
<td valign="top">

Windows 10



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

Latest version



</td>
</tr>
<tr>
<td valign="top">

macOS



</td>
<td valign="top">

Desktop



</td>
<td valign="top">

Latest 2 versions



</td>
<td valign="top">

Latest 2 versions



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version<sup>3</sup>



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
</tr>
<tr>
<td valign="top">

iOS



</td>
<td valign="top">

Phone and Tablet<sup>3</sup>



</td>
<td valign="top">

Latest 2 versions



</td>
<td valign="top">

Latest 2 versions



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version



</td>
</tr>
<tr>
<td valign="top">

Android



</td>
<td valign="top">

Phone and Tablet<sup>3</sup>



</td>
<td valign="top">

As of version 5



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version



</td>
<td valign="top">

-



</td>
<td valign="top">

Latest version



</td>
</tr>
</table>

1\) The specified browsers are also supported in virtual environments, such as Citrix and VMware. Any issues found must be reproducible in a non-virtualized environment.  
 2\) OpenUI5 detects Microsoft Edge \(Chromium\) as Google Chrome and treats it the same.  
 3\) Not supported for `sap.ui.commons` and `sap.ui.ux3`.  
 

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__MS_IE"/>

### OpenUI5 Support Status for Microsoft Internet Explorer 11

Support for Microsoft Internet Explorer 11 \(IE11\) ended after OpenUI5 1.87. The last long-term maintenance version of OpenUI5 that supports IE11 is OpenUI5 1.84. Versions up to and including OpenUI5 1.87 will continue to support IE11 as long as they are in maintenance \(see [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html)\).

In case you have legacy applications and you still need IE11 with an OpenUI5 version that no longer supports it, we recommend that you either use a dual browser strategy \(for example, your users use another supported browser in addition to IE11\) or you switch to Microsoft Edge \(Chromium\), which has an integrated Internet Explorer runtime mode.

***

<a name="loio74b59efa0eef48988d3b716bd0ecc933__section_n3t_dns_hnb"/>

### Supported Reference Devices on iOS and Android

For mobile operating systems, support is restricted to specific reference devices.

When creating support incidents, make sure that the device you refer to belongs to the listed ones:


<table>
<tr>
<th valign="top">

Platform



</th>
<th valign="top">

Device



</th>
<th valign="top">

End of Support Date



</th>
</tr>
<tr>
<td valign="top" rowspan="13">

iOS

SAP always supports the 2 latest releases of the iOS operating system, not exceeding 3 years from vendor release date. OpenUI5 supports Apple iPhone and iPad series until 3 years from the vendor device release date, except defined otherwise.



</td>
<td valign="top">

Apple iPhone XS



</td>
<td valign="top">

September 2021



</td>
</tr>
<tr>
<td valign="top">

Apple iPhone XR



</td>
<td valign="top">

October 2021



</td>
</tr>
<tr>
<td valign="top">

Apple iPhone 11



</td>
<td valign="top">

September 2022



</td>
</tr>
<tr>
<td valign="top">

Apple iPhone SE \(2nd\)



</td>
<td valign="top">

April 2023



</td>
</tr>
<tr>
<td valign="top">

Apple iPhone 12



</td>
<td valign="top">

October 2023



</td>
</tr>
<tr>
<td valign="top">

Apple iPad \(6th\)



</td>
<td valign="top">

March 2021



</td>
</tr>
<tr>
<td valign="top">

Apple iPad Pro \(3rd\)



</td>
<td valign="top">

October 2021



</td>
</tr>
<tr>
<td valign="top">

Apple iPad Air \(3rd\)



</td>
<td valign="top">

March 2022



</td>
</tr>
<tr>
<td valign="top">

Apple iPad Mini \(5th\)



</td>
<td valign="top">

March 2022



</td>
</tr>
<tr>
<td valign="top">

Apple iPad \(7th\)



</td>
<td valign="top">

September 2022



</td>
</tr>
<tr>
<td valign="top">

Apple iPad Pro \(4th\)



</td>
<td valign="top">

March 2023



</td>
</tr>
<tr>
<td valign="top">

Apple iPad \(8th\)



</td>
<td valign="top">

September 2023



</td>
</tr>
<tr>
<td valign="top">

Apple iPad Air \(4th\)



</td>
<td valign="top">

October 2023



</td>
</tr>
<tr>
<td valign="top" rowspan="8">

Android

Android OS based devices are very fragmented in matters of operating system variants and hardware diversity. OpenUI5 supports Samsung Galaxy S and Galaxy Tab S series until 3 years from vendor device release date, except defined otherwise.



</td>
<td valign="top">

Samsung Galaxy S9



</td>
<td valign="top">

March 2021



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy S10



</td>
<td valign="top">

March 2022



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy S20



</td>
<td valign="top">

March 2023



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy Tab S4



</td>
<td valign="top">

August 2021



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy Tab S5e



</td>
<td valign="top">

April 2022



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy Tab S6



</td>
<td valign="top">

August 2022



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy Tab S6 Lite



</td>
<td valign="top">

July 2023



</td>
</tr>
<tr>
<td valign="top">

Samsung Galaxy Tab S7



</td>
<td valign="top">

August 2023



</td>
</tr>
</table>

-   **[Visual Degradations](Visual_Degradations_f08f296.md "Depending on the combination of device and browser, visual degradations may occur in
		certain libraries.")**  
Depending on the combination of device and browser, visual degradations may occur in certain libraries.
-   **[Keyboard Shortcuts for OpenUI5 Tools](Keyboard_Shortcuts_for_OpenUI5_Tools_154844c.md "OpenUI5 provides tools for information, diagnostics and testing purposes that
		are accessible via keyboard shortcuts.")**  
OpenUI5 provides tools for information, diagnostics and testing purposes that are accessible via keyboard shortcuts.

