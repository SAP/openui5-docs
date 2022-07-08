<!-- loiof01ebd44da544fa8824464447b896a5c -->

| loio |
| -----|
| f01ebd44da544fa8824464447b896a5c |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/f01ebd44da544fa8824464447b896a5c) | [demo kit latest release](https://sdk.openui5.org/topic/f01ebd44da544fa8824464447b896a5c)</div>

## What's New in OpenUI5 1.104

With this release OpenUI5 is upgraded from version 1.103 to 1.104.

***

<a name="loiof01ebd44da544fa8824464447b896a5c__section_yds_gcs_c5b"/>

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

<a name="loiof01ebd44da544fa8824464447b896a5c__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

<code><b>sap.m.Link</b></code>

We have provided a new API in the control, and now app developers can change the control's role to `button` when it's used for triggering a function.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Link). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have \(experimentally\) enabled the possibility for a shared JavaScript library to be used as an extension by multiple cards. As a card developer, you can set this extension via the manifest. For more information, see the [Card Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/sharedExtension) in the Card Explorer.

-   We have made the loading placeholders for Table and Object cards more detailed to better reveal the expected loading content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.LazyLoading).

-   We have \(experimentally\) introduced the possibility for ComboBox or TextArea form inputs to be used inside the Object card. Afterwards, you can process and submit the data provided with these form inputs to a back-end service. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/form) in the Card Explorer.

-   The Object card \(experimentally\) supports custom error message when there is empty data retrieved from the back end. To enable this feature, we have added a new `hasData` property inside the `content` section of the manifest. Card developers should set this property to point to a chosen data attribute. At runtime, if a condition is met, the corresponding illustrated message is displayed. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/errorMessages/object).




</td>
</tr>
</table>

***

<a name="loiof01ebd44da544fa8824464447b896a5c__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

