<!-- loio34afc69bf9194d43a9f49042825bb199 -->

| loio |
| -----|
| 34afc69bf9194d43a9f49042825bb199 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/34afc69bf9194d43a9f49042825bb199) | [demo kit latest release](https://sdk.openui5.org/topic/34afc69bf9194d43a9f49042825bb199)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.112

With this release OpenUI5 is upgraded from version 1.111 to 1.112.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

** **


<table>
<tr>
<th valign="top">

Version



</th>
<th valign="top">

Type



</th>
<th valign="top">

Category



</th>
<th valign="top">

Title



</th>
<th valign="top">

Description



</th>
<th valign="top">

Action



</th>
<th valign="top">

Available as of



</th>
</tr>
<tr>
<td valign="top">

 Upcoming 



</td>
<td valign="top">

 Deleted 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **End of Cloud Provisioning for Versions \(Q1/2023\).** 



</td>
<td valign="top">

**End of Cloud Provisioning for Versions \(Q1/2023\)**

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.90
-   1.93
-   1.97
-   1.98

Action: Upgrade to a version that’s still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.53 to 1.38.55
    -   1.71.44 to 1.71.46
    -   1.84.21 to 1.84.23
    -   1.96.2 to 1.96.7

    Action: Upgrade to the latest available patch for the respective SAPUI5 version.


For more information, see [UI5 Releases Ending Service in 2023](https://blogs.sap.com/2022/12/05/ui5-releases-ending-service-in-2023/) and [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Info Only•Upcoming</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-03-31



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **What's New Viewer for OpenUI5** 



</td>
<td valign="top">

**What's New Viewer for OpenUI5**

Due to some issues with references to OpenUI5 content we had to remove the What's New viewer for OpenUI5. The What's New viewer is therefore only available in SAPUI5. For more information, see [Want to Know What’s New in SAPUI5 and SAP Fiori Elements? Check the What’s New Viewer!](https://blogs.sap.com/?p=1702680).

<sub>Changed•Announcement•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Input`, `sap.m.ComboBox`, `sap.m.MultiComboBox`** 



</td>
<td valign="top">

**`sap.m.Input`, `sap.m.ComboBox`, `sap.m.MultiComboBox`**

We have removed the experimental flag for the `showItems(fnFilter)` method. For more information, see the [`sap.m.Input`API Reference](https://sdk.openui5.org/api/sap.m.Input/methods/showItems) and [`sap.m.ComboBoxBase`API Reference](https://sdk.openui5.org/api/sap.m.ComboBoxBase/methods/showItems).

<sub>Changed•Control•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.IllustratedMessage`** 



</td>
<td valign="top">

**`sap.m.IllustratedMessage`**

-   We have added a new sample that demonstrates how to use `sap.m.IllustratedMessage` with an external illustration set. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.IllustratedMessage/sample/sap.m.sample.IllustratedMessageInPageCustom).

-   We have added a new `ariaTitleLevel` property. It allows setting custom aria-level values to the title in `sap.m.IllustratedMessage`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage). 

<sub>Changed•Control•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.MessagePage`** 



</td>
<td valign="top">

**`sap.m.MessagePage`**

We have deprecated the `sap.m.MessagePage`, and recommend using the `sap.m.IllustratedMessage` instead.

<sub>Deprecated•Control•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have \(experimentally\) introduced two new `ShowCard` and `HideCard` actions that enable you, from one card, to open another card that shows more details or actions. The `ShowCard` action opens a dialog with the new card, which is created by a given manifest. The `HideCard` action closes this dialog. For more information, see the [Show Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/actions/showCard) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/cardActions/showHideCard) in the Card Explorer.

-   We have \(experimentally\) enhanced the Object card and now it also supports `Image` and `Input` as content types. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Samples](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/formWithValidation) in the Card Explorer.

-   We have added a new \(experimental\) `previewMode` property that can be used when the end user is exploring, selecting, or configuring cards. It depends on the host environment to trigger the card rendering into the required preview mode. The available options for the host developers are:

    -   `Off` \(default\) - live data is displayed.
    -   `MockData` - the card shows mock data, loaded using a data request. The card developer should set the data source in the `data/mockData` part of the manifest.
    -   `Abstract` - the card shows an abstract placeholder without loading data.

     For more information, see the [Integrate/Preview](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/preview) section and the [Samples](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/preview) in the Card Explorer. 

-   The date range filter now supports several new options: `dateTimeRange`, `fromDateTime`, `toDateTime`, and `dateTime`. For more information, see the [Date Range Filter](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/dateRange) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/dateRangeFilter/agenda) in the Card Explorer.

<sub>Changed•Control•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
<tr>
<td valign="top">

 1.112 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

Feature



</td>
<td valign="top">

 **OpenUI5 OData V4 Model** 



</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now provide Deep Create in a first version as an experimental feature. You can use a transient context as the binding context of a list binding and call `sap.ui.model.odata.v4.ODataListBinding#create` on that dependent list binding. Note that the Deep Create feature is currently neither complete nor intended for productive use.
-   The experimental hierarchy feature introduced with OpenUI5 1.105 now works if the hierarchy properties announced by the [Org.OData.Aggregation.V1.RecursiveHierarchy](https://oasis-tcs.github.io/odata-vocabularies/vocabularies/Org.OData.Aggregation.V1.html#RecursiveHierarchy) and [com.sap.vocabularies.Hierarchy.v1.RecursiveHierarchy](https://github.com/SAP/odata-vocabularies/blob/main/vocabularies/Hierarchy.md) annotations are part of a property of the complex type.
-   You can now specify `$$sharedRequest:false` for list bindings. This is helpful for list bindings of separate value list models, as `$$sharedRequest` defaults to `true` for these bindings.

<sub>Changed•Feature•Info Only•1.112</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-03-23



</td>
</tr>
</table>

