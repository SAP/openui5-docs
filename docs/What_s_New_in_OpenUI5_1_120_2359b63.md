<!-- loio2359b636a11a4236bb754c2bbf31e97f -->

| loio |
| -----|
| 2359b636a11a4236bb754c2bbf31e97f |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/2359b636a11a4236bb754c2bbf31e97f) | [demo kit latest release](https://sdk.openui5.org/topic/2359b636a11a4236bb754c2bbf31e97f)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.120

With this release OpenUI5 is upgraded from version 1.119 to 1.120.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

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

**End of Cloud Provisioning for OpenUI5 Versions \(Q4/2023\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q4/2023\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q4/2023.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.106
-   1.107

**Action**: Upgrade to a version that’s still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.57
    -   1.71.51-1.71.52
    -   1.84.28 to 1.84.30
    -   1.96.12 to 1.96.14

    **Action**: Upgrade to the latest available patch for the respective OpenUI5 version.

-   Other versions:

    -   1.102.8 to 1.102.11
    -   1.105.1 to 1.105.2

    **Action**: Upgrade to a version that’s still in maintenance.


For more information, see [UI5 Releases Ending Service in 2023](https://blogs.sap.com/2022/12/05/ui5-releases-ending-service-in-2023/) and [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Required•Upcoming</sub>

</td>
<td valign="top">

Required 

</td>
<td valign="top">

2023-12-31

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.VariantManagement`** 

</td>
<td valign="top">

**`sap.m.VariantManagement`**

We have introduced `sap.m.VariantManagement`, which replaces `sap.ui.comp.variants.VariantManagement` and offers a set of equivalent features. For more information, see [Transition to sap.m.VariantManagement](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/0b64485af6e4407d96ae27ae6773b401.html "This documentation is meant to ease the transition from sap.ui.comp.variants.VariantManagement (deprecated) to sap.m.VariantManagement.") :arrow_upper_right: and the [API Reference](https://sdk.openui5.org/api/sap.m.VariantManagement).

<sub>New•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**Deprecation of *Belize* and *Quartz* Themes** 

</td>
<td valign="top">

**Deprecation of *Belize* and *Quartz* Themes**

We have deprecated the *Belize* \(theme IDs: `sap_belize`, `sap_belize_plus`, `sap_belize_hcb`, `sap_belize_hcw`\) and *Quartz* \(theme IDs: `sap_fiori_3`, `sap_fiori_3_dark`, `sap_fiori_3_hcb`, `sap_fiori_3_hcw`\) theme families as of OpenUI5 version 1.120.2.

We recommend that you switch to the *Horizon* theme family \(theme IDs: `sap_horizon`, `sap_horizon_dark`, `sap_horizon_hcb`, `sap_horizon_hcw`\).

<sub>Deprecated•Announcement•Recommended•1.120</sub>

</td>
<td valign="top">

Recommended 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table*`** 

</td>
<td valign="top">

**`sap.ui.table*`**

-   The `sorted` property of `sap.ui.table.Column` has been deprecated. Instead, the `sortOrder` property has been enhanced to also support `None` \(using `sap.ui.core.SortOrder`\), which is now the default. To ensure backward compatibility, `sortOrder` is automatically changed from `None` to `Ascending` if the `sorted` property is set to `true`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Column%23controlProperties) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Sorting).

-   We have improved the cell selection in these tables for `CellSelector` and the behavior when selecting cells and ranges.
    -   You can now use `sap.m.plugins.CellSelector` even with an inactive `DragDropConfig`. To control if the plugin is active, we have added the `enabled` property.

    -   When using the [Shift\] and [Up Arrow\], [Down Arrow\] keys for cell selection, the cell selection now takes precedence over the range selection. Pressing [Esc\] will remove the current cell selection. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.SelectCopyPaste).



<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Field` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Field` \(experimental\)**

We have enabled the autocomplete feature for this experimental control. If the user enters text into a field, the first item in the result list that matches the text typed in by the user is automatically completed.

