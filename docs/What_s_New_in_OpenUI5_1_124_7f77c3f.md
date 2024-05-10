<!-- loio7f77c3f5ccf4497b9746488318e087cc -->

| loio |
| -----|
| 7f77c3f5ccf4497b9746488318e087cc |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/7f77c3f5ccf4497b9746488318e087cc) | [demo kit latest release](https://sdk.openui5.org/topic/7f77c3f5ccf4497b9746488318e087cc)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.124

With this release OpenUI5 is upgraded from version 1.123 to 1.124.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

****


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

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2024\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2024\)**

> ### Note:  
> The following information concerns important upcoming changes for end users. These changes may require end users to adjust and/or test cases to be adapted, but they won't stop or disrupt software or processes.

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q2/2024.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.111
-   1.112
-   1.113
-   1.115

**Action**: Upgrade to a version that is still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.61
    -   1.71.55-1.71.56
    -   1.84.32 to 1.84.35
    -   1.96.18 to 1.96.20
    -   1.108.7 to 1.108.14

    **Action**: Upgrade to the latest available patch for the respective OpenUI5 version.


For more information, see [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Info Only•Upcoming</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

9999-01-01

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Deprecations** 

</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature

</td>
<td valign="top">

**`sap.m.plugins.CellSelector`** 

</td>
<td valign="top">

**`sap.m.plugins.CellSelector`**

-   The `sap.m.plugins.CellSelector` plugin is no longer experimental. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector).

-   We have made the `getSelection` function public. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector%23methods/getSelection).


<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Decoupling of `sap_bluecrystal` Theme** 

</td>
<td valign="top">

**Decoupling of `sap_bluecrystal` Theme**

The `sap_bluecrystal` theme has now been decoupled from the base theme so that changes of the base theme CSS do not affect the theme any longer.

<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Table`** 

</td>
<td valign="top">

**`sap.m.Table`**

You can now use `sap.m.plugins.CellSelector` for cell selection in a responsive table. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector) and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TableSelectCopy).

<sub>Changed•Control•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` ** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` **

We have extended the `MultiSelectionPlugin`: If the number of selected rows is smaller than the set limit of rows, all these rows can be selected at once with a single operation. If there are more rows than the set limit, the first x rows are selected until the limit x has been reached. Now a *Complete* icon is shown to indicate that all rows have been selected. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.plugins.MultiSelectionPlugin%23methods/setLimit) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).

<sub>Changed•Control•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.mdc` library** 

</td>
<td valign="top">

**`sap.ui.mdc` library**

The library is now no longer experimental. To demonstrate the features of the controls in this library, we have also added more samples in the Demo Kit.

> ### Note:  
> The `Chart` control is still experimental.

For more information, see [sap.ui.mdc](sap_ui_mdc_1dd2aa9.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc), and the [Samples](https://sdk.openui5.org/entity/sap.ui.mdc). 

<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

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

We have \(experimentally\) introduced a new `data-help-id` attribute that you can use to connect the card with an end-user help system. Its default value is equal to the `sap.app/id` from the card's manifest. For more information, see the [Help ID](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/helpId) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**TypeScript** 

</td>
<td valign="top">

**TypeScript**

You can now use the*dts-generator* tool to generate TypeScript type definitions for any custom OpenUI5 library written in JavaScript. This is the same tool that is used for generating the productive type definitions for OpenUI5 and all its libraries.

For more information, see the [GitHub repo](https://github.com/SAP/ui5-typescript/tree/main/packages/dts-generator) and the [npm package](https://www.npmjs.com/package/@ui5/dts-generator).

<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

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

-   You can now use the experimental feature of moving nodes of a recursive hierarchy using`sap.ui.model.odata.v4.Context#move` with any initial expansion state of the hierarchy. An expansion state can be provided via the `expandTo` property of either the `$$aggregation` binding parameter or the `sap.ui.model.odata.v4.ODataListBinding#setAggregation` API.

    For more information, see the API Reference for [`v4.Context#move`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/move), [`v4.ODataModel#bindList`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel%23methods/bindList), and [`v4.ODataListBinding#setAggregation`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/setAggregation).

-   If you move a node with the experimental `sap.ui.model.odata.v4.Context#move` API and the moved node has siblings, it is now shown by default at a position assigned by the back end. Alternatively, you now have the option of moving the node to a position before a specified sibling or to the last position among its siblings.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/move).

-   The tree state is now kept when sorting or filtering a recursive hierarchy.

-   We have introduced the new `$$clearSelectionOnFilter` list binding parameter. When a filter or search is changed, it allows you to automatically deselect records that were selected via the experimental `sap.ui.model.odata.v4.Context#setSelected` API.

    For more information, see the API Reference for [`v4.ODataModel#bindList`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel%23methods/bindList) and [`v4.Context#setSelected`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/setSelected).


<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
<tr>
<td valign="top">

1.124 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Accessibility** 

</td>
<td valign="top">

**Accessibility**

We are now using JAWS 2024 as a reference testing environment in OpenUI5. For more information, see the *Assistive technologies reference testing environment for SAPUI5* SAP Note [2564165](https://me.sap.com/notes/2564165).

<sub>Changed•Feature•Info Only•1.124</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-05-16

</td>
</tr>
</table>

