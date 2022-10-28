<!-- loio799291a4be7542c9a0a96ba425d0dec2 -->

| loio |
| -----|
| 799291a4be7542c9a0a96ba425d0dec2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/799291a4be7542c9a0a96ba425d0dec2) | [demo kit latest release](https://sdk.openui5.org/topic/799291a4be7542c9a0a96ba425d0dec2)</div>

## What's New in OpenUI5 1.108

With this release OpenUI5 is upgraded from version 1.107 to 1.108.

***

<a name="loio799291a4be7542c9a0a96ba425d0dec2__section_pzq_t5d_s5b"/>

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

**Reminder: Outdated OpenUI5 Versions to Be Removed from the CDN**

For security reasons, OpenUI5 versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

***

<a name="loio799291a4be7542c9a0a96ba425d0dec2__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**Replacement for `jQuery.fn.control`**

To become more independent from specific jQuery functionality, we now provide the new `sap.ui.core.Element#closestTo` method as a replacement for the `jQuery.fn.control` extension function, which is commonly used to retrieve the nearest OpenUI5 control that wraps a given DOM element. The new method returns a single OpenUI5 element instead of the array of OpenUI5 elements returned by `jQuery.fn.control`. You might therefore need to add an outer loop when migrating your code to the new API.

For more information, see [Legacy jQuery.sap Replacement](Legacy_jQuery_sap_Replacement_a075ed8.md)and the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Element/methods/sap.ui.core.Element.closestTo).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   We now support "deep create" requests for navigation properties of cardinality "many". For more information, see [Deep Create](OData_V2_Model_6c47b2b.md#loio4c4cd99af9b14e08bb72470cc7cabff4__section_DCR).
-   We now provide the new `sap.ui.model.ClientTreeBinding#getCount` method.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.ClientTreeBinding/methods/getCount).
-   When you use an `sap.ui.model.type.Currency`, `sap.ui.model.odata.type.Currency`, or the currency instance of `sap.ui.core.format.NumberFormat`, entered currency codes are now parsed case-insensitively where possible.
-   We have introduced the new `calendarWeekNumbering` format option for `sap.ui.core.format.DateFormat`.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now provide "deferred delete" requests: You can call the `sap.ui.model.odata.v4.Context#delete` method with an API group; the back-end request is then only sent when `ODataModel#submitBatch` is called for this API group. For more information, see [Deleting an Entity](Deleting_an_Entity_2613ebc.md).
-   We have improved our documentation of how to overwrite value list annotations in local annotation files. For more information, see [Value Lists](Value_Lists_ab267a6.md).
-   The `dataRequested` and `dataReceived` events introduced with OpenUI5 1.106 for the `sap.ui.model.odata.v4.ODataModel` now provide the path for additional property requests.For more information, see the API Reference for [`ODataModel.dataReceived`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/events/dataReceived) and [`ODataModel.dataRequested`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/events/dataRequested).



</td>
</tr>
</table>

***

<a name="loio799291a4be7542c9a0a96ba425d0dec2__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Avatar`**

Up to three Latin letters can be displayed as initials in a `sap.m.Avatar`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Avatar) and the [Sample](https://sdk.openui5.org/entity/sap.m.Avatar/sample/sap.m.sample.Avatar). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Carousel`**

We have improved the keyboard interaction and accessibility of the control. The initial focus is now on the active carousel item, unlike before, when it was on the carousel container. This allows you to focus on a concrete item and provides more information to the screen readers.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithMorePages).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IllustratedMessage`**

We have introduced a new illustration breakpoint variant `Dot`, suitable for spaces that don't have a lot of vertical space. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessageSize).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   The Adaptive card now uses the recently released 1.7.0 UI5 WebComponents bundle. For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesOther/adaptive) Learn section in the Card Explorer.

-   You can now configure the visibility of the card footer using the new `visible` boolean property. Card developers can set this property in the manifest. Additionally, they can add it to the `Configuration.js`, which will also enable card administrators, who are using the Configuration editor, to control the visibility of the card footer. For more information, see the [Card Footer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/footer) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/footer/hiddenFooter) in the Card Explorer.

-   We have made the loading placeholder for Analytical cards more detailed to better reveal the expected loading content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.LazyLoading).

-   We have \(experimentally\) enhanced the `sap.ui.integration.Extension` with a new `loadDependencies` lifecycle hook. As a card developer, you can use it to load critical dependencies for your extension, without which the data cannot be displayed. While the dependencies are loaded, the card displays a loading animation. This hook is asynchronous, so other tasks won’t be blocked. For more information, see the [Card Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/loadDependencies) in the Card Explorer, and the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.Extension).

-   A new `visible` property is now introduced for icons and avatars to achieve consistency in representation if an empty value for the `src` property is used in the card manifest. The new property is available for:

    -   Default Header
    -   Sap.f.CardHeader
    -   ObjectContent
    -   TableContent
    -   List Content

     For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/iconVisibility) in the Card Explorer. 




</td>
</tr>
</table>

***

<a name="loio799291a4be7542c9a0a96ba425d0dec2__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

***

<a name="loio799291a4be7542c9a0a96ba425d0dec2__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**TypeScript Demo App**

A new `TypeScript To-Do List` demo app is now available in both the Demo Apps and the Samples sections of the Demo Kit. For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.sample.TsTodos).



</td>
</tr>
</table>

