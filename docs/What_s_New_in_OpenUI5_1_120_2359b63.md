<!-- loio2359b636a11a4236bb754c2bbf31e97f -->

| loio |
| -----|
| 2359b636a11a4236bb754c2bbf31e97f |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/2359b636a11a4236bb754c2bbf31e97f) | [demo kit latest release](https://sdk.openui5.org/topic/2359b636a11a4236bb754c2bbf31e97f)</div>

## What's New in OpenUI5 1.120

With this release OpenUI5 is upgraded from version 1.119 to 1.120.

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

1.120 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.Table`** 

</td>
<td valign="top">

**`sap.ui.table.Table`**

With OpenUI5 version 1.120.2, we have introduced the `findOn` function for selection plugins, which allows you to search for these plugins in a given table.

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

Control 

</td>
<td valign="top">

**`sap.m.VariantManagement`** 

</td>
<td valign="top">

**`sap.m.VariantManagement`**

We have introduced `sap.m.VariantManagement`, which replaces `sap.ui.comp.variants.VariantManagement` and offers a set of equivalent features. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.VariantManagement).

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

**Deprecation of *Belize* Themes** 

</td>
<td valign="top">

**Deprecation of *Belize* Themes**

We have deprecated the *Belize* \(theme IDs: `sap_belize`, `sap_belize_plus`, `sap_belize_hcb`, `sap_belize_hcw`\) theme family as of OpenUI5 version 1.120.2.

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

We have now enabled the resizing of columns for `sap.m.Table` and `sap.ui.table.Table`, and not just `sap.ui.mdc.Table`. To enable this feature, we have made `ColumnWidthController` available as an extension of `sap.m.p13n.SelectionController`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.ColumnWidthController), the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.m.sample.p13n.EngineGridTable) for `sap.ui.table.Table`, and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.p13n.Engine) for `sap.m.Table`.

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

Announcement 

</td>
<td valign="top">

**Apply Best Practices to Become Future-Ready \(as of 1.120.2\)** 

</td>
<td valign="top">

**Apply Best Practices to Become Future-Ready \(as of 1.120.2\)**

The OpenUI5 framework has been evolving constantly, for instance to account for features in browser development \(such as modern ECMAScript support\) or their end of maintenance \(such as the end of IE11 support\). Substantial modularization efforts were a crucial step on this journey, which continues towards a future major version upgrade. In recent releases, but particularly with OpenUI5 1.120, a significant number of improvements have been introduced, for example the replacement of legacy APIs of the `Core` and `Configuration` modules.

To make sure that your code bases, that is, your OpenUI5 applications and libraries, do not become legacy but are ready for the future, please continue applying best practices. To support your efforts, we are updating the documentation in many places, with OpenUI5 1.120 but also beyond. [Best Practices for Developers](Best_Practices_for_Developers_28fcd55.md) aims to be a good starting point for you, collecting fundamental information and offering practical guidance. Thanks for your support!

<sub>Changed•Announcement•Info Only•1.120</sub>

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

We have implemented a modular, future-proof solution for configuration handling, and deprecated the legacy `sap.ui.core.Configuration` module. To reflect these deprecations and the entities replacing them, the API Reference has been updated and documentation on the [Deprecated Configuration API](Deprecated_Configuration_API_2acafbf.md) has been added \(as of 1.120.2\). For an updated list of configuration options, see [Configuration of the OpenUI5 Runtime](Configuration_of_the_OpenUI5_Runtime_91f08de.md) and [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

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

-   We now use the localization content of the Unicode Common Locale Data Repository \(CLDR\) version 43.0.0.

-   We now support the following additional locales \(as of 1.120.5\):

    -   mk\_MK
    -   cnr\_ME
    -   sr\_Cyrl\_RS


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

    -   Creating new root nodes

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create).

    -   Moving nodes to become root nodes \(as of 1.120.2\)

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/move).

    -   Deleting nodes, even if an initial expansion has been set using the `expandTo` parameter of `$$aggregation` / `v4.ODataListBinding#setAggregation`

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/delete).

    -   Creating nodes, even if an initial expansion has been set using the `expandTo` parameter of `$$aggregation` / `v4.ODataListBinding#setAggregation` \(as of 1.120.2\)

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4ODataListBinding%23methods/create).

    -   Moving nodes, even if the hierarchy has been fully expanded using the `expandTo` parameter of `$$aggregation` / `v4.ODataListBinding#setAggregation` \(as of 1.120.2\).

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/move).


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

We have deprecated all entities of `sap.ui.core.Core`, except for the `ready` method. For more information, see [Deprecated Core API](Deprecated_Core_API_798dd9a.md) \(as of 1.120.2\)and the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Core).

We have also deprecated the entire `sap.ui.core.Configuration` module. For more information, see *Updated Configuration of the OpenUI5 Runtime* in this What's New \(as of 1.120.2\).

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

