<!-- loio91a4a2f59e444ada8d003369a580f61d -->

# What's New in OpenUI5 1.121

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

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\) , we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.plugins.ContextMenuSetting).

-   We have enabled the `rememberSelections` property that stores binding paths of selections after binding updates in OData V4. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.ListBase%23methods/getRememberSelections).


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

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\), we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.plugins.ContextMenuSetting).

-   We have implemented the static `findOn` function in plugin classes that allow you to find all plugins used in a given control. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin%23methods/sap.ui.table.plugins.MultiSelectionPlugin.findOn).


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

We have provided copy and paste functionality that allows users to copy data in plain `text` and `html` format using the `extractDataHandler` of `sap.m.plugins.CopyProvider`. This way users can, for example, copy data in various data formats from a table to a spreadsheet and vice versa. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.plugins.CopyProvider.extractDataHandler) and the [Sample](https://ui5.sap.com/#/entity/sap.m.Table/sample/sap.m.sample.TableCopy).

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

-   In some simple scenarios, where the table is used to display information only \(read-only scenarios\), you might want to hide the toolbar of the table. To enable this, we have provided the `hideToolbar` property. See the documentation for restrictions related to this feature. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.mdc.Table%23methods/getHideToolbar).

-   To visualize which scope is affected by the context menu actions \(a single row or all selected rows\) , we have enabled the new `ContextMenuSetting` plugin. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.plugins.ContextMenuSetting).


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

So that delegate metadata can be easily understood, we have changed the main identifier attribute of `propertyInfo` from `name` to `key`. For compatibility reasons, we ensure that applications can still use the legacy format. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.mdc.util.PropertyInfo). 

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

-   We have enhanced personalization with filtering options: A filter panel is now available in the `Engine`. We have also enabled the implementation of a `FilterController`. This implementation includes variants and can be used by any control. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.p13n.Engine) and the [Sample](https://ui5.sap.com/#/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineCustomFilters).

-   You can now use several selection controllers of the same type. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.p13n.Engine) and the [Sample](https://ui5.sap.com/#/entity/sap.m.p13n.Engine/sample/sap.m.sample.p13n.EngineMultipleController).

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

We have introduced a new \(experimental\) `interactionMode` property that you can use to control the interaction behavior of the tab filters in relation with their nested tabs and the availability of their own content. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.IconTabFilter) and the [Sample](https://ui5.sap.com/#/entity/sap.tnt.ToolHeader/sample/sap.tnt.sample.ToolHeaderIconTabHeader).

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

For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.Carousel/sample/sap.m.sample.CarouselWithMorePages). 

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