<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.table.ColumnWidthController`**

</td>
<td valign="top">

**`sap.m.table.ColumnWidthController`**

We have now enabled the resizing of columns for `sap.m.Table` and `sap.ui.table.Table` and not just `sap.ui.mdc.Table`. To enable this feature, we have made `ColumnWidthController` available as an extension of `sap.m.p13n.SelectionController`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.ColumnWidthController), the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.m.sample.p13n.EngineGridTable) for `sap.ui.table.Table`, and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.p13n.Engine) for `sap.m.Table`.

<sub>New•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

New 

</td>
<td valign="top">

User Documentation 

</td>
<td valign="top">

**Usage of Forms** 

</td>
<td valign="top">

**Usage of Forms**

To help users of forms choose the one that best suits their requirements, we have provided an overview of forms and how they can be used. For more information, see [Forms: Which One Should I Choose?](Forms_Which_One_Should_I_Choose_d1d8eb0.md) .

<sub>New•User Documentation•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Updated Configuration of the OpenUI5 Runtime** 

</td>
<td valign="top">

**Updated Configuration of the OpenUI5 Runtime**

We have implemented a modular, future-proof solution for configuration handling and deprecated the legacy `sap.ui.core.Configuration` module. To reflect these deprecations and the entities replacing them, the API Reference has been updated accordingly; the documentation will be gradually updated as well. For an updated list of configuration options, see [Configuration of the OpenUI5 Runtime](Configuration_of_the_OpenUI5_Runtime_91f08de.md) and [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Configuration).

<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Reworked Walkthrough Tutorial** 

</td>
<td valign="top">

**Reworked Walkthrough Tutorial**

You can now take the Walkthrough tutorial with UI5 Tooling as our preferred development environment; the sample code for all tutorial steps has been updated to work with UI5 Tooling out of the box. We also included features of modern ECMAScript and added an additional step showing how to build an application.

For more information, see [Walkthrough Tutorial](Walkthrough_Tutorial_3da5f4b.md).

<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Localization** 

</td>
<td valign="top">

**Localization**

We now use the localization content of the Unicode Common Locale Data Repository \(CLDR\) version 43.0.0.

<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

The `transitionMessagesOnly` parameter is now supported by `sap.ui.model.odata.v2.ODataTreeBinding`.

<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

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

-   For recursive hierarchies, we now provide the `sap.ui.model.odata.v4.Context#isAncestorOf` API to check whether a node is an ancestor of another node.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/isAncestorOf).

-   For recursive hierarchies, we provide the following **experimental APIs and features**. Note that they must not be used in productive applications yet:

    -   `sap.ui.model.odata.v4.Context#getParent` and `sap.ui.model.odata.v4.Context#requestParent` to retrieve the parent of a node

        For more information, see the API Reference for [`Context#getParent`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/getParent) and [`Context#requestParent`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/requestParent).

    -   Creation of new root nodes

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create).

    -   Deletion of nodes even if an initial expansion has been set via the `expandTo` parameter of `$$aggregation` / `v4.ODataListBinding#setAggregation`

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/delete).


-   The `withCredentials` model parameter is no longer experimental; you can now use it in productive applications.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel).


<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

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

We have deprecated all entities of `sap.ui.core.Core`, except the `ready` method.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Core).

For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

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

The `$...Settings` types \(the structures describing what data can be passed into constructors\) now also contain the `specialSettings` \(non-bindable data for initialization, like the `id`, `objectBindings`, `bindingContexts`, and the `componentData` for Components\).

<sub>Changed•Feature•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`** 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`**

We have added a new `width` property to the control. Depending on the theme, the control has a minimum width set. You can use the new property to increase the width. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.SideNavigation).

<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

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

We now provide a new `date` formatter. In contrast to the existing `dateTime` formatter, the new date formatter doesn’t include time in the formatted value by default. For more information, see the [Card Formatters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters/dateAndTime) section and [Date](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/dateAndTime/date) sample in the Card Explorer.

<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Avatar`** 

</td>
<td valign="top">

**`sap.m.Avatar`**

We have introduced a new `active` property that allows applications to control the avatar's active state when the user interacts with it or opens/closes the user menu. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Avatar).

<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
<tr>
<td valign="top">

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

Users can now easily customize the width of a column by dragging the column separators.

<sub>Changed•Control•Info Only•1.120</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2023-11-02

</td>
</tr>
</table>

