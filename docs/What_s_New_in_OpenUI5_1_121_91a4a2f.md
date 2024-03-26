<!-- loio91a4a2f59e444ada8d003369a580f61d -->

| loio |
| -----|
| 91a4a2f59e444ada8d003369a580f61d |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/91a4a2f59e444ada8d003369a580f61d) | [demo kit latest release](https://sdk.openui5.org/topic/91a4a2f59e444ada8d003369a580f61d)</div>

## What's New in OpenUI5 1.121

With this release OpenUI5 is upgraded from version 1.120 to 1.121.

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

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`** 

</td>
<td valign="top">

****`sap.m.List`, `sap.m.Table`, `sap.m.Tree`****

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\) , we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.ContextMenuSetting).

-   We have enabled the `rememberSelections` property that stores binding paths of selections after binding updates in OData V4. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/getRememberSelections).


<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\), we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.ContextMenuSetting).

-   We have implemented the static `findOn` function in plugin classes that allow you to find all plugins used in a given control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.plugins.MultiSelectionPlugin%23methods/sap.ui.table.plugins.MultiSelectionPlugin.findOn).


<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.plugins.CopyProvider`** 

</td>
<td valign="top">

**`sap.m.plugins.CopyProvider`**

We have provided copy and paste functionality that allows users to copy data in plain `text` and `html` format using the `extractDataHandler` of `sap.m.plugins.CopyProvider`. This way users can, for example, copy data in various data formats from a table to a spreadsheet and vice versa. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CopyProvider.extractDataHandler) and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TableCopy).

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Table` \(experimental\)**

-   In some simple scenarios, where the table is used to display information only \(read-only scenarios\), you might want to hide the toolbar of the table. To enable this, we have provided the `hideToolbar` property. See the documentation for restrictions related to this feature. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.Table%23methods/getHideToolbar).

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\) , we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.ContextMenuSetting).


<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Chart`, `sap.ui.mdc.FilterBar`, `sap.ui.mdc.Table` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Chart`, `sap.ui.mdc.FilterBar`, `sap.ui.mdc.Table` \(experimental\)**

So that delegate metadata can be easily understood, we have changed the main identifier attribute of `propertyInfo` from `name` to `key`. For compatibility reasons, we ensure that applications can still use the legacy format. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.util.PropertyInfo). 

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.m.p13n.Engine`** 

</td>
<td valign="top">

**`sap.m.p13n.Engine`**

-   We have enhanced personalization with filtering options: A filter panel is now available in the `Engine`. We have also enabled the implementation of a `FilterController`. This implementation includes variants and can be used by any control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.p13n.Engine) and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineCustomFilters).

-   You can now use several selection controllers of the same type. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.p13n.Engine) and the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineMultipleController).

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Field`, `sap.ui.mdc.FilterBar`, `sap.ui.mdc.ValueHelp` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Field`, `sap.ui.mdc.FilterBar`, `sap.ui.mdc.ValueHelp` \(experimental\)**

You can now copy and paste content, such as a combination of key and description, from a table or any type of tabular format, into filter fields. Note that only the first column of the table will be taken into account.

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabFilter`** 

</td>
<td valign="top">

**`sap.m.IconTabFilter`**

We have introduced a new \(experimental\) `interactionMode` property that you can use to control the interaction behavior of the tab filters in relation with their nested tabs and the availability of their own content. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabFilter) and the [Sample](https://sdk.openui5.org/entity/sap.tnt.ToolHeader/sample/sap.tnt.sample.ToolHeaderIconTabHeader).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Carousel`** 

</td>
<td valign="top">

**`sap.m.Carousel`**

Using the new `scrollMode` property, you can now allow users to browse through multiple carousel pages with one click. The available options are listed in the `sap.m.CarouselScrollMode` enum:

-   `SinglePage` \(default\) – the user can slide pages one by one. This was the behavior until now.
-   `VisiblePages` – when there are multiple visible pages in the carousel \(visiblePagesCount property has a value greater than one\), the user can slide them all with one click.

For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithMorePages). 

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

