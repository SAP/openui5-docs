<!-- loio5deb78f36022473487be44cb3a71140a -->

| loio |
| -----|
| 5deb78f36022473487be44cb3a71140a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5deb78f36022473487be44cb3a71140a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5deb78f36022473487be44cb3a71140a)</div>

## What's New in OpenUI5 1.100

With this release OpenUI5 is upgraded from version 1.99 to 1.100.

***

<a name="loio5deb78f36022473487be44cb3a71140a__section_vvy_452_rrb"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
<th valign="top">

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Reminder: Outdated Versions to Be Removed from the CDN**

For security reasons, versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

***

<a name="loio5deb78f36022473487be44cb3a71140a__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**New Theme Flavors Available for SAP Fiori User Experience \(Experimental\)**

The new flavors for the preview version of the *Horizon* visual theme for SAP Fiori are now available \(theme IDs: `sap_horizon_dark`, `sap_horizon_hcb`, and `sap_horizon_hcw`\). In addition to *Morning Horizon*, which was introduced in an earlier release, we have now also provided *Evening Horizon*, *Horizon High Contrast Black*, and *Horizon High Contrast White*.

To preview the new theme flavors, see

-   [https://openui5.hana.ondemand.com/?sap-ui-theme=sap\_horizon\_dark\#/controls](https://openui5.hana.ondemand.com/?sap-ui-theme=sap_horizon_dark#/controls)

-   [https://openui5.hana.ondemand.com/?sap-ui-theme=sap\_horizon\_hcb\#/controls](https://openui5.hana.ondemand.com/?sap-ui-theme=sap_horizon_hcb#/controls)

-   [https://openui5.hana.ondemand.com/?sap-ui-theme=sap\_horizon\_hcw\#/controls](https://openui5.hana.ondemand.com/?sap-ui-theme=sap_horizon_hcw#/controls)


> ### Note:  
> The themes have the status 'experimental' and are thus subject to change. They must not be used as a basis for custom themes as long as the status is 'experimental'.



</td>
</tr>
</table>

***

<a name="loio5deb78f36022473487be44cb3a71140a__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

You can now access the status of a `Context` in bindings with the `@$ui5.context.isInactive` and `@$ui5.context.isTransient` instance annotations.For more information, see the [API Reference for `#isInactive`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.Context%23methods/isInactive) and the [API Reference for `#isTransient`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.Context%23methods/isTransient).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `sap.ui.model.odata.v4.ODataModel#getKeepAliveContext` method introduced with OpenUI5 1.99 also works if either no context exists in the identified list binding or if no list binding could be identified at all.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/getKeepAliveContext) and [Relative Bindings](Data_Reuse_648e360.md#loio648e360fa22d46248ca783dc6eb44531__section_relativeBindings).

-   You can now refresh a list binding with transient records.




</td>
</tr>
</table>

***

<a name="loio5deb78f36022473487be44cb3a71140a__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.QuickView`**

Тhe control now displays a language-dependent “–” symbol when the text for a value is empty. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.QuickView) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.QuickViewCard/sample/sap.m.sample.QuickViewCard).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Select`**

The `sap.m.Select` control has a new `liveChange` event that fires when the user navigates to a different item.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   The `showMessage` method is now \(experimentally\) available for all card types. It allows developers to display a message to the user. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/showMessage) in the Card Explorer.

-   We have introduced a new `initials` formatter, which creates initials from names. The default length of the returned initials is 2, but you can control it using the optional `length` property. For more information, see the [Initials Formatter](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters/initials) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/initials) in the Card Explorer.

-   We have added a new [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/encodeURIComponent) that demonstrates how you can use expression binding with `EncodeURIComponent` formatter. Expression binding also supports some of the native JS functions like `Array`, `Boolean`, `Date`, `Infinity`, `isFinite`, `isNaN`, `JSON`, `Math`, `NaN`, `Number`, `Object`, `parseFloat`, `parseInt`, `RegExp`, `String`, and `undefined`.




</td>
</tr>
</table>

***

<a name="loio5deb78f36022473487be44cb3a71140a__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