We have made several design enhancements to the control. Additionally, using the new `sap.tnt.NavigationListGroup` control, you can now arrange some of the navigation items in a group. For more information, see the [NavigationListGroup API Reference](https://ui5.sap.com/#/api/sap.tnt.NavigationListGroup) and the [Sample](https://ui5.sap.com/#/entity/sap.tnt.SideNavigation/sample/sap.tnt.sample.SideNavigation).

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

-   We have \(experimentally\) added a new filter of type `sap.m.ComboBox`, which supports a two-column layout. For more information, see the [Combo Box Filter](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/filters/comboBox) section and [ComboBox](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/comboBoxFilter) sample in the Card Explorer.
-   We have \(experimentally\) introduced an additional option to define actions-strip buttons in a list item or in a footer. It allows you to dynamically set specific actions for each list item in the List card. They can now be defined with a template, and can be based on the fetched data from a back-end service. For more information, see the [Actions Strip](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section and [Dynamic Actions Strip](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/dynamicActionsStrip) sample in the Card Explorer.
-   We have \(experimentally\) added an option to set group labels for one or more actions-strip buttons. For more information, see the [Actions Strip](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section and [Actions Labels](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/actionsLabels) sample in the Card Explorer.
-   We have introduced a new `preferIcon` property for the actions-strip buttons. If set to `true`, the button in the visible area is displayed only as an icon. This feature saves space in the actions strip. For more information, see the [Actions Strip](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/actionsStrip) section in the Card Explorer.
-   The following features are no longer experimental:

    -   Search filter
    -   CSRF tokens \(with new binding syntax\)
    -   Actions strip
    -   Card footer

    For more information, see the [Learn](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/gettingStarted) section in the Card Explorer.

-   We have \(experimentally\) enabled the Object card to show an image with text overlay. There are multiple new properties available that you can use to control how the image is displayed and the overlay behavior of the texts. For more information, see the [Object Card](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and [Sample](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/objectCardWithImageWithOverlay) in the Card Explorer.

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

We have added new icons to the SAP Fiori Tools icon font. Find the icon that fits your needs via the [Icon Explorer](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/iconExplorer/webapp/index.html) tool.

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

For more information, see [Walkthrough Tutorial (TypeScript)](https://help.sap.com/viewer/93953b95df5f4e938c8eb421cef56319/1.138_SAPUI5_ABAP/en-US/dad1905a07f849ce9c509721317d38d8.html "In this tutorial we'll introduce you to all major development paradigms of SAPUI5. We'll demonstrate the use of TypeScript with SAPUI5 and highlight the specific characteristics of this approach.") :arrow_upper_right:.

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

    For more information, see [Require Modules in XML View and Fragment](../04_Essentials/require-modules-in-xml-view-and-fragment-b11d853.md) and [Meta Model for OData V4](../04_Essentials/meta-model-for-odata-v4-7f29fb3.md).

-   You can now explicitly provide `$single` as a new group ID to`sap.ui.model.odata.v4.Context#delete`, `sap.ui.model.odata.v4.ODataModel#delete`, and `sap.ui.model.odata.v4.ODataContextBinding#execute`. Requests will then be sent as fast as with `$direct`, but they will be wrapped in a batch request as with `$auto`.

    For more information, see the API Reference for [`v4.Context#delete`](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.Context%23methods/delete), [`v4.ODataModel#delete`](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/delete), and [`v4.ODataContextBinding#execute`](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.ODataContextBinding%23methods/execute).


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

We have introduced two new illustration types added to the default illustration set: `SignOut` and `NewMail`. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.IllustratedMessage).

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

We have implemented the new `required` property for better interaction with assistive technologies. Please note, you should only use this property when it isn't possible to establish a single relationship between the field and a label. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.CheckBox). 

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

The `sap.ui.core.InvisibleMessageMode` enum is no longer experimental. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.core.InvisibleMessageMode).

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

The `resizable` property is no longer experimental. You can make your popovers dynamic and responsive by resizing them. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Popover).

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

For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Wizard).

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

The `formattedValueStateText` aggregation is no longer experimental. You can manage formatted value state texts within input controls without worrying about future changes. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.InputBase).

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

We have added a new `Working` day type in the `sap.ui.unified.CalendarDayType` enum. Now you can set a weekend day as a working day when there is a work schedule that differs from the standard working-week days. For more information, see the [DateTypeRange API Reference](https://ui5.sap.com/#/api/sap.ui.unified.DateTypeRange) and the [Sample](https://ui5.sap.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarWithLegend).

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

We have introduced a new `rowHeaderDescription` property. As an application developer, you can use it to define the text that will be announced by screen readers when a user navigates to the row header. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.PlanningCalendarRow).

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

To improve the accessibility of the control, we have provided shorter and more user-friendly texts for screen-reader announcements of appointment durations. Now we use the full date format \(for example, “Thursday, August 17, 2023”\) instead of the short format \(“8/17/23”\). Additionally, now we use the shorter “From/To”, instead of “Start Time/End Time”.For more information, see the [Sample](https://ui5.sap.com/#/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendar).

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

You can use the new wrapping property of the `sap.m.ViewSettingsItem` control to change the item’s title text behavior from truncate \(default\) to wrapping. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.ViewSettingsItem).

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

The default behavior of the control is to set the widths of the side content and the main content according to the screen size. Using the new `sideContentWidthM`, `sideContentWidthL`, and `sideContentWidthXL` properties you can now override the default values for M, L, and XL display breakpoints. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.layout.DynamicSideContent).

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

**Parent topic:**[Previous Versions](previous-versions-6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.135](what-s-new-in-openui5-1-135-93d7630.md "With this release OpenUI5 is upgraded from version 1.134 to 1.135.")