We have made several design enhancements to the control. Additionally, using the new `sap.tnt.NavigationListGroup` control, you can now arrange some of the navigation items in a group. For more information, see the [NavigationListGroup API Reference](https://sdk.openui5.org/api/sap.tnt.NavigationListGroup) and the [Sample](https://sdk.openui5.org/entity/sap.tnt.SideNavigation/sample/sap.tnt.sample.SideNavigation).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

-   We have \(experimentally\) added a new filter of type `sap.m.ComboBox`, which supports a two-column layout. For more information, see the [Combo Box Filter](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/comboBox) section and [ComboBox](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/comboBoxFilter) sample in the Card Explorer.
-   We have \(experimentally\) introduced an additional option to define actions-strip buttons in a list item or in a footer. It allows you to dynamically set specific actions for each list item in the List card. They can now be defined with a template, and can be based on the fetched data from a back-end service. For more information, see the [Actions Strip](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section and [Dynamic Actions Strip](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/dynamicActionsStrip) sample in the Card Explorer.
-   We have \(experimentally\) added an option to set group labels for one or more actions-strip buttons. For more information, see the [Actions Strip](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section and [Actions Labels](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/actionsLabels) sample in the Card Explorer.
-   We have introduced a new `preferIcon` property for the actions-strip buttons. If set to `true`, the button in the visible area is displayed only as an icon. This feature saves space in the actions strip. For more information, see the [Actions Strip](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section in the Card Explorer.
-   The following features are no longer experimental:

    -   Search filter
    -   CSRF tokens \(with new binding syntax\)
    -   Actions strip
    -   Card footer

    For more information, see the [Learn](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/gettingStarted) section in the Card Explorer.

-   We have \(experimentally\) enabled the Object card to show an image with text overlay. There are multiple new properties available that you can use to control how the image is displayed and the overlay behavior of the texts. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/objectCardWithImageWithOverlay) in the Card Explorer.

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Icon Explorer** 

</td>
<td valign="top">

**Icon Explorer**

We have added new icons to the SAP Fiori Tools icon font. Find the icon that fits your needs via the [Icon Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/iconExplorer/webapp/index.html) tool.

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

-   We have added support for `abstract` classes \(OpenUI5 classes marked as `abstract` are now also marked as such in the type definitions\).
-   Constructors hidden in OpenUI5 via `@hideconstructor` are now protected in the type definitions.

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Walkthrough Tutorial in TypeScript** 

</td>
<td valign="top">

**Walkthrough Tutorial in TypeScript**

A new tutorial is now available. This is the TypeScript version of our existing Walkthrough tutorial, offering you the same comprehensive tour of OpenUI5 but now in TypeScript.

For more information, see [Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md).

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

-   You can now use aliases for computed annotations in XML views. Use `template:require` or `<template:alias>` during templating and `core:require` in XML views for defining your aliases. Note that we no longer recommend using global names for computed annotations in XML views or during templating.

    For more information, see [Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md) and [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md).

-   You can now explicitly provide `$single` as a new group ID to`sap.ui.model.odata.v4.Context#delete`, `sap.ui.model.odata.v4.ODataModel#delete`, and `sap.ui.model.odata.v4.ODataContextBinding#execute`. Requests will then be sent as fast as with `$direct`, but they will be wrapped in a batch request as with `$auto`.

    For more information, see the API Reference for [`v4.Context#delete`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/delete), [`v4.ODataModel#delete`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel%23methods/delete), and [`v4.ODataContextBinding#execute`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding%23methods/execute).


<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Formatting** 

</td>
<td valign="top">

**Formatting**

We now support rounding of string-based values as used, for example, for `Edm.Decimal`.

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

We now use the localization content of the Unicode Common Locale Data Repository \(CLDR\) version 44.0.0.

<sub>Changed•Feature•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.ShellBar`** 

</td>
<td valign="top">

**`sap.f.ShellBar`**

We have reworked the positioning and naming of the AI copilot Joule and the search field in the `sap.f.ShellBar` for size XXL.

![](images/loio4c1af9cf431f48de9c61d32e68b8f885_LowRes.png)

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

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

We have introduced two new illustration types added to the default illustration set: `SignOut` and `NewMail`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.CheckBox`** 

</td>
<td valign="top">

**`sap.m.CheckBox`**

We have implemented the new `required` property for better interaction with assistive technologies. Please note, you should only use this property when it isn't possible to establish a single relationship between the field and a label. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.CheckBox). 

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.core.InvisibleMessage`** 

</td>
<td valign="top">

**`sap.ui.core.InvisibleMessage`**

The `sap.ui.core.InvisibleMessageMode` enum is no longer experimental. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.InvisibleMessageMode).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Popover`, `sap.m.ResponsivePopover`** 

</td>
<td valign="top">

**`sap.m.Popover`, `sap.m.ResponsivePopover`**

The `resizable` property is no longer experimental. You can make your popovers dynamic and responsive by resizing them. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Popover).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input`, `sap.m.MultiInput`, `sap.m.ComboBox`, `sap.m.MultiComboBox`** 

</td>
<td valign="top">

**`sap.m.Input`, `sap.m.MultiInput`, `sap.m.ComboBox`, `sap.m.MultiComboBox`**

We have prevented the closing of the suggestions popover when pressing [Enter\] on a group header item.

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Wizard`** 

</td>
<td valign="top">

**`sap.m.Wizard`**

-   We have added stable IDs to the list items in the `WizardProgressNavigator`.

-   The `sap.m.WizardRenderMode` property is no longer experimental. You can customize the rendering mode of the `sap.m.Wizard` control.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Wizard).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.InputBase`** 

</td>
<td valign="top">

**`sap.m.InputBase`**

The `formattedValueStateText` aggregation is no longer experimental. You can manage formatted value state texts within input controls without worrying about future changes. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.InputBase).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`, `sap.m.SinglePlanningCalendar`, and `sap.ui.unified.Calendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`, `sap.m.SinglePlanningCalendar`, and `sap.ui.unified.Calendar`**

We have added a new `Working` day type in the `sap.ui.unified.CalendarDayType` enum. Now you can set a weekend day as a working day when there is a work schedule that differs from the standard working-week days. For more information, see the [DateTypeRange API Reference](https://sdk.openui5.org/api/sap.ui.unified.DateTypeRange) and the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendarRow`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendarRow`**

We have introduced a new `rowHeaderDescription` property. As an application developer, you can use it to define the text that will be announced by screen readers when a user navigates to the row header. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendarRow).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

To improve the accessibility of the control, we have provided shorter and more user-friendly texts for screen-reader announcements of appointment durations. Now we use the full date format \(for example, “Thursday, August 17, 2023”\) instead of the short format \(“8/17/23”\). Additionally, now we use the shorter “From/To”, instead of “Start Time/End Time”.For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`** 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`**

You can use the new wrapping property of the `sap.m.ViewSettingsItem` control to change the item’s title text behavior from truncate \(default\) to wrapping. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsItem).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
<tr>
<td valign="top">

1.121 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.DynamicSideContent`** 

</td>
<td valign="top">

**`sap.ui.layout.DynamicSideContent`**

The default behavior of the control is to set the widths of the side content and the main content according to the screen size. Using the new `sideContentWidthM`, `sideContentWidthL`, and `sideContentWidthXL` properties you can now override the default values for M, L, and XL display breakpoints. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.DynamicSideContent).

<sub>Changed•Control•Info Only•1.121</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-02-22

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](What_s_New_in_OpenUI5_1_115_409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](What_s_New_in_OpenUI5_1_114_890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](What_s_New_in_OpenUI5_1_113_a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](What_s_New_in_OpenUI5_1_112_34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](What_s_New_in_OpenUI5_1_111_7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](What_s_New_in_OpenUI5_1_110_71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](What_s_New_in_OpenUI5_1_109_3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](What_s_New_in_OpenUI5_1_108_66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](What_s_New_in_OpenUI5_1_107_d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](What_s_New_in_OpenUI5_1_106_5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](What_s_New_in_OpenUI5_1_105_4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](What_s_New_in_OpenUI5_1_104_69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](What_s_New_in_OpenUI5_1_103_0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](What_s_New_in_OpenUI5_1_102_f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

