<!-- loiob88b40e124634bb4897f36846f23cd12 -->

| loio |
| -----|
| b88b40e124634bb4897f36846f23cd12 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/b88b40e124634bb4897f36846f23cd12) | [demo kit latest release](https://sdk.openui5.org/topic/b88b40e124634bb4897f36846f23cd12)</div>

## What's New in OpenUI5 1.107

With this release OpenUI5 is upgraded from version 1.106 to 1.107.

***

<a name="loiob88b40e124634bb4897f36846f23cd12__section_tlr_g1x_z5b"/>

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
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Documentation now open for contributions on GitHub**

The documentation under [https://sdk.openui5.org/\#/topic](https://sdk.openui5.org/topic) is now also available on GitHub as Markdown files. Every documentation page in the Demo Kit has a direct link to the corrresponding Markdown file in the new [https://github.com/SAP-docs/sapui5](https://github.com/SAP-docs/sapui5) repository:![](images/loioe111aeba4f43463daec60af171842654_LowRes.png)

If you have any suggestions for improvements or if you spot an error, feel free to create an issue or a pull request there.

For more information, see [Open Documentation Initiative for SAPUI5 and SAP Fiori Elements – Help Us to Help You!](https://blogs.sap.com/?p=1579981)



</td>
<td valign="top">

1.107



</td>
</tr>
</table>

***

<a name="loiob88b40e124634bb4897f36846f23cd12__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

We now provide the `sap.ui.model.odata.v4.ODataModel#getServiceUrl`, `sap.ui.model.odata.v4.ODataModel#getKeyPredicate`, and`sap.ui.model.odata.v4.ODataModel#requestKeyPredicate` methods.For more information, see the API Reference for [`#getServiceUrl`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/getServiceUrl), [`#getKeyPredicate`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/getKeyPredicate), and [`#requestKeyPredicate`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/requestKeyPredicate).



</td>
</tr>
</table>

***

<a name="loiob88b40e124634bb4897f36846f23cd12__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

To improve performance, we have now made the initial rendering faster: Table, tree, and list items are now already created when the data is requested from the back end. When the data is received, the binding context is updated. This way, rendering the UI with the requested data becomes faster.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.upload.UploadSet`**

We've introduced directory \(folder\) uploads using the `UploadSet` control. It allows you to directly upload files from directories and subdirectories by configuring the directory property. You can also use the drag and drop feature to upload directories.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   The new \(experimental\) `titleMaxLines` and `subTitleMaxLines` properties enable you to limit the number of lines for the title and subtitle in both the Default and Numeric card headers. Additionally, with the new \(experimental\) `detailsMaxLines` property you can also limit the number of lines for the details in the Numeric card header. For more information, see the [Default Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/default) and [Numeric Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/numeric) sections in the Card Explorer.

-   You can now add items of type `Link` \(experimental\) in the `actionsStrip` of footers and list items. For more information, see the [Card Footer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/footer) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/footer) in the Card Explorer.

-   All icons now have a new `initials` property, which is used as a fallback if the `src` property is not set or there is an issue with the resource. For more information, see the [List Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/list) section in the Card Explorer.

-   You can now configure the visibility of card headers using the new `visible` Boolean property. Card developers can set this property in the manifest. Additionally, they can add it to the `Configuration.js`, which will also enable card administrators, who are using the Configuration editor, to control the visibility of the card header. For more information, see the [Default Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/default) and [Numeric Header](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/numeric) sections and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/designtimeAdmin) in the Card Explorer.

-   We have added a new \(experimental\) `stateChanged` event that is fired when the state of the card is changed. For example, when the card is initialized, a new page inside the card is selected, a filter is changed, or data is refreshed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card).




</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageSection`**

We have added a new `wrapTitle` property. It allows long titles to wrap into multiple lines. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageSection).



</td>
</tr>
</table>

***

<a name="loiob88b40e124634bb4897f36846f23cd12__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

***

<a name="loiob88b40e124634bb4897f36846f23cd12__section_r5v_3h5_zcb"/>

### Demo Kit Improvements and Documentation


<table>
<tr>
<td valign="top">

***Edit on GitHub* Button**

We have enabled external collaboration for our documentation through `github.com`. You can now contribute to our content through pull requests or by asking for enhancements by opening GitHub issues.

![](images/loiod5a8a29abd5740a3b2d752053a023424_LowRes.png)



</td>
</tr>
</table>