[What's New in OpenUI5 1.134](what-s-new-in-openui5-1-134-c512d71.md "With this release OpenUI5 is upgraded from version 1.133 to 1.134.")

[What's New in OpenUI5 1.133](what-s-new-in-openui5-1-133-86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](what-s-new-in-openui5-1-132-bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](what-s-new-in-openui5-1-131-7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](what-s-new-in-openui5-1-130-85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](what-s-new-in-openui5-1-129-d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](what-s-new-in-openui5-1-128-1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](what-s-new-in-openui5-1-127-e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](what-s-new-in-openui5-1-126-1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](what-s-new-in-openui5-1-125-9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](what-s-new-in-openui5-1-124-7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](what-s-new-in-openui5-1-123-9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](what-s-new-in-openui5-1-122-5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.120](what-s-new-in-openui5-1-120-2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](what-s-new-in-openui5-1-119-0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](what-s-new-in-openui5-1-118-3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](what-s-new-in-openui5-1-117-029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](what-s-new-in-openui5-1-116-ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](what-s-new-in-openui5-1-115-409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](what-s-new-in-openui5-1-114-890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](what-s-new-in-openui5-1-113-a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](what-s-new-in-openui5-1-112-34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](what-s-new-in-openui5-1-111-7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](what-s-new-in-openui5-1-110-71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](what-s-new-in-openui5-1-109-3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](what-s-new-in-openui5-1-108-66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](what-s-new-in-openui5-1-107-d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](what-s-new-in-openui5-1-106-5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](what-s-new-in-openui5-1-105-4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](what-s-new-in-openui5-1-104-69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](what-s-new-in-openui5-1-103-0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](what-s-new-in-openui5-1-102-f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](what-s-new-in-openui5-1-101-7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](what-s-new-in-openui5-1-100-27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](what-s-new-in-openui5-1-99-4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](what-s-new-in-openui5-1-98-d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](what-s-new-in-openui5-1-97-fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](what-s-new-in-openui5-1-96-7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](what-s-new-in-openui5-1-95-a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](what-s-new-in-openui5-1-94-c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](what-s-new-in-openui5-1-93-f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](what-s-new-in-openui5-1-92-1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](what-s-new-in-openui5-1-91-0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](what-s-new-in-openui5-1-90-91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](what-s-new-in-openui5-1-89-e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](what-s-new-in-openui5-1-88-e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](what-s-new-in-openui5-1-87-b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](what-s-new-in-openui5-1-86-4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](what-s-new-in-openui5-1-85-1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](what-s-new-in-openui5-1-84-dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](what-s-new-in-openui5-1-82-3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](what-s-new-in-openui5-1-81-f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](what-s-new-in-openui5-1-80-8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](what-s-new-in-openui5-1-79-99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](what-s-new-in-openui5-1-78-f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](what-s-new-in-openui5-1-77-c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](what-s-new-in-openui5-1-76-aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](what-s-new-in-openui5-1-75-5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](what-s-new-in-openui5-1-74-c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](what-s-new-in-openui5-1-73-231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](what-s-new-in-openui5-1-72-521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](what-s-new-in-openui5-1-71-a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](what-s-new-in-openui5-1-70-f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](what-s-new-in-openui5-1-69-89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](what-s-new-in-openui5-1-68-f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](what-s-new-in-openui5-1-67-a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](what-s-new-in-openui5-1-66-c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](what-s-new-in-openui5-1-65-0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](what-s-new-in-openui5-1-64-0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](what-s-new-in-openui5-1-63-e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](what-s-new-in-openui5-1-62-771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](what-s-new-in-openui5-1-61-d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](what-s-new-in-openui5-1-60-5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](what-s-new-in-openui5-1-58-7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](what-s-new-in-openui5-1-56-108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](what-s-new-in-openui5-1-54-c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](what-s-new-in-openui5-1-52-849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](what-s-new-in-openui5-1-50-759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](what-s-new-in-openui5-1-48-fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](what-s-new-in-openui5-1-46-6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](what-s-new-in-openui5-1-44-a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](what-s-new-in-openui5-1-42-468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](what-s-new-in-openui5-1-40-fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](what-s-new-in-openui5-1-38-f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

