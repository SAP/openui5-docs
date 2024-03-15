<!-- loio5d078da3eec34ab59c7c28a30c93cf59 -->

| loio |
| -----|
| 5d078da3eec34ab59c7c28a30c93cf59 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/5d078da3eec34ab59c7c28a30c93cf59) | [demo kit latest release](https://sdk.openui5.org/topic/5d078da3eec34ab59c7c28a30c93cf59)</div>

## What's New in OpenUI5 1.122

With this release OpenUI5 is upgraded from version 1.121 to 1.122.

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

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`, `sap.ui.layout.form.SimpleForm`** 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`, `sap.ui.layout.form.SimpleForm`**

You can now define up to three columns in medium and four in large size in a form using `ColumnLayout`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.form.ColumnsL) for columns in L, the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.form.ColumnsM) for columns in M, the [Sample](https://sdk.openui5.org/entity/sap.ui.layout.form.Form/sample/sap.ui.layout.sample.Form_Column_threeGroups346) for `Form`, and the [Sample](https://sdk.openui5.org/entity/sap.ui.layout.form.SimpleForm/sample/sap.ui.layout.sample.SimpleForm_Column_threeGroups346) for `SimpleForm`.

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Samples for `sap.ui.mdc` library** 

</td>
<td valign="top">

**Samples for `sap.ui.mdc` library**

You can now test more features of the controls in the \(experimental\) `sap.ui.mdc` library in the samples. To find the samples for this library in the Demo Kit, go to *Samples* and select MDC Samples. For more information, see the [Samples](https://sdk.openui5.org/entity/sap.ui.mdc).

<sub>Changed•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Support for Async Control Event Handlers** 

</td>
<td valign="top">

**Support for Async Control Event Handlers**

You can now use the modern “`async`/`await`” JavaScript syntax for control event handlers. We have adjusted some tutorials and samples to benefit from this coding style.

Keep in mind that certain restrictions remain for asynchronous functions; in particular, they should not be used with the lifecycle hooks predefined by the OpenUI5 framework.

For more information, see [Async Functions and Event Handlers](ECMAScript_Support_0cb44d7.md#loio0cb44d7a147640a0890cefa5fd7c7f8e__section_EHR).

<sub>Changed•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Localization** 

</td>
<td valign="top">

**Localization**

We have deprecated the Legacy Unit Key Mapping introduced with OpenUI5 1.110 and will no longer adapt it when switching to future versions of the Unicode Common Locale Data Repository \(CLDR\).

<sub>Deprecated•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Data Binding** 

</td>
<td valign="top">

**Data Binding**

We have reworked the Data Binding tutorial, offering you state-of-the-art usage of data binding in OpenUI5.

For more information, see [Data Binding Tutorial](Data_Binding_Tutorial_e531093.md).

<sub>Changed•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

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

-   The selection set via the experimental `sap.ui.model.odata.v4.Context#setSelected` method is now also available via the experimental `@$ui5.context.isSelected` client-side annotation.

-   The `sap.ui.model.odata.v4.Context#requestParent` and `sap.ui.model.odata.v4.Context#getParent` methods that we introduced with OpenUI5 1.120 are no longer experimental; you can now use them in productive applications.

-   The `refresh` and `requestRefresh` methods of `sap.ui.model.odata.v4.ODataContextBinding` and `sap.ui.model.odata.v4.ODataListBinding` now also work on bindings for which the `$$ownRequest` binding parameter is set to `true`.


<sub>Changed•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ColorPalette`** 

</td>
<td valign="top">

**`sap.m.ColorPalette`**

We have introduced a new \(experimental\) `selectedColor` property that shows the last selected color in the color palette. Now, when the user selects a color, the selected color swatch appears bigger than the other color swatches and has an outline. If the user moves the focus, the selected color will continue to be shown until a new color is selected. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ColorPalette).

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MenuButton`** 

</td>
<td valign="top">

**`sap.m.MenuButton`**

We have removed the maximum-width restriction of the `MenuButton` to avoid any undesirable text truncation. Now, the button will expand according to the available space when necessary. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MenuButton).

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`** 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`**

To improve the user experience, we have configured the calendar to always show 6 weeks. The new behavior will prevent any unnecessary resizing when the user browses across months. For more information, see the [Samples](https://sdk.openui5.org/entity/sap.ui.unified.Calendar).

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

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

There is a new \(experimental\) feature in Analytical cards for the popover that opens when the user presses the interactive area \(when it’s available\). As a card developer, you can now specify an action button at the bottom of this popover. The action can be either a standard navigation action, or a custom-defined extension. For more information, see the [Details Popover](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/detailsPopover) and [Popover Extension Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/popoverExtensionActions) samples, and the [Analytical Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/analytical) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.ObjectPageSection`** 

</td>
<td valign="top">

**`sap.uxap.ObjectPageSection`**

We have added a new `anchorBarButtonColor` property. It allows you to specify the text color of each button inside the `AnchorBar`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageSection).

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`** 

</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

We have introduced a new `sapUxAPObjectPageSubSectionTransparentBackground` class for `sap.uxap.ObjectPageSubSection` that allows applications to set a transparent background for subsections. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageSubSection).

<sub>Changed•Control•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
<tr>
<td valign="top">

1.122 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

****Demo Kit: New Design for the Tools Section**** 

</td>
<td valign="top">

**Demo Kit: New Design for the Tools Section**

We have redesigned the Tools section of the Demo Kit. It is now called Resources and has a new look and feel. For more information, see [Resources](https://sdk.openui5.org/resources).

<sub>Changed•Feature•Info Only•1.122</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-03-21

</td>
</tr>
</table>

